---
UID: NS:d3dkmddi._DXGKARG_CONNECTDOORBELL
tech.root: display
title: DXGKARG_CONNECTDOORBELL
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the DXGKARG_CONNECTDOORBELL structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_FUTURE
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_CONNECTDOORBELL
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_CONNECTDOORBELL
 - DXGKARG_CONNECTDOORBELL
f1_keywords:
 - _DXGKARG_CONNECTDOORBELL
 - d3dkmddi/_DXGKARG_CONNECTDOORBELL
 - DXGKARG_CONNECTDOORBELL
 - d3dkmddi/DXGKARG_CONNECTDOORBELL
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_CONNECTDOORBELL
---

## -description

The **DXGKARG_CONNECTDOORBELL** structure contains parameters for [**DxgkDdiConnectDoorbell**](ns-d3dkmddi-dxgkddi_connectdoorbell.md).

## -struct-fields

### -field hDoorbell

[in] KMD handle to the doorbell object, which was previously created using [**DxgkDdiCreateDoorbell**](nc-d3dkmddi-dxgkddi_createdoorbell.md).

### -field Flags

[in] A bit field of [**DXGKARG_CONNECTDOORBELL_FLAGS**](ns-d3dkmddi-dxgkarg_connectdoorbell_flags.md) values specifying the doorbell connection flags. If UMD created this doorbell with the **RequireSecondaryCpuVA** flag, then *Dxgkrnl* sets the **RequireSecondaryAddress** flag in this DDI to inform KMD that this doorbell requires two physical addresses.

### -field KernelCpuVirtualAddress

[out] Kernel-mode CPU virtual address mapped to the physical address that KMD wants to assign to this doorbell. *Dxgkrnl* will map this address to a process address space CPU virtual address that was provided to the UMD in [**D3DKMTCreateDoorbell**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreatedoorbell.md). UMD will write a specific value to this address, effectively "ringing the doorbell" to notify the GPU scheduler of new work submission on HwQueue1.

### -field SecondaryKernelCpuVirtualAddress

[out/optional] Kernel-mode CPU virtual address mapped to the secondary physical address that KMD wants to assign to this doorbell, if required.

### -field Status

[out] A [**D3DDDI_DOORBELLSTATUS**](../d3dukmdt/ne-d3dukmdt-d3dddi_doorbellstatus.md) value that KMD wants *Dxgkrnl* to write into the UMD-visible page that [**pDoorbellStatusCpuVirtualAddress**](../d3dkmthk/ns-d3dkmthk-d3dkmt_create_doorbell.md) points to. This value can only be D3DDDI_DOORBELL_STATUS_CONNECTED or D3DDDI_DOORBELL_STATUS_CONNECTED_NOTIFY.

## -see-also

[**D3DDDI_DOORBELLSTATUS**](../d3dukmdt/ne-d3dukmdt-d3dddi_doorbellstatus.md)

[**D3DKMTCreateDoorbell**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreatedoorbell.md)

[**DXGKARG_CONNECTDOORBELL_FLAGS**](ns-d3dkmddi-dxgkarg_connectdoorbell_flags.md)

[**DxgkDdiConnectDoorbell**](ns-d3dkmddi-dxgkddi_connectdoorbell.md)
