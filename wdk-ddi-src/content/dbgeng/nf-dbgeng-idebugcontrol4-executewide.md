---
UID: NF:dbgeng.IDebugControl4.ExecuteWide
title: IDebugControl4::ExecuteWide
author: windows-driver-content
description: The ExecuteWide method executes the specified debugger commands.
old-location: debugger\executewide.htm
tech.root: debugger
ms.assetid: 2aece5f0-5cfd-47fe-b8c1-e191f0a4296d
ms.date: 5/3/2018
ms.keywords: ExecuteWide, ExecuteWide method [Windows Debugging], ExecuteWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],ExecuteWide method, IDebugControl4.ExecuteWide, IDebugControl4::ExecuteWide, dbgeng/IDebugControl4::ExecuteWide, debugger.executewide
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
-	IDebugControl4.ExecuteWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::ExecuteWide


## -description


The <b>ExecuteWide</b>  method executes the specified debugger commands.


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



This method executes the given command string.  If the string has multiple commands, these methods will not return until all of the commands have been executed. This may involve waiting for the target to execute, so these methods can take an arbitrary amount of time to complete.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543215">ExecuteCommandFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
 

 

