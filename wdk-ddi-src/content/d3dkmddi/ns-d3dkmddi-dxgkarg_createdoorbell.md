---
UID: NS:d3dkmddi._DXGKARG_CREATEDOORBELL
tech.root: display
title: DXGKARG_CREATEDOORBELL
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the DXGKARG_CREATEDOORBELL structure.
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
req.typenames: DXGKARG_CREATEDOORBELL
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
 - _DXGKARG_CREATEDOORBELL
 - DXGKARG_CREATEDOORBELL
f1_keywords:
 - _DXGKARG_CREATEDOORBELL
 - d3dkmddi/_DXGKARG_CREATEDOORBELL
 - DXGKARG_CREATEDOORBELL
 - d3dkmddi/DXGKARG_CREATEDOORBELL
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_CREATEDOORBELL
---

## -description

The **DXGKARG_CREATEDOORBELL** structure contains parameters for KMD's [**DxgkDdiCreateDoorbell**](nc-d3dkmddi-dxgkddi_createdoorbell.md) callback function.

## -struct-fields

### -field hHwQueue

[in] Handle to a KMD hardware queue object, which was created in a previous call to [**D3DKMTCreateHwQueue**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreatehwqueue.md).

### -field hDoorbell

[in/out] As input, contains the OS's handle to the doorbell. KMD can store the input handle in its tracking structures. As output, **hDoorbell** contains KMD's kernel-mode handle to the doorbell.

### -field PrivateDriverDataSize

[in] Size, in bytes, of the driver's private data that is associated with the doorbell.

### -field PrivateDriverData

[in/out] Pointer to the driver's private data that is associated with the doorbell.

### -field hRingBuffer

[in] Handle to the ring buffer allocation [previously created](../d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation.md) by UMD. This allocation is GPU visible and already resident. The [**ResizeRingBufferOperation**](ns-d3dkmddi-dxgkarg_createdoorbell_flags.md) flag is a hint from UMD to KMD that a doorbell is being recreated for this hardware queue with a new, resized ring buffer.

### -field hRingBufferControl

[in] KMD handle to a ring buffer control allocation [previously created](../d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation.md) by UMD. UMD and KMD can use this allocation as a control area to store ring buffer read/write pointer locations if required. The allocation must be GPU visible and already resident.

### -field Flags

A bit field of [**DXGKARG_CREATEDOORBELL_FLAGS**](ns-d3dkmddi-dxgkarg_createdoorbell_flags.md) values specifying the doorbell creation flags.

## -see-also

[**D3DKMTCreateAllocation**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation.md)

[**DXGKARG_CREATEDOORBELL_FLAGS**](ns-d3dkmddi-dxgkarg_createdoorbell_flags.md)

[**DxgkDdiCreateDoorbell**](nc-d3dkmddi-dxgkddi_createdoorbell.md)
