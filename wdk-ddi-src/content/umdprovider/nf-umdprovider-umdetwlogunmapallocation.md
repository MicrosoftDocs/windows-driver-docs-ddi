---
UID: NF:umdprovider.UMDEtwLogUnmapAllocation
title: UMDEtwLogUnmapAllocation function (umdprovider.h)
description: Indicates that a Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) memory allocation, or a portion of the allocation, is no longer being used. Call this function whether or not the allocation is being destroyed.
old-location: display\umdetwlogunmapallocation.htm
tech.root: display
ms.assetid: 36c204fb-638d-44d2-8379-a5bd79e4167a
ms.date: 05/10/2018
keywords: ["UMDEtwLogUnmapAllocation function"]
ms.keywords: UMDEtwLogUnmapAllocation, UMDEtwLogUnmapAllocation function [Display Devices], display.umdetwlogunmapallocation, umdprovider/UMDEtwLogUnmapAllocation
req.header: umdprovider.h
req.include-header: Umdprovider.h
req.target-type: Desktop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UMDEtwLogUnmapAllocation
 - umdprovider/UMDEtwLogUnmapAllocation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - umdprovider.h
api_name:
 - UMDEtwLogUnmapAllocation
---

# UMDEtwLogUnmapAllocation function


## -description

Indicates that a Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) memory allocation, or a portion of the allocation, is no longer being used. Call this function whether or not the allocation is being destroyed.

## -parameters

### -param hD3DAllocation

A handle to the Direct3D allocation.

 For Direct3D 10 user-mode drivers, the handle will be the value of the <i>hResource</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function. For Direct3D 9 user-mode drivers, the handle will be the value of the <i>pResource</i> parameter that the driver returns in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a> function.

The driver can set this value to <b>NULL</b> if it uses allocations internally.

### -param hDxgAllocation

A handle to the DirectX graphics kernel subsystem (Dxgkrnl.sys) allocation that the Direct3D allocation is mapped to.

### -param Offset

The starting address, in bytes, of the Direct3D allocation within the Dxgkrnl allocation.

### -param Size

The size, in bytes, of the Direct3D allocation within the Dxgkrnl allocation.

### -param Usage

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/umdprovider/ns-umdprovider-_umdetw_allocation_usage">UMDETW_ALLOCATION_USAGE</a> structure that indicates the reason for this mapping.

### -param Semantic

If the allocation is used internally by the user-mode driver, this is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/umdprovider/ne-umdprovider-_umdetw_allocation_semantic">UMDETW_ALLOCATION_SEMANTIC</a> structure that indicates what the allocation is used for.

## -remarks

When called, this function logs an event that describes which API resource the allocation is, or was, being used for. If no API resource was associated with the allocation, the function logs an event that describes the purpose that the driver indicated for this allocation.

The user-mode display driver must completely account for the video memory it allocates, so it must call this function to log an event every time the allocation changes.

The driver should pass the same parameters values to <b>UMDEtwLogUnmapAllocation</b> as it did to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/umdprovider/nf-umdprovider-umdetwlogmapallocation">UMDEtwLogMapAllocation</a>.

<b>UMDEtwLogUnmapAllocation</b> is defined inline in Umdprovider.h as:

```cpp
FORCEINLINE void LogMapAllocation(BOOLEAN Enter,
                    ULONGLONG hD3DAllocation,
                    ULONGLONG hDxgAllocation,
                    ULONGLONG Offset,
                    ULONGLONG Size,
                    UMDETW_ALLOCATION_USAGE Usage,
                    UMDETW_ALLOCATION_SEMANTIC Semantic)
{
    if (Enabled)
    {   
        EVENT_DATA_DESCRIPTOR Descriptors[6];
        
        // Create a description of the event
        EventDataDescCreate(&Descriptors[0], &hD3DAllocation, 8);
        EventDataDescCreate(&Descriptors[1], &hDxgAllocation, 8);
        EventDataDescCreate(&Descriptors[2], &Offset, 8);
        EventDataDescCreate(&Descriptors[3], &Size, 8);
        EventDataDescCreate(&Descriptors[4], &Usage, 4);
        EventDataDescCreate(&Descriptors[5], &Semantic, 4);

        // Log the event
        EventWrite(
            RegHandle,
            Enter ? (InRundown ? &RundownAllocationEvent : &MapAllocationEvent) : &UnmapAllocationEvent,
            sizeof(Descriptors) / sizeof(Descriptors[0]),
            Descriptors
        );
    }
}

FORCEINLINE void UMDEtwLogUnmapAllocation(ULONGLONG hD3DAllocation,
                              ULONGLONG hDxgAllocation,
                              ULONGLONG Offset,
                              ULONGLONG Size,
                              UMDETW_ALLOCATION_USAGE Usage,
                              UMDETW_ALLOCATION_SEMANTIC Semantic)
{
    LogMapAllocation(FALSE,
                     hD3DAllocation,
                     hDxgAllocation,
                     Offset,
                     Size,
                     Usage,
                     Semantic);
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/umdprovider/ne-umdprovider-_umdetw_allocation_semantic">UMDETW_ALLOCATION_SEMANTIC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/umdprovider/ns-umdprovider-_umdetw_allocation_usage">UMDETW_ALLOCATION_USAGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/umdprovider/nf-umdprovider-umdetwlogmapallocation">UMDEtwLogMapAllocation</a>

