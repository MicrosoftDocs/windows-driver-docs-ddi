---
UID: NF:dbgeng.IDebugClient5.GetExitCode
title: IDebugClient5::GetExitCode (dbgeng.h)
description: The GetExitCode method returns the exit code of the current process if that process has already run through to completion.
old-location: debugger\getexitcode.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient5::GetExitCode"]
ms.keywords: GetExitCode, GetExitCode method [Windows Debugging], GetExitCode method [Windows Debugging],IDebugClient interface, GetExitCode method [Windows Debugging],IDebugClient2 interface, GetExitCode method [Windows Debugging],IDebugClient3 interface, GetExitCode method [Windows Debugging],IDebugClient4 interface, GetExitCode method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],GetExitCode method, IDebugClient2 interface [Windows Debugging],GetExitCode method, IDebugClient2::GetExitCode, IDebugClient3 interface [Windows Debugging],GetExitCode method, IDebugClient3::GetExitCode, IDebugClient4 interface [Windows Debugging],GetExitCode method, IDebugClient4::GetExitCode, IDebugClient5 interface [Windows Debugging],GetExitCode method, IDebugClient5.GetExitCode, IDebugClient5::GetExitCode, IDebugClient::GetExitCode, IDebugClient_c0198b4c-b627-42c9-80eb-15db22156293.xml, dbgeng/IDebugClient2::GetExitCode, dbgeng/IDebugClient3::GetExitCode, dbgeng/IDebugClient4::GetExitCode, dbgeng/IDebugClient5::GetExitCode, dbgeng/IDebugClient::GetExitCode, debugger.getexitcode
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugClient5::GetExitCode
 - dbgeng/IDebugClient5::GetExitCode
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient.GetExitCode
 - IDebugClient2.GetExitCode
 - IDebugClient3.GetExitCode
 - IDebugClient4.GetExitCode
 - IDebugClient5.GetExitCode
---

# IDebugClient5::GetExitCode


## -description

The <b>GetExitCode</b> method returns the exit code of the current process if that process has already run through to completion.

## -parameters

### -param Code 

[out]
Receives the exit code of the process.  If the process is still running, <i>Code</i> will be set to STILL_ACTIVE.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
