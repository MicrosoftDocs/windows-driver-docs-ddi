---
UID: NF:dbgeng.IDebugControl.Disassemble
title: IDebugControl::Disassemble method
author: windows-driver-content
description: The Disassemble method disassembles a processor instruction in the target's memory.
old-location: debugger\disassemble.htm
old-project: debugger
ms.assetid: a512c846-6896-48ca-a234-b9a30a3bff06
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: Disassemble method [Windows Debugging], Disassemble method [Windows Debugging], IDebugControl interface, Disassemble method [Windows Debugging], IDebugControl2 interface, Disassemble method [Windows Debugging], IDebugControl3 interface, Disassemble,IDebugControl.Disassemble, IDebugControl, IDebugControl interface [Windows Debugging], Disassemble method, IDebugControl2 interface [Windows Debugging], Disassemble method, IDebugControl2::Disassemble, IDebugControl3 interface [Windows Debugging], Disassemble method, IDebugControl3::Disassemble, IDebugControl::Disassemble, IDebugControl_7eb9fdc3-f2a0-4239-a035-9abb8e85cd28.xml, dbgeng/IDebugControl2::Disassemble, dbgeng/IDebugControl3::Disassemble, dbgeng/IDebugControl::Disassemble, debugger.disassemble
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
-	IDebugControl.Disassemble
-	IDebugControl2.Disassemble
-	IDebugControl3.Disassemble
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl::Disassemble method


## -description


The <b>Disassemble</b>  method disassembles a processor instruction in the target's memory.


## -syntax


````
HRESULT Disassemble(
  [in]            ULONG64  Offset,
  [in]            ULONG    Flags,
  [out, optional] PSTR     Buffer,
  [in]            ULONG    BufferSize,
  [out, optional] PULONG   DisassemblySize,
  [out]           PULONG64 EndOffset
);
````


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

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="https://msdn.microsoft.com/933a308c-61d1-4ca4-89c1-5749ba1b41c1">u (Unassemble)</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538121">Assemble</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>



 

 


