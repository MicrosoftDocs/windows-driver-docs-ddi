---
UID: NF:dbgeng.IDebugClient4.GetExitCode
title: IDebugClient4::GetExitCode method
author: windows-driver-content
description: The GetExitCode method returns the exit code of the current process if that process has already run through to completion.
old-location: debugger\getexitcode.htm
old-project: debugger
ms.assetid: faa5cc0f-a99c-42fb-ab8f-a37c31bc4dde
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetExitCode method [Windows Debugging], GetExitCode method [Windows Debugging], IDebugClient interface, GetExitCode method [Windows Debugging], IDebugClient2 interface, GetExitCode method [Windows Debugging], IDebugClient3 interface, GetExitCode method [Windows Debugging], IDebugClient4 interface, GetExitCode method [Windows Debugging], IDebugClient5 interface, GetExitCode,IDebugClient4.GetExitCode, IDebugClient interface [Windows Debugging], GetExitCode method, IDebugClient2 interface [Windows Debugging], GetExitCode method, IDebugClient2::GetExitCode, IDebugClient3 interface [Windows Debugging], GetExitCode method, IDebugClient3::GetExitCode, IDebugClient4, IDebugClient4 interface [Windows Debugging], GetExitCode method, IDebugClient4::GetExitCode, IDebugClient5 interface [Windows Debugging], GetExitCode method, IDebugClient5::GetExitCode, IDebugClient::GetExitCode, IDebugClient_c0198b4c-b627-42c9-80eb-15db22156293.xml, dbgeng/IDebugClient2::GetExitCode, dbgeng/IDebugClient3::GetExitCode, dbgeng/IDebugClient4::GetExitCode, dbgeng/IDebugClient5::GetExitCode, dbgeng/IDebugClient::GetExitCode, debugger.getexitcode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient.GetExitCode
-	IDebugClient2.GetExitCode
-	IDebugClient3.GetExitCode
-	IDebugClient4.GetExitCode
-	IDebugClient5.GetExitCode
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient4::GetExitCode method


## -description


The <b>GetExitCode</b> method returns the exit code of the current process if that process has already run through to completion.


## -syntax


````
HRESULT GetExitCode(
  [out] PULONG Code
);
````


## -parameters




### -param Code [out]

Receives the exit code of the process.  If the process is still running, <i>Code</i> will be set to STILL_ACTIVE.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The process is still running.

</td>
</tr>
</table>
 




## -remarks



This method is available only for live user-mode debugging.



