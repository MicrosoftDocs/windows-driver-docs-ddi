---
UID: NF:dbgeng.IDebugControl3.OutputDisassembly
title: IDebugControl3::OutputDisassembly method
author: windows-driver-content
description: The OutputDisassembly method disassembles a processor instruction and sends the disassembly to the output callbacks.
old-location: debugger\outputdisassembly.htm
old-project: debugger
ms.assetid: 2a9944a4-3885-4e83-b20e-040cffcbf85b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDebugControl interface [Windows Debugging], OutputDisassembly method, IDebugControl2 interface [Windows Debugging], OutputDisassembly method, IDebugControl2::OutputDisassembly, IDebugControl3, IDebugControl3 interface [Windows Debugging], OutputDisassembly method, IDebugControl3::OutputDisassembly, IDebugControl::OutputDisassembly, IDebugControl_9f2641b6-ca40-4f1f-85e6-911bb0ab82f8.xml, OutputDisassembly method [Windows Debugging], OutputDisassembly method [Windows Debugging], IDebugControl interface, OutputDisassembly method [Windows Debugging], IDebugControl2 interface, OutputDisassembly method [Windows Debugging], IDebugControl3 interface, OutputDisassembly,IDebugControl3.OutputDisassembly, dbgeng/IDebugControl2::OutputDisassembly, dbgeng/IDebugControl3::OutputDisassembly, dbgeng/IDebugControl::OutputDisassembly, debugger.outputdisassembly
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl.OutputDisassembly
-	IDebugControl2.OutputDisassembly
-	IDebugControl3.OutputDisassembly
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::OutputDisassembly method


## -description


The <b>OutputDisassembly</b> method disassembles a processor instruction and sends the disassembly to the <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">output callbacks</a>.


## -syntax


````
HRESULT OutputDisassembly(
  [in]  ULONG    OutputControl,
  [in]  ULONG64  Offset,
  [in]  ULONG    Flags,
  [out] PULONG64 EndOffset
);
````


## -parameters




### -param OutputControl [in]

Specifies the output control that determines which client's output callbacks receive the output.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.  For more information about output, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.


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
</table>
 




## -remarks



The assembly language depends on the effective processor type of the target system.  For information about the assembly language, see the processor documentation.

For an overview of using assembly in debugger applications, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540661">Debugging in Assembly Mode</a>.  For more information about using assembly with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538127">Assembling and Disassembling Instructions</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541948">Disassemble</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553216">OutputDisassemblyLines</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::OutputDisassembly method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

