---
UID: NF:dbgeng.IDebugControl3.OutputDisassembly
title: IDebugControl3::OutputDisassembly (dbgeng.h)
description: The OutputDisassembly method disassembles a processor instruction and sends the disassembly to the output callbacks.
old-location: debugger\outputdisassembly.htm
tech.root: debugger
ms.assetid: 2a9944a4-3885-4e83-b20e-040cffcbf85b
ms.date: 05/03/2018
ms.keywords: IDebugControl interface [Windows Debugging],OutputDisassembly method, IDebugControl2 interface [Windows Debugging],OutputDisassembly method, IDebugControl2::OutputDisassembly, IDebugControl3 interface [Windows Debugging],OutputDisassembly method, IDebugControl3.OutputDisassembly, IDebugControl3::OutputDisassembly, IDebugControl::OutputDisassembly, IDebugControl_9f2641b6-ca40-4f1f-85e6-911bb0ab82f8.xml, OutputDisassembly, OutputDisassembly method [Windows Debugging], OutputDisassembly method [Windows Debugging],IDebugControl interface, OutputDisassembly method [Windows Debugging],IDebugControl2 interface, OutputDisassembly method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::OutputDisassembly, dbgeng/IDebugControl3::OutputDisassembly, dbgeng/IDebugControl::OutputDisassembly, debugger.outputdisassembly
f1_keywords:
 - "dbgeng/IDebugControl.OutputDisassembly"
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
- IDebugControl.OutputDisassembly
- IDebugControl2.OutputDisassembly
- IDebugControl3.OutputDisassembly
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::OutputDisassembly


## -description


The <b>OutputDisassembly</b> method disassembles a processor instruction and sends the disassembly to the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">output callbacks</a>.


## -parameters




### -param OutputControl [in]

Specifies the output control that determines which client's output callbacks receive the output.  For possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.  For more information about output, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/input-and-output">Input and Output</a>.


### -param Offset [in]

Specifies the location in the target's memory of the instruction to disassemble.


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
Compute the effective address from the current register information and display it.

</td>
</tr>
<tr>
<td>
DEBUG_DISASM_MATCHING_SYMBOLS

</td>
<td>
If the address of the instruction has an exact symbol match, output the symbol.

</td>
</tr>
<tr>
<td>
DEBUG_DISASM_SOURCE_LINE_NUMBER

</td>
<td>
Include the source line number of the instruction in the output.

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
 


### -param EndOffset [out]

Receives the location in the target's memory of the instruction that follows the disassembled instruction.


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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-outputdisassemblylines">OutputDisassemblyLines</a>
 

 

