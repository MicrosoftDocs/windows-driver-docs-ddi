---
UID: NF:dbgeng.IDebugControl2.Assemble
title: IDebugControl2::Assemble method
author: windows-driver-content
description: The Assemble method assembles a single processor instruction. The assembled instruction is placed in the target's memory.
old-location: debugger\assemble.htm
old-project: debugger
ms.assetid: 4d7d84e7-4fa4-4514-9d52-dbae5fed159b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: Assemble method [Windows Debugging], Assemble method [Windows Debugging], IDebugControl interface, Assemble method [Windows Debugging], IDebugControl2 interface, Assemble method [Windows Debugging], IDebugControl3 interface, Assemble,IDebugControl2.Assemble, IDebugControl interface [Windows Debugging], Assemble method, IDebugControl2, IDebugControl2 interface [Windows Debugging], Assemble method, IDebugControl2::Assemble, IDebugControl3 interface [Windows Debugging], Assemble method, IDebugControl3::Assemble, IDebugControl::Assemble, IDebugControl_99336950-ba0b-46e1-871d-582f08ab5519.xml, dbgeng/IDebugControl2::Assemble, dbgeng/IDebugControl3::Assemble, dbgeng/IDebugControl::Assemble, debugger.assemble
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
-	IDebugControl.Assemble
-	IDebugControl2.Assemble
-	IDebugControl3.Assemble
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::Assemble method


## -description


The <b>Assemble</b> method assembles a single processor instruction.  The assembled instruction is placed in the target's memory.


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
      The <b>Assemble</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff538126">AssembleWide</a> methods are not supported on some architectures, and on some other architectures not all instructions are supported.</div>
<div> </div>
The assembly language options--returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>--affect the operation of this method.

For an overview of using assembly in debugger applications, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540661">Debugging in Assembly Mode</a>.  For more information about using assembly with the <a href="https://msdn.microsoft.com/e4d53375-c82e-493b-9ccb-444c211fbc79">debugger engine API</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538127">Assembling and Disassembling Instructions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541948">Disassemble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::Assemble method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
