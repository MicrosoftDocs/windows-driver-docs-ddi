---
UID: NS:d3dkmthk._D3DKMT_CREATE_DOORBELL_FLAGS
tech.root: display
title: D3DKMT_CREATE_DOORBELL_FLAGS
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the D3DKMT_CREATE_DOORBELL_FLAGS structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_FUTURE
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMT_CREATE_DOORBELL_FLAGS
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
 - _D3DKMT_CREATE_DOORBELL_FLAGS
 - D3DKMT_CREATE_DOORBELL_FLAGS
f1_keywords:
 - _D3DKMT_CREATE_DOORBELL_FLAGS
 - d3dkmthk/_D3DKMT_CREATE_DOORBELL_FLAGS
 - D3DKMT_CREATE_DOORBELL_FLAGS
 - d3dkmthk/D3DKMT_CREATE_DOORBELL_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DKMT_CREATE_DOORBELL_FLAGS
---

## -description

The **D3DKMT_CREATE_DOORBELL_FLAGS** structure specifies doorbell creation flags.

## -struct-fields

### -field RequireSecondaryCpuVA

UMD sets this flag on hardware that implements a secondary doorbell location. For such devices, the OS reserves another CPU virtual address for this doorbell. This address remains constant over the lifetime of the doorbell, even if the underlying physical doorbell gets disconnected.

### -field ResizeRingBufferOperation

Indication from UMD to KMD that a doorbell is being recreated for this hardware queue with a new, resized [**hRingBuffer**](nf-d3dkmthk-d3dkmtcreatedoorbell.md) ring buffer.

### -field Reserved

Reserved; set to zero.

### -field Value

An alternative way to access the structure members.

## -see-also

[**D3DKMT_CREATE_DOORBELL**](nf-d3dkmthk-d3dkmtcreatedoorbell.md)

[**D3DKMTCreateDoorbell**](nf-d3dkmthk-d3dkmtcreatedoorbell.md)
