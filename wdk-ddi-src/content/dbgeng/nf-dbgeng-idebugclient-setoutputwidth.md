---
UID: NF:dbgeng.IDebugClient.SetOutputWidth
title: IDebugClient::SetOutputWidth method
author: windows-driver-content
description: Controls the width of an output line for commands that produce formatted output.
old-location: debugger\idebugclient_setoutputwidth.htm
old-project: debugger
ms.assetid: E2FAEBDD-336D-4E11-933B-88A6EA3BBDF9
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient::SetOutputWidth, IDebugClient interface [Windows Debugging], SetOutputWidth method, debugger.idebugclient_setoutputwidth, SetOutputWidth method [Windows Debugging], SetOutputWidth, IDebugClient, dbgeng/IDebugClient::SetOutputWidth, SetOutputWidth method [Windows Debugging], IDebugClient interface
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugClient.SetOutputWidth
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugClient::SetOutputWidth method


## -description


    Controls the width of an output line for
    commands that produce formatted output. 


## -syntax


````
HRESULT SetOutputWidth(
  [in] ULONG Columns

);
````


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

<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::SetOutputWidth method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

