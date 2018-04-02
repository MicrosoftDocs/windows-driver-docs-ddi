---
UID: NF:dbgeng.IDebugClient.SetOutputWidth
title: IDebugClient::SetOutputWidth method
author: windows-driver-content
description: Controls the width of an output line for commands that produce formatted output.
old-location: debugger\idebugclient_setoutputwidth.htm
old-project: debugger
ms.assetid: E2FAEBDD-336D-4E11-933B-88A6EA3BBDF9
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugClient, IDebugClient interface [Windows Debugging], SetOutputWidth method, IDebugClient::SetOutputWidth, SetOutputWidth method [Windows Debugging], SetOutputWidth method [Windows Debugging], IDebugClient interface, SetOutputWidth,IDebugClient.SetOutputWidth, dbgeng/IDebugClient::SetOutputWidth, debugger.idebugclient_setoutputwidth
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient.SetOutputWidth
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient::SetOutputWidth method


## -description


    Controls the width of an output line for
    commands that produce formatted output. 


## -parameters




### -param Columns [in]

The number of columns in the output.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 




## -remarks



This setting is a suggestion that can be overridden by other settings.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>
 

 

