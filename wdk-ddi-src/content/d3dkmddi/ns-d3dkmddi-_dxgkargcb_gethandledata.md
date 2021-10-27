---
UID: NS:d3dkmddi._DXGKARGCB_GETHANDLEDATA
title: DXGKARGCB_GETHANDLEDATA (d3dkmddi.h)
description: The DXGKARGCB_GETHANDLEDATA structure describes a handle to private data.
old-location: display\dxgkargcb_gethandledata.htm
ms.date: 10/13/2021
keywords: ["DXGKARGCB_GETHANDLEDATA structure"]
ms.keywords: DXGKARGCB_GETHANDLEDATA, DXGKARGCB_GETHANDLEDATA structure [Display Devices], DmStructs_6ae35474-ffde-4e60-8324-b6266cc54fd8.xml, _DXGKARGCB_GETHANDLEDATA, d3dkmddi/DXGKARGCB_GETHANDLEDATA, display.dxgkargcb_gethandledata
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: DXGKARGCB_GETHANDLEDATA
f1_keywords:
 - _DXGKARGCB_GETHANDLEDATA
 - d3dkmddi/_DXGKARGCB_GETHANDLEDATA
 - DXGKARGCB_GETHANDLEDATA
 - d3dkmddi/DXGKARGCB_GETHANDLEDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_GETHANDLEDATA
 - DXGKARGCB_GETHANDLEDATA
---

# DXGKARGCB_GETHANDLEDATA structure

## -description

The **DXGKARGCB_GETHANDLEDATA** structure contains the arguments used in the [**DXGKCB_GETHANDLEDATA**](nc-d3dkmddi-dxgkcb_getcaptureaddress.md) callback function.

## -struct-fields

### -field hObject [in]

A handle to the private data. This handle is the kernel-mode handle that the DirectX graphics kernel subsystem (part of *Dxgkrnl.sys*) assigned for the private data.

### -field Type [in]

A [**DXGK_HANDLE_TYPE**](ne-d3dkmddi-dxgk_handle_type.md) value that indicates the type of handle to retrieve data about.

### -field Flags [in]

A [**DXGKCB_GETHANDLEDATAFLAGS**](ns-d3dkmddi-_dxgkcb_gethandledataflags.md) structure that indicates if allocations belong to a resource.

## -see-also

[**DXGKCB_GETHANDLEDATAFLAGS**](ns-d3dkmddi-_dxgkcb_gethandledataflags.md)

[**DXGKCB_GETHANDLEDATA**](nc-d3dkmddi-dxgkcb_gethandledata.md)

[**DxgkDdiCreateAllocation**](nc-d3dkmddi-dxgkddi_createallocation.md)
