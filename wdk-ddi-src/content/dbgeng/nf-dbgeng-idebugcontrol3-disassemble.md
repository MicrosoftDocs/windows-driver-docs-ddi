---
UID: NF:dbgeng.IDebugControl3.Disassemble
title: IDebugControl3::Disassemble (dbgeng.h)
description: The Disassemble method disassembles a processor instruction in the target's memory.
old-location: debugger\disassemble.htm
tech.root: debugger
ms.assetid: a512c846-6896-48ca-a234-b9a30a3bff06
ms.date: 05/03/2018
ms.keywords: Disassemble, Disassemble method [Windows Debugging], Disassemble method [Windows Debugging],IDebugControl interface, Disassemble method [Windows Debugging],IDebugControl2 interface, Disassemble method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],Disassemble method, IDebugControl2 interface [Windows Debugging],Disassemble method, IDebugControl2::Disassemble, IDebugControl3 interface [Windows Debugging],Disassemble method, IDebugControl3.Disassemble, IDebugControl3::Disassemble, IDebugControl::Disassemble, IDebugControl_7eb9fdc3-f2a0-4239-a035-9abb8e85cd28.xml, dbgeng/IDebugControl2::Disassemble, dbgeng/IDebugControl3::Disassemble, dbgeng/IDebugControl::Disassemble, debugger.disassemble
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl.Disassemble"
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
- IDebugControl.Disassemble
- IDebugControl2.Disassemble
- IDebugControl3.Disassemble
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::Disassemble


## -description


The <b>Disassemble</b>  method disassembles a processor instruction in the target's memory.


## -parameters




### -param Offset [in]

Specifies the location in the target's memory of the instruction to disassemble.


### -param Flags [in]

Specifies the bit-flags that affect the behavior of this method.  Currently the only flag that can be set is DEBUG_DISASM_EFFECTIVE_ADDRESS; when set, the engine will compute the effective address from the current register information and display it.


### -param Buffer [out, optional]

Receives the disassembled instruction.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param DisassemblySize [out, optional]

Receives the size, in characters, of the disassembled instruction.  If <i>DisassemblySize</i> is <b>NULL</b>, this information is not returned.


### -param EndOffset [out]

Receives the location in the target's memory of the instruction following the disassembled instruction.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, <i>Buffer</i> was too small to hold the disassembled instruction and the instruction was truncated to fit.

</td>
</tr>
</table>
 




## -remarks



The assembly language depends on the effective processor type of the target system.  For information about the assembly language, see the processor documentation.

The disassembly options--returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getassemblyoptions">GetAssemblyOptions</a>--affect the operation of this method.

For an overview of using assembly in debugger applications, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-in-assembly-mode">Debugging in Assembly Mode</a>.  For more information about using assembly with the debugger engine API, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/assembling-and-disassembling-instructions">Assembling and Disassembling Instructions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-assemble">Assemble</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getassemblyoptions">GetAssemblyOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/u--unassemble-">u (Unassemble)</a>
 

 

