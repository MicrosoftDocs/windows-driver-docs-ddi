---
UID: NS:d3dkmthk._D3DKMT_DESTROY_DOORBELL
tech.root: display
title: D3DKMT_DESTROY_DOORBELL
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the D3DKMT_DESTROY_DOORBELL structure.
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
req.typenames: D3DKMT_DESTROY_DOORBELL
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
 - _D3DKMT_DESTROY_DOORBELL
 - D3DKMT_DESTROY_DOORBELL
f1_keywords:
 - _D3DKMT_DESTROY_DOORBELL
 - d3dkmthk/_D3DKMT_DESTROY_DOORBELL
 - D3DKMT_DESTROY_DOORBELL
 - d3dkmthk/D3DKMT_DESTROY_DOORBELL
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DKMT_DESTROY_DOORBELL
---

## -description

The **D3DKMT_DESTROY_DOORBELL** structure identifies the doorbell object that [**D3DKMTDestroyDoorbell**](nf-d3dkmthk-d3dkmtdestroydoorbell.md) should destroy.

## -struct-fields

### -field hHwQueue

[in] User-mode driver handle to the hardware queue whose doorbell is to be destroyed. This handle was created in a previous call to  [**D3DKMTCreateHwQueue**](nf-d3dkmthk-d3dkmtcreatehwqueue.md).

## -see-also

[**D3DKMTCreateDoorbell**](nf-d3dkmthk-d3dkmtcreatedoorbell.md)

 [**D3DKMTCreateHwQueue**](nf-d3dkmthk-d3dkmtcreatehwqueue.md)

[**D3DKMTDestroyDoorbell**](nf-d3dkmthk-d3dkmtdestroydoorbell.md)
