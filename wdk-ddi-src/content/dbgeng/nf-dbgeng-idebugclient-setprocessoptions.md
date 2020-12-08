---
UID: NF:dbgeng.IDebugClient.SetProcessOptions
title: IDebugClient::SetProcessOptions (dbgeng.h)
description: The SetProcessOptions method sets the process options affecting the current process.
old-location: debugger\setprocessoptions.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient::SetProcessOptions"]
ms.keywords: IDebugClient interface [Windows Debugging],SetProcessOptions method, IDebugClient.SetProcessOptions, IDebugClient2 interface [Windows Debugging],SetProcessOptions method, IDebugClient2::SetProcessOptions, IDebugClient3 interface [Windows Debugging],SetProcessOptions method, IDebugClient3::SetProcessOptions, IDebugClient4 interface [Windows Debugging],SetProcessOptions method, IDebugClient4::SetProcessOptions, IDebugClient5 interface [Windows Debugging],SetProcessOptions method, IDebugClient5::SetProcessOptions, IDebugClient::SetProcessOptions, IDebugClient_d9936a28-08c3-4c4c-ba2b-accc9443b825.xml, SetProcessOptions, SetProcessOptions method [Windows Debugging], SetProcessOptions method [Windows Debugging],IDebugClient interface, SetProcessOptions method [Windows Debugging],IDebugClient2 interface, SetProcessOptions method [Windows Debugging],IDebugClient3 interface, SetProcessOptions method [Windows Debugging],IDebugClient4 interface, SetProcessOptions method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::SetProcessOptions, dbgeng/IDebugClient3::SetProcessOptions, dbgeng/IDebugClient4::SetProcessOptions, dbgeng/IDebugClient5::SetProcessOptions, dbgeng/IDebugClient::SetProcessOptions, debugger.setprocessoptions
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
 - IDebugClient::SetProcessOptions
 - dbgeng/IDebugClient::SetProcessOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient.SetProcessOptions
 - IDebugClient2.SetProcessOptions
 - IDebugClient3.SetProcessOptions
 - IDebugClient4.SetProcessOptions
 - IDebugClient5.SetProcessOptions
---

# IDebugClient::SetProcessOptions


## -description

The <b>SetProcessOptions</b> method sets the process options affecting the current process.

## -parameters

### -param Options 

[in]
Specifies a set of flags that will become the new process options for the current process.  For details on these options, see <a href="/windows-hardware/drivers/debugger/debug-process-xxx">DEBUG_PROCESS_XXX</a>.

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

This method is available only in live user-mode debugging.

Some of the process options are global options, others are specific to the current process.

If any process options are modified, the engine will notify the event callbacks by calling their <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> method with the DEBUG_CES_PROCESS_OPTIONS flag set.

For more information about creating and attaching to live user-mode targets, see <a href="/windows-hardware/drivers/debugger/live-user-mode-targets">Live User-Mode Targets</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-addprocessoptions">AddProcessOptions</a>



<a href="/windows-hardware/drivers/debugger/debug-process-xxx">DEBUG_PROCESS_XXX</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getprocessoptions">GetProcessOptions</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-removeprocessoptions">RemoveProcessOptions</a>
