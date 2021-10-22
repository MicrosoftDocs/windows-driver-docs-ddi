---
UID: NE:d3dkmddi._DXGK_HANDLE_TYPE
tech.root: display
title: DXGK_HANDLE_TYPE
ms.date: 10/13/2021
targetos: Windows
description: Learn more about the DXGK_HANDLE_TYPE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_HANDLE_TYPE
 - DXGK_HANDLE_TYPE
f1_keywords:
 - _DXGK_HANDLE_TYPE
 - d3dkmddi/_DXGK_HANDLE_TYPE
 - DXGK_HANDLE_TYPE
 - d3dkmddi/DXGK_HANDLE_TYPE
dev_langs:
 - c++
---

## -description

**DXGK_HANDLE_TYPE** identifies the handle type of an allocation.

## -enum-fields

### -field DXGK_HANDLE_ALLOCATION

The handle is the result of the creation of a primary surface.

### -field DXGK_HANDLE_RESOURCE

The handle is for an allocation that belongs to a resource.

## -see-also

[**DXGKARGCB_RELEASEHANDLEDATA**](ns-d3dkmddi-dxgkargcb_releasehandledata.md)

[**DXGKARGCB_GETHANDLEDATA**](nc-d3dkmddi-dxgkcb_gethandledata.md)

[**DXGKCB_RELEASEHANDLEDATA**](nc-d3dkmddi-dxgkcb_releasehandledata.md)

[**DxgkDdiCreateAllocation**](nc-d3dkmddi-dxgkddi_createallocation.md)
