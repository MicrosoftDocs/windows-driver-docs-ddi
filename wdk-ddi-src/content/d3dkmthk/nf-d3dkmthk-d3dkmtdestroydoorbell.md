---
UID: NF:d3dkmthk.D3DKMTDestroyDoorbell
tech.root: display
title: D3DKMTDestroyDoorbell
ms.date: 04/08/2024
targetos: Windows
description: Learn more about the D3DKMTDestroyDoorbell function.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMTDestroyDoorbell
f1_keywords:
 - D3DKMTDestroyDoorbell
 - d3dkmthk/D3DKMTDestroyDoorbell
dev_langs:
 - c++
helpviewer_keywords:
 - D3DKMTDestroyDoorbell
---

# D3DKMTDestroyDoorbell function (d3dkmthk.h)

## -description

**D3DKMTDestroyDoorbell** destroys a doorbell.

## -parameters

### -param unnamedParam1

[in] Pointer to a [**D3DKMT_DESTROY_DOORBELL**](ns-d3dkmthk-d3dkmt_destroy_doorbell.md) structure that identifies the hardware queue whose doorbell is to be destroyed.

## -returns

**D3DKMTDestroyDoorbell** returns STATUS_SUCCESS when the OS successfully destroys the doorbell object. If **hDoorbell** points to a valid doorbell, then this call always succeeds; otherwise it returns STATUS_INVALID_PARAMETER.

## -remarks

When UMD calls **D3DKMTDestroyDoorbell**, the OS does the following:

* Removes its reference to **hRingBuffer** and to **hRingBufferControl** allocations belonging to this doorbell.
* Frees the mapping that **DoorbellStatusCPUVirtualAddress** points to.
* Frees both the user-mode and kernel-mode mappings that **DoorbellCPUVirtuslAddress** points to.
* Calls KMD's [**DxgkDdiDestroyDoorbell**] so that KMD can disconnect the physical doorbell location and destroy its doorbell objects.

The UMD must not use the handle after calling **D3DKMTDestroyDoorbell**.

For more information, see [User-mode work submission](/windows-hardware/drivers/display/user-mode-work-submission).

## -see-also

[**D3DKMT_DESTROY_DOORBELL**](ns-d3dkmthk-d3dkmt_destroy_doorbell.md)

[**D3DKMTCreateDoorbell**](nf-d3dkmthk-d3dkmtcreatedoorbell.md)
