---
UID: NF:dbgeng.IDebugClient5.CreateProcessWide
title: IDebugClient5::CreateProcessWide (dbgeng.h)
description: The CreateProcessWide method creates a process from the specified command line.
old-location: debugger\createprocesswide.htm
tech.root: debugger
ms.assetid: 2a45c971-3dad-47ad-a819-6f2c6e34ad37
ms.date: 05/03/2018
ms.keywords: CreateProcessWide, CreateProcessWide method [Windows Debugging], CreateProcessWide method [Windows Debugging],IDebugClient3 interface, CreateProcessWide method [Windows Debugging],IDebugClient4 interface, CreateProcessWide method [Windows Debugging],IDebugClient5 interface, IDebugClient3 interface [Windows Debugging],CreateProcessWide method, IDebugClient3::CreateProcessWide, IDebugClient4 interface [Windows Debugging],CreateProcessWide method, IDebugClient4::CreateProcessWide, IDebugClient5 interface [Windows Debugging],CreateProcessWide method, IDebugClient5.CreateProcessWide, IDebugClient5::CreateProcessWide, dbgeng/IDebugClient3::CreateProcessWide, dbgeng/IDebugClient4::CreateProcessWide, dbgeng/IDebugClient5::CreateProcessWide, debugger.createprocesswide
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
- IDebugClient3.CreateProcessWide
- IDebugClient4.CreateProcessWide
- IDebugClient5.CreateProcessWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::CreateProcessWide


## -description


The <b>CreateProcessWide</b> method creates a process from the specified command line.


## -parameters




### -param Server [in]

Specifies the process server to use when attaching to the process.  If <i>Server</i> is zero, the engine will create a local process without using a process server.


### -param CommandLine [in]

Specifies the command line to execute to create the new process. The <b>CreateProcessWide</b> method might modify the contents of the string that you supply in this parameter. Therefore, this parameter cannot be a pointer to read-only memory (such as a const variable or a literal string). Passing a constant string in this parameter can lead to an access violation.


### -param CreateFlags [in]

Specifies the flags to use when creating the process.  For details on these flags, see the <b>CreateFlags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/ns-dbgeng-_debug_create_process_options">DEBUG_CREATE_PROCESS_OPTIONS</a> structure.


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

If <i>CreateFlags</i> contains either of the flags DEBUG_PROCESS or DEBUG_ONLY_THIS_PROCESS, the engine also attaches to the newly created process. This behavior is similar to that of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-createprocessandattach2">CreateProcessAndAttach2</a> when its argument <i>ProcessId</i> is set to zero.

For more information about creating and attaching to live user-mode targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/live-user-mode-targets">Live User-Mode Targets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-create--create-process-">.create (Create Process)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-attachprocess">AttachProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-connectprocessserver">ConnectProcessServer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-createprocess2">CreateProcess2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-createprocessandattach2">CreateProcessAndAttach2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
 

 

