---
UID: NF:dbgeng.IDebugControl4.ExecuteWide
title: IDebugControl4::ExecuteWide method
author: windows-driver-content
description: The ExecuteWide method executes the specified debugger commands.
old-location: debugger\executewide.htm
old-project: debugger
ms.assetid: 2aece5f0-5cfd-47fe-b8c1-e191f0a4296d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ExecuteWide method [Windows Debugging], ExecuteWide method [Windows Debugging], IDebugControl4 interface, ExecuteWide,IDebugControl4.ExecuteWide, IDebugControl4, IDebugControl4 interface [Windows Debugging], ExecuteWide method, IDebugControl4::ExecuteWide, dbgeng/IDebugControl4::ExecuteWide, debugger.executewide
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
-	IDebugControl4.ExecuteWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::ExecuteWide method


## -description


The <b>ExecuteWide</b>  method executes the specified debugger commands.


## -syntax


````
HRESULT ExecuteWide(
  [in] ULONG  OutputControl,
  [in] PCWSTR Command,
  [in] ULONG  Flags
);
````


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



<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::ExecuteWide method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

