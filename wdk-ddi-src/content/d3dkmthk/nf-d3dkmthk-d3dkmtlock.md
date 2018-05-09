---
UID: NF:d3dkmthk.D3DKMTLock
title: D3DKMTLock function
author: windows-driver-content
description: The D3DKMTLock function locks an entire allocation or specific pages within an allocation.
old-location: display\d3dkmtlock.htm
old-project: display
ms.assetid: d64abd43-edf2-465a-8d99-8fdce1fcd25f
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTLock, D3DKMTLock function [Display Devices], OpenGL_Functions_ca085861-b8a0-434a-843d-9b8052376df5.xml, d3dkmthk/D3DKMTLock, display.d3dkmtlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTLock function


## -description


The <b>D3DKMTLock</b> function locks an entire allocation or specific pages within an allocation.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548094">D3DKMT_LOCK</a> structure that describes parameters for locking an allocation.


## -returns



<b>D3DKMTLock</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The allocation was successfully locked.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display device was reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_ALLOCATION_BUSY</b></dt>
</dl>
</td>
<td width="60%">
The allocation was currently in use and could not be locked.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_TOO_MANY_REFERENCES</b></dt>
</dl>
</td>
<td width="60%">
Too many references were pending on the allocation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_CANT_EVICT_PINNED_ALLOCATION</b></dt>
</dl>
</td>
<td width="60%">
The allocation could not be locked because a deswizzling aperture was unavailable and because the allocation is pinned and could not be evicted.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -remarks



The <b>D3DKMTLock</b> function is called to access system memory allocations and video memory allocations.


#### Examples

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTLock</b> to lock an entire allocation.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID* LockEntireAllocation(D3DKMT_HANDLE hDevice, D3DKMT_HANDLE hAllocation, UINT PrivateData)
{
    D3DKMT_LOCK LockAllocation = {0};

    LockAllocation.hDevice = hDevice;
    LockAllocation.hAllocation = LockData.hAllocation;
    LockAllocation.Flags.LockEntire = TRUE;
    LockAllocation.PrivateDriverData = PrivateData;
    LockAllocation.NumPages = 0;
    LockAllocation.pPages = NULL;
 
    if (NT_SUCCESS((*pfnKTLock)(&amp;LockAllocation))) {
        return LockAllocation.pData;
    }
    return NULL;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548094">D3DKMT_LOCK</a>
 

 

