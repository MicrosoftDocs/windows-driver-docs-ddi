---
UID: NF:dbgeng.IDebugControl6.GetExecutionStatusEx
title: IDebugControl6::GetExecutionStatusEx (dbgeng.h)
description: The GetExecutionStatusEx method returns information about the execution status of the debugger engine.
old-location: debugger\idebugcontrol6_getexecutionstatusex.htm
tech.root: debugger
ms.assetid: C14A3106-AEF7-4BA2-9E21-32D8B2D5BD7E
ms.date: 05/03/2018
keywords: ["IDebugControl6::GetExecutionStatusEx"]
ms.keywords: GetExecutionStatusEx, GetExecutionStatusEx method [Windows Debugging], GetExecutionStatusEx method [Windows Debugging],IDebugControl6 interface, IDebugControl6 interface [Windows Debugging],GetExecutionStatusEx method, IDebugControl6.GetExecutionStatusEx, IDebugControl6::GetExecutionStatusEx, dbgeng/IDebugControl6::GetExecutionStatusEx, debugger.idebugcontrol6_getexecutionstatusex
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugControl6::GetExecutionStatusEx
 - dbgeng/IDebugControl6::GetExecutionStatusEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl6.GetExecutionStatusEx
---

# IDebugControl6::GetExecutionStatusEx


## -description

The GetExecutionStatusEx method returns information about the execution status of the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a>.

## -parameters

### -param Status 

[out]
Receives the extended execution status.  This will be set to values described in  <a href="/windows-hardware/drivers/debugger/debug-status-xxx">DEBUG_STATUS_XXX</a>.

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
</table>

## -remarks

For more information, see <a href="/windows-hardware/drivers/debugger/target-information">Target Information</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol6">IDebugControl6</a>