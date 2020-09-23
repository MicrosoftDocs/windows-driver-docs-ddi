---
UID: NF:dbgeng.IDebugControl4.ExecuteCommandFileWide
title: IDebugControl4::ExecuteCommandFileWide (dbgeng.h)
description: The ExecuteCommandFileWide method opens the specified file and executes the debugger commands that are contained within.
old-location: debugger\executecommandfilewide.htm
tech.root: debugger
ms.assetid: 4c3fbd76-745a-45d0-b4fd-6da382712322
ms.date: 05/03/2018
keywords: ["IDebugControl4::ExecuteCommandFileWide"]
ms.keywords: ExecuteCommandFileWide, ExecuteCommandFileWide method [Windows Debugging], ExecuteCommandFileWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],ExecuteCommandFileWide method, IDebugControl4.ExecuteCommandFileWide, IDebugControl4::ExecuteCommandFileWide, dbgeng/IDebugControl4::ExecuteCommandFileWide, debugger.executecommandfilewide
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
 - IDebugControl4::ExecuteCommandFileWide
 - dbgeng/IDebugControl4::ExecuteCommandFileWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl4.ExecuteCommandFileWide
---

# IDebugControl4::ExecuteCommandFileWide


## -description

The <b>ExecuteCommandFileWide</b>  method opens the specified file and executes the debugger commands that are contained within.

## -parameters

### -param OutputControl 

[in]
Specifies where to send the output of the command.  For possible values, see <a href="/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.  For more information about output, see <a href="/windows-hardware/drivers/debugger/input-and-output">Input and Output</a>.

### -param CommandFile 

[in]
Specifies the name of the file that contains the commands to execute.  This file is opened for reading and its contents are interpreted as if they had been typed into the debugger console.

### -param Flags 

[in]
Specifies execution options for the command.  The default options are to log the command but not to send it to the output.  For details about the values that <i>Flags</i> can take, see <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-execute">Execute</a>.

## -returns

This method might also return error values, including error values caused by a failure to open the specified file.  For more information, see <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

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

This method reads the specified file and execute the commands one line at a time using <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-execute">Execute</a>.  If an exception occurred while executing a line, the execution will continue with the next line.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-execute">Execute</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>