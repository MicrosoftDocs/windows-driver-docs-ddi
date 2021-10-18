---
UID: NS:d3dkmddi._DXGKARGCB_ENUMHANDLECHILDREN
title: DXGKARGCB_ENUMHANDLECHILDREN (d3dkmddi.h)
description: The DXGKARGCB_ENUMHANDLECHILDREN structure describes a parent resource and the index of one of its child allocations.
old-location: display\dxgkargcb_enumhandlechildren.htm
ms.date: 10/13/2021
keywords: ["DXGKARGCB_ENUMHANDLECHILDREN structure"]
ms.keywords: DXGKARGCB_ENUMHANDLECHILDREN, DXGKARGCB_ENUMHANDLECHILDREN structure [Display Devices], DmStructs_b02ec187-32ca-41ff-bfc3-03d058872b5d.xml, _DXGKARGCB_ENUMHANDLECHILDREN, d3dkmddi/DXGKARGCB_ENUMHANDLECHILDREN, display.dxgkargcb_enumhandlechildren
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
 - _DXGKARGCB_ENUMHANDLECHILDREN
 - DXGKARGCB_ENUMHANDLECHILDREN
---

# DXGKARGCB_ENUMHANDLECHILDREN structure

## -description

The **DXGKARGCB_ENUMHANDLECHILDREN** structure contains the arguments used in the [**DXGKCB_ENUMHANDLECHILDREN**](nc-d3dkmddi-dxgkcb_enumhandlechildren.md) callback function, to enumerate allocations associated with a parent resource.

## -struct-fields

### -field hObject

[in] A handle to the parent resource of a group of child allocations. This handle is the kernel-mode handle that the DirectX graphics kernel subsystem (part of *Dxgkrnl.sys*) assigned for the parent resource.

### -field Index

[in] The index into the array of child allocations that belongs to the resource that **hObject** specifies.

## -see-also

[**DXGKCB_ENUMHANDLECHILDREN**](nc-d3dkmddi-dxgkcb_enumhandlechildren.md)
