---
UID: NF:dbgeng.IDebugControl3.ExecuteCommandFile
title: IDebugControl3::ExecuteCommandFile (dbgeng.h)
description: The ExecuteCommandFile method opens the specified file and executes the debugger commands that are contained within.
old-location: debugger\executecommandfile.htm
tech.root: debugger
ms.assetid: 6b8f53d7-361c-40a3-b93c-39e653bd9032
ms.date: 05/03/2018
keywords: ["IDebugControl3::ExecuteCommandFile"]
ms.keywords: ExecuteCommandFile, ExecuteCommandFile method [Windows Debugging], ExecuteCommandFile method [Windows Debugging],IDebugControl interface, ExecuteCommandFile method [Windows Debugging],IDebugControl2 interface, ExecuteCommandFile method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],ExecuteCommandFile method, IDebugControl2 interface [Windows Debugging],ExecuteCommandFile method, IDebugControl2::ExecuteCommandFile, IDebugControl3 interface [Windows Debugging],ExecuteCommandFile method, IDebugControl3.ExecuteCommandFile, IDebugControl3::ExecuteCommandFile, IDebugControl::ExecuteCommandFile, IDebugControl_61c4589a-321e-4574-8565-87bdc7b36a73.xml, dbgeng/IDebugControl2::ExecuteCommandFile, dbgeng/IDebugControl3::ExecuteCommandFile, dbgeng/IDebugControl::ExecuteCommandFile, debugger.executecommandfile
f1_keywords:
 - "dbgeng/IDebugControl.ExecuteCommandFile"
 - "IDebugControl.ExecuteCommandFile"
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
- IDebugControl.ExecuteCommandFile
- IDebugControl2.ExecuteCommandFile
- IDebugControl3.ExecuteCommandFile
targetos: Windows
req.typenames: 
---

# IDebugControl3::ExecuteCommandFile


## -description


The <b>ExecuteCommandFile</b>  method opens the specified file and executes the debugger commands that are contained within.


## -parameters




### -param OutputControl 
[in]
Specifies where to send the output of the command.  For possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.  For more information about output, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/input-and-output">Input and Output</a>.


### -param CommandFile 
[in]
Specifies the name of the file that contains the commands to execute.  This file is opened for reading and its contents are interpreted as if they had been typed into the debugger console.


### -param Flags 
[in]
Specifies execution options for the command.  The default options are to log the command but not to send it to the output.  For details about the values that <i>Flags</i> can take, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-execute">Execute</a>.


## -returns



This method might also return error values, including error values caused by a failure to open the specified file.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

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



This method reads the specified file and execute the commands one line at a time using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-execute">Execute</a>.  If an exception occurred while executing a line, the execution will continue with the next line.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-execute">Execute</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>
 

 

