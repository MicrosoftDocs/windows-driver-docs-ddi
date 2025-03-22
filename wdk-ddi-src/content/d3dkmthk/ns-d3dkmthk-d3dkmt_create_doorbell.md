---
UID: NS:d3dkmthk._D3DKMT_CREATE_DOORBELL
tech.root: display
title: D3DKMT_CREATE_DOORBELL
ms.date: 04/08/2024
targetos: Windows
description: Learn more about the D3DKMT_CREATE_DOORBELL structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMT_CREATE_DOORBELL
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CREATE_DOORBELL
 - D3DKMT_CREATE_DOORBELL
f1_keywords:
 - _D3DKMT_CREATE_DOORBELL
 - d3dkmthk/_D3DKMT_CREATE_DOORBELL
 - D3DKMT_CREATE_DOORBELL
 - d3dkmthk/D3DKMT_CREATE_DOORBELL
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DKMT_CREATE_DOORBELL
---

# D3DKMT_CREATE_DOORBELL structure (d3dkmthk.h)

## -description

The **D3DKMT_CREATE_DOORBELL** structure contains parameters for [**D3DKMTCreateDoorbell**](nf-d3dkmthk-d3dkmtcreatedoorbell.md).

## -struct-fields

### -field hHwQueue

[in] UMD handle of the hardware queue object created in a prior call to [**D3DKMTCreateHwQueue**](nf-d3dkmthk-d3dkmtcreatehwqueue.md). This handle identifies the hardware queue for which a doorbell needs to be assigned.

### -field hRingBuffer

[in] UMD handle to a ring buffer allocation that UMD [previously created](nf-d3dkmthk-d3dkmtcreateallocation.md). The allocation must be GPU visible and already resident. *Dxgkrnl* passes along the GPU virtual address (VA) and size of this allocation to KMD in a corresponding [**DxgkDdiCreateDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createdoorbell.md) call. The [**ResizeRingBufferOperation**](ns-d3dkmthk-d3dkmt_create_doorbell_flags.md) flag is a hint from UMD to KMD that a doorbell is being recreated for this hardware queue with a new, resized ring buffer.

### -field hRingBufferControl

[in/optional] UMD handle to a ring buffer control allocation [previously created](nf-d3dkmthk-d3dkmtcreateallocation.md) by UMD. UMD and KMD can use this allocation as a control area to store ring buffer read/write pointer locations if required. The allocation must be GPU visible and already resident when UMD calls **D3DKMTCreateDoorbell**. *Dxgkrnl* passes along the GPU VA and size of this allocation to KMD in a corresponding [**DxgkDdiCreateDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createdoorbell.md) call.

### -field Flags

[in/optional] A bit field of [**D3DKMT_CREATE_DOORBELL_FLAGS**](ns-d3dkmthk-d3dkmt_create_doorbell_flags.md) values specifying the doorbell creation flags.

### -field PrivateDriverDataSize

[in] Size of the private driver data that **pPrivateDriverData** points to, in bytes.

### -field PrivateDriverData

[in/out] Pointer to a buffer that is private to the driver. The size of this buffer is specified by **PrivateDriverDataSize**. The maximum buffer size allowed is D3DDDI_DOORBELL_PRIVATEDATA_MAX_BYTES_WDDM3_1 bytes.

### -field DoorbellCPUVirtualAddress

[out] Pointer to the CPU VA (both read/write) reserved by the OS for this doorbell. UMD will write a specific value to this address, effectively "ringing the doorbell" to notify the GPU scheduler of a new work submission on the hardware queue. This address remains constant over the lifetime of the doorbell, even if the underlying physical doorbell gets disconnected. The UMD should always use this address to write/read to this doorbell.

### -field DoorbellSecondaryCPUVirtualAddress

[out/optional] Pointer to a secondary CPU VA (both read/write) reserved by the OS for this doorbell.

On hardware that implements a secondary doorbell location the UMD sets the [**RequireSecondaryCpuVA**](ns-d3dkmthk-d3dkmt_create_doorbell_flags.md) flag. For such devices, the OS will reserve another CPU VA for this doorbell. Over the lifetime of the doorbell, this address will remain constant even if the underlying physical doorbell gets disconnected.

### -field DoorbellStatusCPUVirtualAddress

[out] Pointer to the CPU VA of the doorbell status. The value at this address indicates to the UMD whether the doorbell assigned to this hardware queue is currently connected. Each time the UMD submits new work to the queue and rings the doorbell, it must check this value to determine whether the doorbell ring succeeded. If the ring failed, UMD must call [**D3DKMTConnectDoorbell**](nf-d3dkmthk-d3dkmtconnectdoorbell.md) to reconnect the doorbell and then try submitting the work again.

The OS allocates and writes this 64-bit doorbell status memory, maps it into the process’s address space, and gives its user-mode CPU VA to the UMD to read from. Hence, UMD should read the 64-bit value stored in this address to obtain the doorbell status. The value of this address can be one of the [**D3DDDI_DOORBELL_STATUS**](../d3dukmdt/ne-d3dukmdt-d3dddi_doorbellstatus.md) enum values.

This address remains constant over the lifetime of the doorbell, even if the underlying physical doorbell gets disconnected. The UMD should always use this address to read the doorbell's status.

Only the OS writes to and updates this status memory:

* On successful return from [**DxgkDdiConnectDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkddi_connectdoorbell.md), the OS writes the status as D3DDDI_DOORBELL_STATUS_CONNECTED.
* If the OS disconnects the doorbell as part of suspending the hardware queue or powering down the GPU, it calls KMD's **DxgkDdiDisconnectDoorbell** and then writes the status as D3DDDI_DOORBELL_STATUS_DISCONNECTED_RETRY.
* If the KMD wants to disconnect the doorbell for any reason, it calls the [**DxgkDisconnectDoorbellCB**](../d3dkmddi/nc-d3dkmddi-dxgkcb_disconnectdoorbell.md) callback to inform the OS. KMD provides D3DDDI_DOORBELL_STATUS as the status, which the OS writes to this status page.
* In GPU lost or stopped scenarios, the OS writes D3DDDI_DOORBELL_STATUS_DISCONNECTED_ABORT as the status.

### -field HwQueueProgressFenceLastQueuedValueCPUVirtualAddress

[out] CPU VA of the location where the UMD will write the newly queued progress fence value every time a new command buffer is appended to the ring buffer.

### -field hDoorbell

[out] Runtime handle to the newly created doorbell object.

## -remarks

For more information, see [User-mode work submission](/windows-hardware/drivers/display/user-mode-work-submission).

## -see-also

[**D3DKMT_CREATE_DOORBELL_FLAGS**](ns-d3dkmthk-d3dkmt_create_doorbell_flags.md)

[**D3DKMTConnectDoorbell**](nf-d3dkmthk-d3dkmtconnectdoorbell.md)

[**D3DKMTCreateAllocation**](nf-d3dkmthk-d3dkmtcreateallocation.md)

[**D3DKMTCreateDoorbell**](nf-d3dkmthk-d3dkmtcreatedoorbell.md)

[**DxgkDdiConnectDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkddi_connectdoorbell.md)

[**DxgkDdiCreateDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createdoorbell.md)
