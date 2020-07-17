---
UID: NF:dbgeng.IDebugClient3.CreateProcess
title: IDebugClient3::CreateProcess (dbgeng.h)
description: The CreateProcess method creates a process from the specified command line.
old-location: debugger\createprocess.htm
tech.root: debugger
ms.assetid: 0c70c1f8-3c1c-4401-a7c4-14dc9bd0af04
ms.date: 05/03/2018
keywords: ["IDebugClient3::CreateProcess"]
ms.keywords: CreateProcess, CreateProcess method [Windows Debugging], CreateProcess method [Windows Debugging],IDebugClient interface, CreateProcess method [Windows Debugging],IDebugClient2 interface, CreateProcess method [Windows Debugging],IDebugClient3 interface, CreateProcess method [Windows Debugging],IDebugClient4 interface, CreateProcess method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],CreateProcess method, IDebugClient2 interface [Windows Debugging],CreateProcess method, IDebugClient2::CreateProcess, IDebugClient3 interface [Windows Debugging],CreateProcess method, IDebugClient3.CreateProcess, IDebugClient3::CreateProcess, IDebugClient4 interface [Windows Debugging],CreateProcess method, IDebugClient4::CreateProcess, IDebugClient5 interface [Windows Debugging],CreateProcess method, IDebugClient5::CreateProcess, IDebugClient::CreateProcess, IDebugClient_6411b416-f861-4c99-94bc-ceffd54acce0.xml, dbgeng/IDebugClient2::CreateProcess, dbgeng/IDebugClient3::CreateProcess, dbgeng/IDebugClient4::CreateProcess, dbgeng/IDebugClient5::CreateProcess, dbgeng/IDebugClient::CreateProcess, debugger.createprocess
f1_keywords:
 - "dbgeng/IDebugClient.CreateProcess"
 - "IDebugClient.CreateProcess"
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
- IDebugClient.CreateProcess
- IDebugClient2.CreateProcess
- IDebugClient3.CreateProcess
- IDebugClient4.CreateProcess
- IDebugClient5.CreateProcess
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient3::CreateProcess


## -description


The <b>CreateProcess</b>  method creates a process from the specified command line.


## -parameters




### -param Server [in]

Specifies the process server to use to attach to the process.  If <i>Server</i> is zero, the engine will create a local process without using a process server.


### -param CommandLine [in]

Specifies the command line to execute to create the new process.


### -param CreateFlags [in]

Specifies the flags to use when creating the process.  For details on these flags, see the <b>CreateFlags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_create_process_options">DEBUG_CREATE_PROCESS_OPTIONS</a> structure.


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



This method is available only for live user-mode debugging.

If <i>CreateFlags</i> contains either of the flags DEBUG_PROCESS or DEBUG_ONLY_THIS_PROCESS, the engine will also attach to the newly created process; this is similar to the behavior of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocessandattach2">CreateProcessAndAttach2</a> with its argument <i>ProcessId</i> set to zero.

For more information about creating and attaching to live user-mode targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/live-user-mode-targets">Live User-Mode Targets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-create--create-process-">.create (Create Process)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachprocess">AttachProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-connectprocessserver">ConnectProcessServer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocess2">CreateProcess2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocessandattach2">CreateProcessAndAttach2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
 

 

