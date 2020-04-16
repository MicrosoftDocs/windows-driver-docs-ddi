---
UID: NF:d3dkmthk.D3DKMTLock
title: D3DKMTLock function (d3dkmthk.h)
description: The D3DKMTLock function locks an entire allocation or specific pages within an allocation.
old-location: display\d3dkmtlock.htm
ms.assetid: d64abd43-edf2-465a-8d99-8fdce1fcd25f
ms.date: 05/10/2018
keywords: ["D3DKMTLock function"]
ms.keywords: D3DKMTLock, D3DKMTLock function [Display Devices], OpenGL_Functions_ca085861-b8a0-434a-843d-9b8052376df5.xml, d3dkmthk/D3DKMTLock, display.d3dkmtlock
f1_keywords:
 - "d3dkmthk/D3DKMTLock"
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
- D3DKMTLock
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTLock function

## -description

The <b>D3DKMTLock</b> function locks an entire allocation or specific pages within an allocation.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_lock">D3DKMT_LOCK</a> structure that describes parameters for locking an allocation.

## -returns

<b>D3DKMTLock</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The allocation was successfully locked.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display device was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
|STATUS_GRAPHICS_ALLOCATION_BUSY|The allocation was currently in use and could not be locked.|
|STATUS_GRAPHICS_TOO_MANY_REFERENCES|Too many references were pending on the allocation.|
|STATUS_GRAPHICS_CANT_EVICT_PINNED_ALLOCATION|The allocation could not be locked because a deswizzling aperture was unavailable and because the allocation is pinned and could not be evicted.|

This function might also return other NTSTATUS values.

## -remarks

The <b>D3DKMTLock</b> function is called to access system memory allocations and video memory allocations.

#### Examples

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTLock</b> to lock an entire allocation.

```cpp
VOID* LockEntireAllocation(D3DKMT_HANDLE hDevice, D3DKMT_HANDLE hAllocation, UINT PrivateData)
{
    D3DKMT_LOCK LockAllocation = {0};

    LockAllocation.hDevice = hDevice;
    LockAllocation.hAllocation = LockData.hAllocation;
    LockAllocation.Flags.LockEntire = TRUE;
    LockAllocation.PrivateDriverData = PrivateData;
    LockAllocation.NumPages = 0;
    LockAllocation.pPages = NULL;
 
    if (NT_SUCCESS((*pfnKTLock)(&LockAllocation))) {
        return LockAllocation.pData;
    }
    return NULL;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_lock">D3DKMT_LOCK</a>
 

 

