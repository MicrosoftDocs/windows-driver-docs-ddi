---
UID: NS:d3dkmddi._DXGKARGCB_ENUMHANDLECHILDREN
title: _DXGKARGCB_ENUMHANDLECHILDREN (d3dkmddi.h)
description: The DXGKARGCB_ENUMHANDLECHILDREN structure describes a parent resource and the index of one of its child allocations.
old-location: display\dxgkargcb_enumhandlechildren.htm
ms.assetid: da97b175-a24c-406d-9747-c84122781f79
ms.date: 05/10/2018
keywords: ["DXGKARGCB_ENUMHANDLECHILDREN structure"]
ms.keywords: DXGKARGCB_ENUMHANDLECHILDREN, DXGKARGCB_ENUMHANDLECHILDREN structure [Display Devices], DmStructs_b02ec187-32ca-41ff-bfc3-03d058872b5d.xml, _DXGKARGCB_ENUMHANDLECHILDREN, d3dkmddi/DXGKARGCB_ENUMHANDLECHILDREN, display.dxgkargcb_enumhandlechildren
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
targetos: Windows
tech.root: display
req.typenames: DXGKARGCB_ENUMHANDLECHILDREN
f1_keywords:
 - _DXGKARGCB_ENUMHANDLECHILDREN
 - d3dkmddi/_DXGKARGCB_ENUMHANDLECHILDREN
 - DXGKARGCB_ENUMHANDLECHILDREN
 - d3dkmddi/DXGKARGCB_ENUMHANDLECHILDREN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKARGCB_ENUMHANDLECHILDREN
---

# _DXGKARGCB_ENUMHANDLECHILDREN structure


## -description

The DXGKARGCB_ENUMHANDLECHILDREN structure describes a parent resource and the index of one of its child allocations.

## -struct-fields

### -field hObject

[in] A handle to the parent resource of a group of child allocations. This handle is the kernel-mode handle that the Microsoft DirectX graphics kernel subsystem (which is part of <i>Dxgkrnl.sys</i>) assigned for the parent resource.

### -field Index

[in] The index into the array of allocations that belongs to the resource that <b>hObject</b> specifies.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_enumhandlechildren">DxgkCbEnumHandleChildren</a>

