---
UID: NF:dbgeng.IDebugControl3.AddAssemblyOptions
title: IDebugControl3::AddAssemblyOptions (dbgeng.h)
description: The AddAssemblyOptions method turns on some of the assembly and disassembly options.
old-location: debugger\addassemblyoptions.htm
tech.root: debugger
ms.assetid: 9274c3eb-a5c0-43a9-a9d4-541482ddace1
ms.date: 05/03/2018
keywords: ["IDebugControl3::AddAssemblyOptions"]
ms.keywords: AddAssemblyOptions, AddAssemblyOptions method [Windows Debugging], AddAssemblyOptions method [Windows Debugging],IDebugControl3 interface, IDebugControl3 interface [Windows Debugging],AddAssemblyOptions method, IDebugControl3.AddAssemblyOptions, IDebugControl3::AddAssemblyOptions, IDebugControl_9cacf343-5c88-4a06-8f68-7c94b15419b8.xml, dbgeng/IDebugControl3::AddAssemblyOptions, debugger.addassemblyoptions
f1_keywords:
 - "dbgeng/IDebugControl3.AddAssemblyOptions"
 - "IDebugControl3.AddAssemblyOptions"
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
- Dbgeng.h
api_name:
- IDebugControl3.AddAssemblyOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::AddAssemblyOptions


## -description


The <b>AddAssemblyOptions</b> method turns on some of the assembly and disassembly options.


## -parameters




### -param Options [in]

Specifies the assembly and disassembly options to turn on.  <i>Options</i> is a bit-set that will be combined with the existing engine options using the bitwise OR operator.  For a description of the options, see <a href="https://docs.microsoft.com/previous-versions/ff541443(v=vs.85)">DEBUG_ASMOPT_XXX</a>.


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
 

These methods can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



For more information about using assembly with the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/d">debugger engine API</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/assembling-and-disassembling-instructions">Assembling and Disassembling Instructions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-asm--change-disassembly-options-">.asm (Change Disassembly Options)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-assemble">Assemble</a>



<a href="https://docs.microsoft.com/previous-versions/ff541443(v=vs.85)">DEBUG_ASMOPT_XXX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-disassemble">Disassemble</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getassemblyoptions">GetAssemblyOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removeassemblyoptions">RemoveAssemblyOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setassemblyoptions">SetAssemblyOptions</a>
 

 

