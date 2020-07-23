---
UID: NF:dbgeng.IDebugControl3.RemoveAssemblyOptions
title: IDebugControl3::RemoveAssemblyOptions (dbgeng.h)
description: The RemoveAssemblyOptions method turns off some of the assembly and disassembly options.
old-location: debugger\removeassemblyoptions.htm
tech.root: debugger
ms.assetid: 0352b418-26ee-4f35-a171-1b456a115014
ms.date: 05/03/2018
keywords: ["IDebugControl3::RemoveAssemblyOptions"]
ms.keywords: IDebugControl3 interface [Windows Debugging],RemoveAssemblyOptions method, IDebugControl3.RemoveAssemblyOptions, IDebugControl3::RemoveAssemblyOptions, IDebugControl_8d971b27-ff9f-4097-a96a-68dabf08b200.xml, RemoveAssemblyOptions, RemoveAssemblyOptions method [Windows Debugging], RemoveAssemblyOptions method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl3::RemoveAssemblyOptions, debugger.removeassemblyoptions
f1_keywords:
 - "dbgeng/IDebugControl3.RemoveAssemblyOptions"
 - "IDebugControl3.RemoveAssemblyOptions"
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
- IDebugControl3.RemoveAssemblyOptions
targetos: Windows
req.typenames: 
---

# IDebugControl3::RemoveAssemblyOptions


## -description


The <b>RemoveAssemblyOptions</b> method turns off some of the assembly and disassembly options.


## -parameters




### -param Options [in]

Specifies the assembly and disassembly options to turn off.  <i>Options</i> is a bit-set; the new value of the engine's options will equal the bitwise NOT of <i>Options</i> combined with the old value by using the bitwise AND operator.  For a description of the assembly and disassembly options, see <a href="https://docs.microsoft.com/previous-versions/ff541443(v=vs.85)">DEBUG_ASMOPT_XXX</a>.


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
 

This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



For more information about using assembly with the debugger engine API, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/assembling-and-disassembling-instructions">Assembling and Disassembling Instructions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-asm--change-disassembly-options-">.asm (Change Disassembly Options)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-addassemblyoptions">AddAssemblyOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-assemble">Assemble</a>



<a href="https://docs.microsoft.com/previous-versions/ff541443(v=vs.85)">DEBUG_ASMOPT_XXX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-disassemble">Disassemble</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getassemblyoptions">GetAssemblyOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setassemblyoptions">SetAssemblyOptions</a>
 

 

