---
UID: NS:d3dkmthk._D3DKMT_OUTPUTDUPLPRESENT
title: _D3DKMT_OUTPUTDUPLPRESENT (d3dkmthk.h)
description: Describes a Desktop Duplication API swapchain present operation.
old-location: display\d3dkmt_outputduplpresent.htm
ms.assetid: 1820e11c-0888-4d6d-aa75-b895c863eb43
ms.date: 05/10/2018
ms.keywords: D3DKMT_OUTPUTDUPLPRESENT, D3DKMT_OUTPUTDUPLPRESENT structure [Display Devices], _D3DKMT_OUTPUTDUPLPRESENT, d3dkmthk/D3DKMT_OUTPUTDUPLPRESENT, display.d3dkmt_outputduplpresent
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_OUTPUTDUPLPRESENT"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3dkmthk.h
api_name:
- D3DKMT_OUTPUTDUPLPRESENT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_OUTPUTDUPLPRESENT
---

# _D3DKMT_OUTPUTDUPLPRESENT structure


## -description


Describes a <a href="https://docs.microsoft.com/windows/desktop/direct3ddxgi/desktop-dup-api">Desktop Duplication API</a> swapchain present operation.


## -struct-fields




### -field hContext

[in] A D3DKMT_HANDLE data type that represents a handle to the context.


### -field hSource

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the source allocation to be displayed.


### -field VidPnSourceId

The zero-based identification number of a video present source in a path of a video present network (VidPN) topology.


### -field BroadcastContextCount

[in] Specifies the number of contexts.


### -field BroadcastContext

[in] A D3DKMT_HANDLE data type that represents the broadcast context.


### -field PresentRegions

[in] Dirty and move regions, of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_present_rgns">D3DKMT_PRESENT_RGNS</a>.


### -field Flags

[in] A bitwise-OR combination of values from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_outputduplpresentflags">D3DKMT_OUTPUTDUPLPRESENTFLAGS</a> enumeration that describe options for the present operation.


### -field hIndirectContext

The indirect adapter context for redirecting through the DoD present path. This member is valid only if the PresentIndirect flag is set.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_outputduplpresentflags">D3DKMT_OUTPUTDUPLPRESENTFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_present_rgns">D3DKMT_PRESENT_RGNS</a>
 

 

