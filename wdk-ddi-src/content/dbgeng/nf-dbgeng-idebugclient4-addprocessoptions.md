---
UID: NF:dbgeng.IDebugClient4.AddProcessOptions
title: IDebugClient4::AddProcessOptions (dbgeng.h)
description: The AddProcessOptions method adds the process options to those options that affect the current process.
old-location: debugger\addprocessoptions.htm
tech.root: debugger
ms.assetid: eb5f1d91-cfad-48e6-b578-64b64034222f
ms.date: 05/03/2018
keywords: ["IDebugClient4::AddProcessOptions"]
ms.keywords: AddProcessOptions, AddProcessOptions method [Windows Debugging], AddProcessOptions method [Windows Debugging],IDebugClient interface, AddProcessOptions method [Windows Debugging],IDebugClient2 interface, AddProcessOptions method [Windows Debugging],IDebugClient3 interface, AddProcessOptions method [Windows Debugging],IDebugClient4 interface, AddProcessOptions method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],AddProcessOptions method, IDebugClient2 interface [Windows Debugging],AddProcessOptions method, IDebugClient2::AddProcessOptions, IDebugClient3 interface [Windows Debugging],AddProcessOptions method, IDebugClient3::AddProcessOptions, IDebugClient4 interface [Windows Debugging],AddProcessOptions method, IDebugClient4.AddProcessOptions, IDebugClient4::AddProcessOptions, IDebugClient5 interface [Windows Debugging],AddProcessOptions method, IDebugClient5::AddProcessOptions, IDebugClient::AddProcessOptions, IDebugClient_995041c9-9380-4a66-b9f8-d74d68398a44.xml, dbgeng/IDebugClient2::AddProcessOptions, dbgeng/IDebugClient3::AddProcessOptions, dbgeng/IDebugClient4::AddProcessOptions, dbgeng/IDebugClient5::AddProcessOptions, dbgeng/IDebugClient::AddProcessOptions, debugger.addprocessoptions
f1_keywords:
 - "dbgeng/IDebugClient.AddProcessOptions"
 - "IDebugClient.AddProcessOptions"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugClient.AddProcessOptions
- IDebugClient2.AddProcessOptions
- IDebugClient3.AddProcessOptions
- IDebugClient4.AddProcessOptions
- IDebugClient5.AddProcessOptions
targetos: Windows
req.typenames: 
---

# IDebugClient4::AddProcessOptions


## -description


The <b>AddProcessOptions</b> method adds the process options to those options that affect the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/c">current process</a>.


## -parameters




### -param Options [in]

Specifies the process options to add to those affecting the current process.  For details on these process options, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-process-xxx">DEBUG_PROCESS_XXX</a>.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



This method is available only in <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/l">live user-mode debugging</a>.

Some of the process options are global options, others are specific to the current process.

If any process options are modified, the engine will notify the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/e">event callbacks</a> by calling their <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> method with the DEBUG_CES_PROCESS_OPTIONS flag set.

For more information about creating and attaching to live user-mode targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/live-user-mode-targets">Live User-Mode Targets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-process-xxx">DEBUG_PROCESS_XXX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getprocessoptions">GetProcessOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-removeprocessoptions">RemoveProcessOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-setprocessoptions">SetProcessOptions</a>
 

 

