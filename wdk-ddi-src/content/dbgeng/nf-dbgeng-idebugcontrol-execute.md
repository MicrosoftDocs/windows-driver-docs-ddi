---
UID: NF:dbgeng.IDebugControl.Execute
title: IDebugControl::Execute
author: windows-driver-content
description: The Execute method executes the specified debugger commands.
old-location: debugger\execute.htm
old-project: debugger
ms.assetid: 595aa371-ff7e-48e2-b29a-a7aabc70ebd7
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: Execute, Execute method [Windows Debugging], Execute method [Windows Debugging],IDebugControl interface, Execute method [Windows Debugging],IDebugControl2 interface, Execute method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],Execute method, IDebugControl.Execute, IDebugControl2 interface [Windows Debugging],Execute method, IDebugControl2::Execute, IDebugControl3 interface [Windows Debugging],Execute method, IDebugControl3::Execute, IDebugControl::Execute, IDebugControl_d49bfbf9-c9e1-4a43-8f2c-8778ef51db79.xml, dbgeng/IDebugControl2::Execute, dbgeng/IDebugControl3::Execute, dbgeng/IDebugControl::Execute, debugger.execute
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
-	IDebugControl.Execute
-	IDebugControl2.Execute
-	IDebugControl3.Execute
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::Execute


## -description


The <b>Execute</b>  method executes the specified debugger commands.


## -parameters




### -param OutputControl [in]

Specifies the output control to use while executing the command.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.  For more information about output, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.


### -param Command [in]

Specifies the command string to execute.  The command is interpreted like those typed into a debugger command window.  This command string can contain multiple commands for the engine to execute.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff540507">Debugger Commands</a> for the command reference.


### -param Flags [in]

Specifies a bit field of execution options for the command.  The default options are to log the command but to not send it to the output.  The following table lists the bits that can be set.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_EXECUTE_ECHO

</td>
<td>
The command string is sent to the output.

</td>
</tr>
<tr>
<td>
DEBUG_EXECUTE_NOT_LOGGED

</td>
<td>
The command string is not logged.  This is overridden by DEBUG_EXECUTE_ECHO.

</td>
</tr>
<tr>
<td>
DEBUG_EXECUTE_NO_REPEAT

</td>
<td>
If <i>Command</i> is an empty string, do not repeat the last command, and do not save the current command string for repeat execution later.

</td>
</tr>
</table>
 


## -returns



This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



This method executes the given command string.  If the string has multiple commands, this method will not return until all of the commands have been executed. If the sequence of commands involves waiting for the target to execute, this method can take an arbitrary amount of time to complete.

<div class="alert"><b>Note</b>  It is important to understand what it means for a step command to execute. A step command initiates a stepping action but does not wait for the stepping to complete. For example, suppose you call <b>IDebugControl::Execute</b> and pass a command string that contains the single command <a href="https://msdn.microsoft.com/ff4b5708-b9d0-4809-9fe4-9a22d4cacbc0">pct</a>. The <b>pct</b> command initiates a step to the next call or return instruction, but <b>pct</b> completes its execution before the stepping takes place. Consequently, <b>IDebugControl::Execute</b> returns before the stepping takes place. Trace and go commands behave in a similar way. Examples of commands that have this behavior include <a href="https://msdn.microsoft.com/9b6aac94-6c53-40c2-a8de-2ad106678c65">g</a>, <a href="https://msdn.microsoft.com/3e06a3ff-b57d-435f-9625-011f38d7b26a">gh</a>, <a href="https://msdn.microsoft.com/99741659-dd43-44ea-ac27-06d821b47fbe">ta</a>, <a href="https://msdn.microsoft.com/28b736f9-69f5-405b-9684-48b4205e7633">tb</a>, <a href="https://msdn.microsoft.com/059d8071-577f-4306-8273-8fdff6a80626">tct</a>, <a href="https://msdn.microsoft.com/497261a9-69fb-4df2-b342-cd62bda8a51f">pa</a>, and <a href="https://msdn.microsoft.com/4b9b786c-2ecc-44a6-a82b-0641d7991abc">pc</a>.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543215">ExecuteCommandFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>
 

 

