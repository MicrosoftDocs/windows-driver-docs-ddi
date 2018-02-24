---
UID: NF:dbgeng.IDebugControl3.ExecuteCommandFile
title: IDebugControl3::ExecuteCommandFile method
author: windows-driver-content
description: The ExecuteCommandFile method opens the specified file and executes the debugger commands that are contained within.
old-location: debugger\executecommandfile.htm
old-project: Debugger
ms.assetid: 6b8f53d7-361c-40a3-b93c-39e653bd9032
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugControl2::ExecuteCommandFile, IDebugControl2, IDebugControl3::ExecuteCommandFile, IDebugControl, IDebugControl3, debugger.executecommandfile, dbgeng/IDebugControl3::ExecuteCommandFile, IDebugControl2 interface [Windows Debugging], ExecuteCommandFile method, ExecuteCommandFile method [Windows Debugging], IDebugControl interface, ExecuteCommandFile method [Windows Debugging], IDebugControl2 interface, IDebugControl_61c4589a-321e-4574-8565-87bdc7b36a73.xml, ExecuteCommandFile, dbgeng/IDebugControl::ExecuteCommandFile, IDebugControl::ExecuteCommandFile, ExecuteCommandFile method [Windows Debugging], IDebugControl3 interface, IDebugControl3 interface [Windows Debugging], ExecuteCommandFile method, ExecuteCommandFile method [Windows Debugging], IDebugControl interface [Windows Debugging], ExecuteCommandFile method, dbgeng/IDebugControl2::ExecuteCommandFile
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl.ExecuteCommandFile
-	IDebugControl2.ExecuteCommandFile
-	IDebugControl3.ExecuteCommandFile
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::ExecuteCommandFile method


## -description


The <b>ExecuteCommandFile</b>  method opens the specified file and executes the debugger commands that are contained within.


## -syntax


````
HRESULT ExecuteCommandFile(
  [in] ULONG OutputControl,
  [in] PCSTR CommandFile,
  [in] ULONG Flags
);
````


## -parameters




### -param OutputControl [in]

Specifies where to send the output of the command.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.  For more information about output, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.


### -param CommandFile [in]

Specifies the name of the file that contains the commands to execute.  This file is opened for reading and its contents are interpreted as if they had been typed into the debugger console.


### -param Flags [in]

Specifies execution options for the command.  The default options are to log the command but not to send it to the output.  For details about the values that <i>Flags</i> can take, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543208">Execute</a>.


## -returns



This method might also return error values, including error values caused by a failure to open the specified file.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.

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



This method reads the specified file and execute the commands one line at a time using <a href="https://msdn.microsoft.com/library/windows/hardware/ff543208">Execute</a>.  If an exception occurred while executing a line, the execution will continue with the next line.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543208">Execute</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl::ExecuteCommandFile method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

