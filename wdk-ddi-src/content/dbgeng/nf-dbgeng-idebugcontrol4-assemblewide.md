---
UID: NF:dbgeng.IDebugControl4.AssembleWide
title: IDebugControl4::AssembleWide method
author: windows-driver-content
description: The AssembleWide method assembles a single processor instruction. The assembled instruction is placed in the target's memory.
old-location: debugger\assemblewide.htm
old-project: debugger
ms.assetid: 6ba291d7-c3e7-4f76-afc3-bf200bae2a8f
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: AssembleWide method [Windows Debugging], AssembleWide method [Windows Debugging], IDebugControl4 interface, AssembleWide,IDebugControl4.AssembleWide, IDebugControl4, IDebugControl4 interface [Windows Debugging], AssembleWide method, IDebugControl4::AssembleWide, dbgeng/IDebugControl4::AssembleWide, debugger.assemblewide
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
-	Dbgeng.h
api_name:
-	IDebugControl4.AssembleWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::AssembleWide method


## -description


The <b>AssembleWide</b> method assembles a single processor instruction.  The assembled instruction is placed in the target's memory.


## -parameters




### -param Offset [in]

Specifies the location in the target's memory to place the assembled instruction.


### -param Instr [in]

Specifies the instruction to assemble.  The instruction is assembled according to the target's effective processor type (returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff556657">SetEffectiveProcessorType</a>).


### -param EndOffset [out]

Receives the location in the target's memory immediately following the assembled instruction.  <i>EndOffset</i> can be used when assembling multiple instructions.


## -returns



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
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



The assembly language depends on the effective processor type of the target machine.  For information about the assembly language, see the processor documentation.

<div class="alert"><b>Note</b>  
      The <a href="https://msdn.microsoft.com/library/windows/hardware/ff538121">Assemble</a> and <b>AssembleWide</b> methods are not supported on some architectures, and on some other architectures not all instructions are supported.</div>
<div> </div>
The assembly language options--returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>--affect the operation of this method.

For an overview of using assembly in debugger applications, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540661">Debugging in Assembly Mode</a>.  For more information about using assembly with the <a href="https://msdn.microsoft.com/e4d53375-c82e-493b-9ccb-444c211fbc79">debugger engine API</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538127">Assembling and Disassembling Instructions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541948">Disassemble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
 

 

