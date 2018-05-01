---
UID: NF:dbgeng.IDebugControl4.DisassembleWide
title: IDebugControl4::DisassembleWide
author: windows-driver-content
description: The DisassembleWide method disassembles a processor instruction in the target's memory.
old-location: debugger\disassemblewide.htm
old-project: debugger
ms.assetid: 7df1f9e5-dac2-490b-9eed-28f8bc4e677a
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: DisassembleWide, DisassembleWide method [Windows Debugging], DisassembleWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],DisassembleWide method, IDebugControl4.DisassembleWide, IDebugControl4::DisassembleWide, dbgeng/IDebugControl4::DisassembleWide, debugger.disassemblewide
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
-	IDebugControl4.DisassembleWide
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::DisassembleWide


## -description


The <b>DisassembleWide</b>  method disassembles a processor instruction in the target's memory.


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

The disassembly options--returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>--affect the operation of this method.

For an overview of using assembly in debugger applications, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540661">Debugging in Assembly Mode</a>.  For more information about using assembly with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538127">Assembling and Disassembling Instructions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538121">Assemble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>



<a href="https://msdn.microsoft.com/933a308c-61d1-4ca4-89c1-5749ba1b41c1">u (Unassemble)</a>
 

 

