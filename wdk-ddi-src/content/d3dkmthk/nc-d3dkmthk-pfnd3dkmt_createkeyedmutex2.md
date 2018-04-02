---
UID: NC:d3dkmthk.PFND3DKMT_CREATEKEYEDMUTEX2
title: PFND3DKMT_CREATEKEYEDMUTEX2
author: windows-driver-content
description: Creates a keyed mutex object that includes private data.
old-location: display\d3dkmtcreatekeyedmutex2.htm
old-project: display
ms.assetid: fedd7aa0-366c-4083-b6d2-692332813b3f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTCreateKeyedMutex2, D3DKMTCreateKeyedMutex2 callback function [Display Devices], PFND3DKMT_CREATEKEYEDMUTEX2, d3dkmthk/D3DKMTCreateKeyedMutex2, display.d3dkmtcreatekeyedmutex2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMTCreateKeyedMutex2
product: Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---

# PFND3DKMT_CREATEKEYEDMUTEX2 callback


## -description


Creates a keyed mutex object that includes private data.


## -parameters




### -param *








#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439474">D3DKMT_CREATEKEYEDMUTEX2</a> structure that describes a keyed mutex object to create.


## -returns



Returns one of the following values:

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
The keyed mutex object was successfully created. 

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
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439345">D3DKMTCreateKeyedMutex2</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -remarks



<b>D3DKMTCreateKeyedMutex2</b> behaves like the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546845">D3DKMTCreateKeyedMutex</a> function but lets the caller specify private data to associate with the keyed mutex.

Keyed mutexes created with <b>D3DKMTCreateKeyedMutex2</b> are still compatible with <a href="https://msdn.microsoft.com/library/windows/hardware/ff547054">D3DKMTOpenKeyedMutex</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff546732">D3DKMTAcquireKeyedMutex</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff547129">D3DKMTReleaseKeyedMutex</a> functions.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546732">D3DKMTAcquireKeyedMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546845">D3DKMTCreateKeyedMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547054">D3DKMTOpenKeyedMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547129">D3DKMTReleaseKeyedMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439474">D3DKMT_CREATEKEYEDMUTEX2</a>
 

 

