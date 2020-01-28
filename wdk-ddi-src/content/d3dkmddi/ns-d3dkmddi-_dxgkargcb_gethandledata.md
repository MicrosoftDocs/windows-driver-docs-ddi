---
UID: NS:d3dkmddi._DXGKARGCB_GETHANDLEDATA
title: _DXGKARGCB_GETHANDLEDATA (d3dkmddi.h)
description: The DXGKARGCB_GETHANDLEDATA structure describes a handle to private data.
old-location: display\dxgkargcb_gethandledata.htm
ms.assetid: 22a03f0b-71c3-4942-b5da-ca588e17d346
ms.date: 05/10/2018
ms.keywords: DXGKARGCB_GETHANDLEDATA, DXGKARGCB_GETHANDLEDATA structure [Display Devices], DmStructs_6ae35474-ffde-4e60-8324-b6266cc54fd8.xml, _DXGKARGCB_GETHANDLEDATA, d3dkmddi/DXGKARGCB_GETHANDLEDATA, display.dxgkargcb_gethandledata
f1_keywords:
 - "d3dkmddi/DXGKARGCB_GETHANDLEDATA"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGKARGCB_GETHANDLEDATA
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARGCB_GETHANDLEDATA
---

# _DXGKARGCB_GETHANDLEDATA structure


## -description


The DXGKARGCB_GETHANDLEDATA structure describes a handle to private data.


## -struct-fields




### -field hObject

[in] A handle to the private data. This handle is the kernel-mode handle that the Microsoft DirectX graphics kernel subsystem (which is part of <i>Dxgkrnl.sys</i>) assigned for the private data.


### -field Type

[in] A DXGK_HANDLE_TYPE-typed value that indicates the type of handle to retrieve data about. This member can be one of the following values:

| **Value** | **Meaning** |
|:--|:--|
| DXGK_HANDLE_ALLOCATION (1) | The allocations belong to a resource. | 
| DXGK_HANDLE_RESOURCE (2) | The [DxgkDdiCreateAllocation](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation)  call is the result of the creation of the primary surface. |


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkcb_gethandledataflags">DXGKCB_GETHANDLEDATAFLAGS</a> structure that indicates if allocations belong to a resource.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkcb_gethandledataflags">DXGKCB_GETHANDLEDATAFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_gethandledata">DxgkCbGetHandleData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>
 

 

