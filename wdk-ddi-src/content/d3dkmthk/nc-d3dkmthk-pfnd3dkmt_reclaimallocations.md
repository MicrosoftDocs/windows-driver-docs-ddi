---
UID: NC:d3dkmthk.PFND3DKMT_RECLAIMALLOCATIONS
title: PFND3DKMT_RECLAIMALLOCATIONS
author: windows-driver-content
description: Reclaims video memory allocations.
old-location: display\d3dkmtreclaimallocations.htm
ms.assetid: 3bfb2a82-9451-4365-b113-6311c3f13fe6
ms.date: 5/10/2018
ms.keywords: D3DKMTReclaimAllocations, D3DKMTReclaimAllocations callback function [Display Devices], PFND3DKMT_RECLAIMALLOCATIONS, PFND3DKMT_RECLAIMALLOCATIONS callback, d3dkmthk/D3DKMTReclaimAllocations, display.d3dkmtreclaimallocations
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
-	D3dkmthk.h
api_name:
-	D3DKMTReclaimAllocations
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DKMT_RECLAIMALLOCATIONS callback function


## -description


Reclaims video memory allocations.


## -parameters




### -param *

*pData* 

[in, out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406566">D3DKMT_RECLAIMALLOCATIONS</a> structure that defines memory allocations to reclaim.


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
The allocations were successfully reclaimed.

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
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439402">D3DKMTOfferAllocations</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406566">D3DKMT_RECLAIMALLOCATIONS</a>
 

 

