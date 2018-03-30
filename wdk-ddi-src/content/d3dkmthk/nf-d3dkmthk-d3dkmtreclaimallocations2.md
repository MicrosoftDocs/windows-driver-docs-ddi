---
UID: NF:d3dkmthk.D3DKMTReclaimAllocations2
title: D3DKMTReclaimAllocations2 function
author: windows-driver-content
description: D3DKMTReclaimAllocations2 reclaims video memory allocations.
old-location: display\d3dkmtreclaimallocations2.htm
old-project: display
ms.assetid: 0BC49546-ECDE-447D-8F7E-4235D96D293B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTReclaimAllocations2, D3DKMTReclaimAllocations2 function [Display Devices], d3dkmthk/D3DKMTReclaimAllocations2, display.d3dkmtreclaimallocations2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.dll: GDI32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTReclaimAllocations2
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTReclaimAllocations2 function


## -description


<b>D3DKMTReclaimAllocations2</b> reclaims video memory allocations.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906801">D3DKMT_RECLAIMALLOCATIONS2</a> structure that defines memory allocations to reclaim.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906801">D3DKMT_RECLAIMALLOCATIONS2</a>
 

 

