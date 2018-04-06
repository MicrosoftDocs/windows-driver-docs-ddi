---
UID: NF:d3dkmthk.D3DKMTEvict
title: D3DKMTEvict function
author: windows-driver-content
description: D3DKMTEvict is used to decrement the allocation residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.
old-location: display\d3dkmtevict.htm
old-project: display
ms.assetid: 010F7CB0-F930-47FF-91DF-D95B21FC76A0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTEvict, D3DKMTEvict function [Display Devices], d3dkmthk/D3DKMTEvict, display.d3dkmtevict
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
req.lib: GDI32.lib
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
-	D3DKMTEvict
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTEvict function


## -description


<b>D3DKMTEvict</b> is used to decrement the allocation residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906794">D3DKMT_EVICT</a> structure that describes the operation.


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
The operation was performed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">

         Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -remarks



Once the eviction request is queued, it is illegal to access the underlying allocation as the allocation may be evicted at anytime from there on at the operating system discretion.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906794">D3DKMT_EVICT</a>
 

 

