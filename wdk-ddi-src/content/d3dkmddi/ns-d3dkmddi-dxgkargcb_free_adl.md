---
UID: NS:d3dkmddi._DXGKARGCB_FREE_ADL
tech.root: display
title: DXGKARGCB_FREE_ADL
ms.date: 10/13/2021
targetos: Windows
description: DXGKARGCB_FREE_ADL contains the information used by the DxgkCbFreeAdl callback function to destroy an address descriptor list (ADL).
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022 (WDDM 2.9)
req.target-type: 
req.typenames: DXGKARGCB_FREE_ADL
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_FREE_ADL
 - DXGKARGCB_FREE_ADL
f1_keywords:
 - _DXGKARGCB_FREE_ADL
 - d3dkmddi/_DXGKARGCB_FREE_ADL
 - DXGKARGCB_FREE_ADL
 - d3dkmddi/DXGKARGCB_FREE_ADL
dev_langs:
 - c++
---

## -description

**DXGKARGCB_FREE_ADL** contains the information used by the [**DXGKCB_FREEADL**](nc-d3dkmddi-dxgkcb_freeadl.md) callback function to destroy an address descriptor list (ADL).

## -struct-fields

### -field hAdapterMemoryObject

[in] The adapter memory object that was used to create the ADL.

### -field pAdl

[in] Pointer to the [**DXGK_ADL**](ns-d3dkmddi-dxgk_adl.md) object that is being freed.

## -see-also

[**DXGK_ADL**](ns-d3dkmddi-dxgk_adl.md)

[**DXGKCB_ALLOCATEADL**](nc-d3dkmddi-dxgkcb_allocateadl.md)

[**DXGKCB_FREEADL**](nc-d3dkmddi-dxgkcb_freeadl.md)
