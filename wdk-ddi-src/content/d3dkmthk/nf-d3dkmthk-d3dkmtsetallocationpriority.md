---
UID: NF:d3dkmthk.D3DKMTSetAllocationPriority
title: D3DKMTSetAllocationPriority function (d3dkmthk.h)
description: The D3DKMTSetAllocationPriority function sets the priority level of a resource or list of allocations.
old-location: display\d3dkmtsetallocationpriority.htm
ms.assetid: d5ad6288-6123-4665-a48e-bbae856cc160
ms.date: 05/10/2018
ms.keywords: D3DKMTSetAllocationPriority, D3DKMTSetAllocationPriority function [Display Devices], OpenGL_Functions_dc77467a-7ec3-4be9-96cd-8bedb5beb948.xml, d3dkmthk/D3DKMTSetAllocationPriority, display.d3dkmtsetallocationpriority
ms.topic: function
f1_keywords:
 - "d3dkmthk/D3DKMTSetAllocationPriority"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Gdi32.dll
- API-MS-Win-dx-d3dkmt-l1-1-0.dll
- API-MS-Win-dx-d3dkmt-l1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTSetAllocationPriority
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTSetAllocationPriority function

## -description

The <b>D3DKMTSetAllocationPriority</b> function sets the priority level of a resource or list of allocations.

## -parameters

### -param D3DKMT_SETALLOCATIONPRIORITY

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setallocationpriority">D3DKMT_SETALLOCATIONPRIORITY</a> structure that contains information for setting the priority level of a resource or list of allocations.

## -returns

<b>D3DKMTSetAllocationPriority</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|Priority level for allocations was successfully set.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display device was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other NTSTATUS values.

## -remarks

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTSetAllocationPriority</b> to set the priority level of a resource (and therefore all of the allocations that are associated with the resource).

```cpp
VOID SetResourcePriority(D3DKMT_HANDLE hDevice, D3DKMT_HANDLE hResource, UINT uiPriority)
{
    D3DKMT_SETALLOCATIONPRIORITY SetAllocationPriorityData;

    SetAllocationPriorityData.hDevice = hDevice;
    SetAllocationPriorityData.hResource = hResource;
    SetAllocationPriorityData.phAllocationList = NULL;
    SetAllocationPriorityData.AllocationCount = 0;
    SetAllocationPriorityData.Priorities = &uiPriority;    

    (*pfnKTSetAllocationPriority)(&SetAllocationPriorityData);
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setallocationpriority">D3DKMT_SETALLOCATIONPRIORITY</a>
