---
UID: NF:dbgeng.IDebugControl3.SetAssemblyOptions
title: IDebugControl3::SetAssemblyOptions (dbgeng.h)
description: The SetAssemblyOptions method sets the assembly and disassembly options that affect how the debugger engine assembles and disassembles processor instructions for the target.
old-location: debugger\setassemblyoptions.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl3::SetAssemblyOptions"]
ms.keywords: IDebugControl3 interface [Windows Debugging],SetAssemblyOptions method, IDebugControl3.SetAssemblyOptions, IDebugControl3::SetAssemblyOptions, IDebugControl_b39768e8-fb98-4056-b548-c568316279e1.xml, SetAssemblyOptions, SetAssemblyOptions method [Windows Debugging], SetAssemblyOptions method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl3::SetAssemblyOptions, debugger.setassemblyoptions
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
 - IDebugControl3::SetAssemblyOptions
 - dbgeng/IDebugControl3::SetAssemblyOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl3.SetAssemblyOptions
---

# IDebugControl3::SetAssemblyOptions


## -description

The <b>SetAssemblyOptions</b> method sets the assembly and disassembly options that affect how the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a> assembles and disassembles processor instructions for the target.

## -parameters

### -param Options 

[in]
Specifies the new assembly and disassembly options to be used by the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a>.  <i>Options</i> is a bit-set; it will replace the existing assembly and disassembly options.  For possible values, see Remarks.  DEBUG_ASMOPT_DEFAULT can be used to set the default options.

## -returns

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

For more information about using assembly with the debugger engine API, see <a href="/windows-hardware/drivers/debugger/assembling-and-disassembling-instructions">Assembling and Disassembling Instructions</a>.

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

<a href="/windows-hardware/drivers/debugger/-asm--change-disassembly-options-">.asm (Change Disassembly Options)</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-addassemblyoptions">AddAssemblyOptions</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-assemble">Assemble</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-disassemble">Disassemble</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getassemblyoptions">GetAssemblyOptions</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removeassemblyoptions">RemoveAssemblyOptions</a>
