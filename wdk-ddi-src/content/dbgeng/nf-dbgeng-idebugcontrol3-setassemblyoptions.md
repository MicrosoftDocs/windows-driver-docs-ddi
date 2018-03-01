---
UID: NF:dbgeng.IDebugControl3.SetAssemblyOptions
title: IDebugControl3::SetAssemblyOptions method
author: windows-driver-content
description: The SetAssemblyOptions method sets the assembly and disassembly options that affect how the debugger engine assembles and disassembles processor instructions for the target.
old-location: debugger\setassemblyoptions.htm
old-project: debugger
ms.assetid: ec86ac71-212c-4edd-94c6-bab1cb5fa660
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugControl3, IDebugControl3 interface [Windows Debugging], SetAssemblyOptions method, IDebugControl3::SetAssemblyOptions, IDebugControl_b39768e8-fb98-4056-b548-c568316279e1.xml, SetAssemblyOptions method [Windows Debugging], SetAssemblyOptions method [Windows Debugging], IDebugControl3 interface, SetAssemblyOptions,IDebugControl3.SetAssemblyOptions, dbgeng/IDebugControl3::SetAssemblyOptions, debugger.setassemblyoptions
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
-	IDebugControl3.SetAssemblyOptions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::SetAssemblyOptions method


## -description


The <b>SetAssemblyOptions</b> method sets the assembly and disassembly options that affect how the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> assembles and disassembles processor instructions for the target.


## -syntax


````
HRESULT SetAssemblyOptions(
  [in] ULONG Options
);
````


## -parameters




### -param Options [in]

Specifies the new assembly and disassembly options to be used by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>.  <i>Options</i> is a bit-set; it will replace the existing assembly and disassembly options.  For possible values, see Remarks.  DEBUG_ASMOPT_DEFAULT can be used to set the default options.


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



For more information about using assembly with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538127">Assembling and Disassembling Instructions</a>.

The assembly and disassembly options affect how the debugger engine assembles and disassembles processor instructions for the target.

The options are represented by a bitset with the following bit flags.

<table>
<tr>
<th>Constant</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>DEBUG_ASMOPT_VERBOSE</b>

</td>
<td>
When this bit is set, additional information is included in the disassembly.

This is equivalent to the <b>verbose</b> option in the <b>.asm</b> command.

</td>
</tr>
<tr>
<td>
<b>DEBUG_ASMOPT_NO_CODE_BYTES</b>

</td>
<td>
When this bit is set, the raw bytes for an instruction are not included in the disassembly.

This is equivalent to the <b>no_code_bytes</b> option in the <b>.asm</b> command.

</td>
</tr>
<tr>
<td>
<b>DEBUG_ASMOPT_IGNORE_OUTPUT_WIDTH</b>

</td>
<td>
When this bit is set, the debugger ignores the width of the output display when formatting instructions during disassembly.

This is equivalent to the <b>ignore_output_width</b> option in the <b>.asm</b> command.

</td>
</tr>
<tr>
<td>
<b>DEBUG_ASMOPT_SOURCE_LINE_NUMBER</b>

</td>
<td>
When this bit is set, each line of the disassembly output is prefixed with the line number of the source code provided by symbol information.

This is equivalent to the <b>source_line</b> option in the <b>.asm</b> command.

</td>
</tr>
</table>
 

Additionally, the value DEBUG_ASMOPT_DEFAULT represents the default set of assembly and disassembly options.  This means that all the options in the preceding table are turned off. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554483">RemoveAssemblyOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562128">.asm (Change Disassembly Options)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541948">Disassemble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538121">Assemble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537852">AddAssemblyOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl3::SetAssemblyOptions method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

