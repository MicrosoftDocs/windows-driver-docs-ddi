---
UID: NF:dbgeng.IDebugControl3.GetAssemblyOptions
title: IDebugControl3::GetAssemblyOptions (dbgeng.h)
description: The GetAssemblyOptions method returns the assembly and disassembly options that affect how the debugger engine assembles and disassembles processor instructions for the target.
old-location: debugger\getassemblyoptions.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl3::GetAssemblyOptions"]
ms.keywords: GetAssemblyOptions, GetAssemblyOptions method [Windows Debugging], GetAssemblyOptions method [Windows Debugging],IDebugControl3 interface, IDebugControl3 interface [Windows Debugging],GetAssemblyOptions method, IDebugControl3.GetAssemblyOptions, IDebugControl3::GetAssemblyOptions, IDebugControl_600ee4dc-0a79-42a9-a394-2ff053874f00.xml, dbgeng/IDebugControl3::GetAssemblyOptions, debugger.getassemblyoptions
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
 - IDebugControl3::GetAssemblyOptions
 - dbgeng/IDebugControl3::GetAssemblyOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl3.GetAssemblyOptions
---

# IDebugControl3::GetAssemblyOptions


## -description

The <b>GetAssemblyOptions</b> method returns the assembly and disassembly options that affect how the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a> assembles and disassembles processor instructions for the target.

## -parameters

### -param Options 

[out]
Receives a bit-set that contains the assembly and disassembly options.  For a description of these options, see <a href="/previous-versions/ff541443(v=vs.85)">DEBUG_ASMOPT_XXX</a>.

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

## -see-also

<a href="/windows-hardware/drivers/debugger/-asm--change-disassembly-options-">.asm (Change Disassembly Options)</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-addassemblyoptions">AddAssemblyOptions</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-assemble">Assemble</a>



<a href="/previous-versions/ff541443(v=vs.85)">DEBUG_ASMOPT_XXX</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-disassemble">Disassemble</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removeassemblyoptions">RemoveAssemblyOptions</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setassemblyoptions">SetAssemblyOptions</a>
