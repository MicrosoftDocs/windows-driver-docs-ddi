---
UID: NS:d3dkmddi._DXGKARGCB_RELEASEHANDLEDATA
tech.root: display
title: DXGKARGCB_RELEASEHANDLEDATA
ms.date: 10/13/2021
targetos: Windows
description: Learn more about the DXGKARGCB_RELEASEHANDLEDATA structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARGCB_RELEASEHANDLEDATA
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_RELEASEHANDLEDATA
 - DXGKARGCB_RELEASEHANDLEDATA
f1_keywords:
 - _DXGKARGCB_RELEASEHANDLEDATA
 - d3dkmddi/_DXGKARGCB_RELEASEHANDLEDATA
 - DXGKARGCB_RELEASEHANDLEDATA
 - d3dkmddi/DXGKARGCB_RELEASEHANDLEDATA
dev_langs:
 - c++
---

## -description

The **DXGKARGCB_RELEASEHANDLEDATA** structure contains the information used by the [**DXGKCB_RELEASEHANDLEDATA**](nc-d3dkmddi-dxgkcb_releasehandledata.md) callback function to release a reference to an allocation.

## -struct-fields

### -field ReleaseHandle

[in] The release handle obtained from a prior call to [**DXGKCB_ACQUIREHANDLEDATA**](nc-d3dkmddi-dxgkcb_acquirehandledata.md).

### -field Type

[in] A [**DXGK_HANDLE_TYPE**](ne-d3dkmddi-dxgk_handle_type.md) value that identifies the handle type of the allocation.

## -see-also

[**DXGK_HANDLE_TYPE**](ne-d3dkmddi-dxgk_handle_type.md)

[**DXGKCB_RELEASEHANDLEDATA**](nc-d3dkmddi-dxgkcb_releasehandledata.md)
