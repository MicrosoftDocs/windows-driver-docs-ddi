---
UID: NF:d3dkmthk.D3DKMTReclaimAllocations2
title: D3DKMTReclaimAllocations2 function
author: windows-driver-content
description: D3DKMTReclaimAllocations2 reclaims video memory allocations.
old-location: display\d3dkmtreclaimallocations2.htm
old-project: display
ms.assetid: 0BC49546-ECDE-447D-8F7E-4235D96D293B
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , 2, 3, A, D, D3DKMTReclaimAllocations2, D3DKMTReclaimAllocations2 function [Display Devices], K, M, R, T, a, c, d3dkmthk/D3DKMTReclaimAllocations2, display.d3dkmtreclaimallocations2, e, i, l, m, n, o, s, t"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTReclaimAllocations2
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTReclaimAllocations2 function


## -description


<b>D3DKMTReclaimAllocations2</b> reclaims video memory allocations.


## -syntax


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTReclaimAllocations2(
  _Inout_ D3DKMT_RECLAIMALLOCATIONS2 *pData
);
````


## -parameters






#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_reclaimallocations2.md">D3DKMT_RECLAIMALLOCATIONS2</a> structure that defines memory allocations to reclaim.


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

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_reclaimallocations2.md">D3DKMT_RECLAIMALLOCATIONS2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTReclaimAllocations2 function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

