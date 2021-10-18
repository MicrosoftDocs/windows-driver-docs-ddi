---
UID: NS:d3dkmddi._DXGK_ADL_FLAGS
tech.root: display
title: DXGK_ADL_FLAGS
ms.date: 05/13/2021
targetos: Windows
description: The DXGK_ADL_FLAGS structure specifies the flag(s) that apply to an address descriptor list (ADL).
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
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: DXGK_ADL_FLAGS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_ADL_FLAGS
 - DXGK_ADL_FLAGS
f1_keywords:
 - _DXGK_ADL_FLAGS
 - d3dkmddi/_DXGK_ADL_FLAGS
 - DXGK_ADL_FLAGS
 - d3dkmddi/DXGK_ADL_FLAGS
dev_langs:
 - c++
---

## -description

The **DXGK_ADL_FLAGS** structure specifies the flag(s) that apply to an [address descriptor list (ADL)](ns-d3dkmddi-dxgk_adl.md).

## -struct-fields

### -field Contiguous

Indicates that the pages in the ADL are contiguous.

### -field Reserved

Reserved for future use.

### -field Value

Another method to access the bits.

## -see-also

[**DXGK_ADL**](ns-d3dkmddi-dxgk_adl.md)
