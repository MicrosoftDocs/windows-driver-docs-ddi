---
UID: NF:dbgeng.IDebugControl6.GetExecutionStatusEx
title: IDebugControl6::GetExecutionStatusEx method
author: windows-driver-content
description: The GetExecutionStatusEx method returns information about the execution status of the debugger engine.
old-location: debugger\idebugcontrol6_getexecutionstatusex.htm
old-project: debugger
ms.assetid: C14A3106-AEF7-4BA2-9E21-32D8B2D5BD7E
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetExecutionStatusEx method [Windows Debugging], GetExecutionStatusEx, IDebugControl6, IDebugControl6::GetExecutionStatusEx, debugger.idebugcontrol6_getexecutionstatusex, GetExecutionStatusEx method [Windows Debugging], IDebugControl6 interface, dbgeng/IDebugControl6::GetExecutionStatusEx, IDebugControl6 interface [Windows Debugging], GetExecutionStatusEx method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: 
req.target-type: Desktop
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
-	IDebugControl6.GetExecutionStatusEx
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl6::GetExecutionStatusEx method


## -description


The GetExecutionStatusEx method returns information about the execution status of the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>.


## -syntax


````
HRESULT GetExecutionStatusEx(
  [out] PULONG Status
);
````


## -parameters




### -param Status [out]

Receives the extended execution status.  This will be set to values described in  <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a>.


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



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol6.md">IDebugControl6</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl6::GetExecutionStatusEx method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

