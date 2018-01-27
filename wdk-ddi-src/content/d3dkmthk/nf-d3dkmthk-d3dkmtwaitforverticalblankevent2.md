---
UID: NF:d3dkmthk.D3DKMTWaitForVerticalBlankEvent2
title: D3DKMTWaitForVerticalBlankEvent2 function
author: windows-driver-content
description: Waits for specified wait objects, including a vertical blank event, to occur and then returns. Supported starting with Windows 8.
old-location: display\d3dkmtwaitforverticalblankevent2.htm
old-project: display
ms.assetid: 71a48c1f-1eca-4f3e-a085-99ffc207a7e0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTWaitForVerticalBlankEvent2 function [Display Devices], display.d3dkmtwaitforverticalblankevent2, D3DKMTWaitForVerticalBlankEvent2, d3dkmthk/D3DKMTWaitForVerticalBlankEvent2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	D3dkmthk.h
apiname: 
-	D3DKMTWaitForVerticalBlankEvent2
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTWaitForVerticalBlankEvent2 function


## -description


Waits for specified wait objects, including a vertical blank event, to occur and then returns. Supported starting with Windows 8.


## -syntax


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTWaitForVerticalBlankEvent2(
  _In_ const D3DKMT_WAITFORVERTICALBLANKEVENT2 *pWait
);
````


## -parameters




### -param D3DKMT_WAITFORVERTICALBLANKEVENT2

TBD



#### - pWait [in]

Specifies parameters for waiting on multiple wait objects, including a vertical blank event.


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
<dt><b>STATUS_WAIT_0 </b></dt>
</dl>
</td>
<td width="60%">
The vertical blank event caused the wait object to return.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_WAIT_1–STATUS_WAIT_8</dt>
</dl>
</td>
<td width="60%">
The number of the user-mode event that caused the wait object to return.

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


