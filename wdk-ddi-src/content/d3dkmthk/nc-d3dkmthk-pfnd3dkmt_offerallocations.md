---
UID: NC:d3dkmthk.PFND3DKMT_OFFERALLOCATIONS
title: PFND3DKMT_OFFERALLOCATIONS
author: windows-driver-content
description: Offers video memory allocations for reuse.
old-location: display\d3dkmtofferallocations.htm
old-project: display
ms.assetid: 3cc84381-fa1e-4c6c-bb5b-459a93676cfd
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTOfferAllocations, D3DKMTOfferAllocations callback function [Display Devices], PFND3DKMT_OFFERALLOCATIONS, PFND3DKMT_OFFERALLOCATIONS callback, d3dkmthk/D3DKMTOfferAllocations, display.d3dkmtofferallocations
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
-	D3dkmthk.h
api_name:
-	D3DKMTOfferAllocations
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3DKMT_OFFERALLOCATIONS callback function


## -description


Offers video memory allocations for reuse.


## -parameters




### -param *








#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406482">D3DKMT_OFFERALLOCATIONS</a> structure that defines memory allocations that the driver offers for reuse.


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
The allocations were successfully offered.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439451">D3DKMTReclaimAllocations</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406482">D3DKMT_OFFERALLOCATIONS</a>
 

 

