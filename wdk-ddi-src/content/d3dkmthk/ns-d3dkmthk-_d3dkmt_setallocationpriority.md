---
UID: NS:d3dkmthk._D3DKMT_SETALLOCATIONPRIORITY
title: _D3DKMT_SETALLOCATIONPRIORITY (d3dkmthk.h)
description: The D3DKMT_SETALLOCATIONPRIORITY structure describes the priority level to set a resource or list of allocations to.
old-location: display\d3dkmt_setallocationpriority.htm
ms.assetid: 3135b9fa-17f0-410a-b563-57fd1548f495
ms.date: 05/10/2018
keywords: ["_D3DKMT_SETALLOCATIONPRIORITY structure"]
ms.keywords: D3DKMT_SETALLOCATIONPRIORITY, D3DKMT_SETALLOCATIONPRIORITY structure [Display Devices], OpenGL_Structs_9afc3b7a-fcd5-4fb4-bfb9-5e752b225a4e.xml, _D3DKMT_SETALLOCATIONPRIORITY, d3dkmthk/D3DKMT_SETALLOCATIONPRIORITY, display.d3dkmt_setallocationpriority
f1_keywords:
 - "d3dkmthk/D3DKMT_SETALLOCATIONPRIORITY"
 - "D3DKMT_SETALLOCATIONPRIORITY"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
- d3dkmthk.h
api_name:
- D3DKMT_SETALLOCATIONPRIORITY
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SETALLOCATIONPRIORITY
---

# _D3DKMT_SETALLOCATIONPRIORITY structure


## -description


The D3DKMT_SETALLOCATIONPRIORITY structure describes the priority level to set a resource or list of allocations to. 


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device that the resource or list of allocations are associated with.


### -field hResource

[in] A handle to a resource whose priority must be set. If the OpenGL ICD uses the array that <b>phAllocationList</b> specifies to set the priority for the list of allocations, it sets <b>hResource</b> to <b>NULL</b>. If the OpenGL ICD sets <b>hResource</b> to a non-<b>NULL</b> value, it must set the <b>AllocationCount</b> member to zero and <b>phAllocationList</b> to <b>NULL</b>. 

If <b>hResource</b> is non-<b>NULL</b>, all of the allocations that belong to the resource are set to the priority that is specified by the first element in the array that <b>pPriorities</b> points to. 


### -field phAllocationList

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations. If the OpenGL ICD sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, it must set <b>phAllocationList</b> to <b>NULL</b>. 


### -field AllocationCount

[in] The number of allocations in the array that <b>phAllocationList</b> specifies. If the OpenGL ICD sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, it must set <b>AllocationCount</b> to zero.


### -field pPriorities

[in] A pointer to an array of priority levels. If the <b>hResource</b> member is non-<b>NULL</b>, the array must contain a single element. If <b>hResource</b> is <b>NULL</b>, the number of elements in the array is specified by the <b>AllocationCount</b> member, and each allocation in the array that <b>phAllocationList</b> specifies is set to the priority level of the corresponding element in <b>pPriorities</b>.

Each element in <b>pPriorities</b> can be set to one of the following values.

|Enumerator|Meaning|
|--- |--- |
|D3DDDI_ALLOCATIONPRIORITY_MINIMUM (0x28000000)|Minimum priority|
|D3DDDI_ALLOCATIONPRIORITY_LOW (0x50000000)|Low priority|
|D3DDDI_ALLOCATIONPRIORITY_NORMAL (0x78000000)|Normal priority|
|D3DDDI_ALLOCATIONPRIORITY_HIGH (0xa0000000)|High priority|
|D3DDDI_ALLOCATIONPRIORITY_MAXIMUM (0xc8000000)|Maximum priority|

For more information about the meanings of the preceding values, see the Remarks section of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setprioritycb">pfnSetPriorityCb</a> function. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetallocationpriority">D3DKMTSetAllocationPriority</a>
 

 

