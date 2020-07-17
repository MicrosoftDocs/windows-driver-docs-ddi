---
UID: NF:dbgeng.IDebugControl2.OutputDisassemblyLines
title: IDebugControl2::OutputDisassemblyLines (dbgeng.h)
description: The OutputDisassemblyLines method disassembles several processor instructions and sends the resulting assembly instructions to the output callbacks.
old-location: debugger\outputdisassemblylines.htm
tech.root: debugger
ms.assetid: fb69e052-1033-457d-bafb-bf4be4ea5966
ms.date: 05/03/2018
keywords: ["IDebugControl2::OutputDisassemblyLines"]
ms.keywords: IDebugControl interface [Windows Debugging],OutputDisassemblyLines method, IDebugControl2 interface [Windows Debugging],OutputDisassemblyLines method, IDebugControl2.OutputDisassemblyLines, IDebugControl2::OutputDisassemblyLines, IDebugControl3 interface [Windows Debugging],OutputDisassemblyLines method, IDebugControl3::OutputDisassemblyLines, IDebugControl::OutputDisassemblyLines, IDebugControl_51f0991b-9b9d-4a21-89be-099537a78ea5.xml, OutputDisassemblyLines, OutputDisassemblyLines method [Windows Debugging], OutputDisassemblyLines method [Windows Debugging],IDebugControl interface, OutputDisassemblyLines method [Windows Debugging],IDebugControl2 interface, OutputDisassemblyLines method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::OutputDisassemblyLines, dbgeng/IDebugControl3::OutputDisassemblyLines, dbgeng/IDebugControl::OutputDisassemblyLines, debugger.outputdisassemblylines
f1_keywords:
 - "dbgeng/IDebugControl.OutputDisassemblyLines"
 - "IDebugControl.OutputDisassemblyLines"
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
- IDebugControl.OutputDisassemblyLines
- IDebugControl2.OutputDisassemblyLines
- IDebugControl3.OutputDisassemblyLines
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::OutputDisassemblyLines


## -description


The <b>OutputDisassemblyLines</b> method disassembles several processor instructions and sends the resulting assembly instructions to the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">output callbacks</a>.


## -parameters




### -param OutputControl [in]

Specifies the output control that determines which client's output callbacks receive the output.  For possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.  For more information about output, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/input-and-output">Input and Output</a>.


### -param PreviousLines [in]

Specifies the number of lines of instructions before the instruction at <i>Offset</i> to include in the output.  Typically, each instruction is output on a single line.  However, some instructions can take up several lines of output; this can cause the number of lines output before the instruction at <i>Offset</i> to be greater than <i>PreviousLines</i>.


### -param TotalLines [in]

Specifies the total number of lines of instructions to include in the output.  Typically, each instruction is output on a single line.  However, some instructions can take up several lines of output; this can cause the number of lines output to be greater than <i>TotalLines</i>.


### -param Offset [in]

Specifies the location in the target's memory of the instructions to disassemble.  The disassembly output will start <i>PreviousLines</i> lines before these processor instructions.


### -param Flags [in]

Specifies the bit-flags that affect the behavior of this method.  The following table lists the bits that can be set.

<table>
<tr>
<th>Bit-Flag</th>
<th>Effect when set</th>
</tr>
<tr>
<td>
DEBUG_DISASM_EFFECTIVE_ADDRESS

</td>
<td>
Compute the effective address of each instruction from the current register information and output it.

</td>
</tr>
<tr>
<td>
DEBUG_DISASM_MATCHING_SYMBOLS

</td>
<td>
If the address of an instruction has an exact symbol match, output the symbol.

</td>
</tr>
<tr>
<td>
DEBUG_DISASM_SOURCE_LINE_NUMBER

</td>
<td>
Include the source line number of each instruction in the output.

</td>
</tr>
<tr>
<td>
DEBUG_DISASM_SOURCE_FILE_NAME

</td>
<td>
Include the source file name in the output.

</td>
</tr>
</table>
 


### -param OffsetLine [out, optional]

Receives the line number in the output that contains the instruction at <i>Offset</i>.  If <i>OffsetLine</i> is <b>NULL</b>, this information is not returned.


### -param StartOffset [out, optional]

Receives the location in the target's memory of the first instruction included in the output.  If <i>StartOffset</i> is <b>NULL</b>, this information is not returned.


### -param EndOffset [out, optional]

Receives the locaiton in the target's memory of the instruction that follows the last disassembled instruction.


### -param LineOffsets [out, optional]

Receives the locations in the target's memory of the instructions included in the output starting with the instruction at <i>Offset</i>.  <i>LineOffsets</i> is an array that contains <i>TotalLines</i> elements.

<i>Offset</i> is the value of first entry in this array unless there was an error disassembling the instructions before this instruction. In this case, the first entry will contain DEBUG_ANY_ID and <i>Offset</i> will be placed in the second entry in the array (index one).

If the output for an instruction spans multiple lines, the element in the array that corresponds to the first line of the instruction will contain the address of the instruction. 

If <i>LineOffsets</i> is <b>NULL</b>, this information is not returned.


## -returns



This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



The assembly language depends on the effective processor type of the target system.  For information about the assembly language, see the processor documentation.

For an overview of using assembly in debugger applications, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-in-assembly-mode">Debugging in Assembly Mode</a>.  For more information about using assembly with the debugger engine API, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/assembling-and-disassembling-instructions">Assembling and Disassembling Instructions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-disassemble">Disassemble</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-outputdisassembly">OutputDisassembly</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/u--unassemble-">u (Unassemble)</a>
 

 

