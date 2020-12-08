---
UID: NF:dbgeng.IDebugSymbols2.OutputTypedDataPhysical
title: IDebugSymbols2::OutputTypedDataPhysical (dbgeng.h)
description: The OutputTypedDataPhysical method formats the contents of a variable in the target computer's physical memory, and then sends this to the output callbacks.
old-location: debugger\outputtypeddataphysical.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols2::OutputTypedDataPhysical"]
ms.keywords: IDebugSymbols interface [Windows Debugging],OutputTypedDataPhysical method, IDebugSymbols2 interface [Windows Debugging],OutputTypedDataPhysical method, IDebugSymbols2.OutputTypedDataPhysical, IDebugSymbols2::OutputTypedDataPhysical, IDebugSymbols3 interface [Windows Debugging],OutputTypedDataPhysical method, IDebugSymbols3::OutputTypedDataPhysical, IDebugSymbols::OutputTypedDataPhysical, IDebugSymbols_35ce4485-6c19-44fd-8382-011b0e620f48.xml, OutputTypedDataPhysical, OutputTypedDataPhysical method [Windows Debugging], OutputTypedDataPhysical method [Windows Debugging],IDebugSymbols interface, OutputTypedDataPhysical method [Windows Debugging],IDebugSymbols2 interface, OutputTypedDataPhysical method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols2::OutputTypedDataPhysical, dbgeng/IDebugSymbols3::OutputTypedDataPhysical, dbgeng/IDebugSymbols::OutputTypedDataPhysical, debugger.outputtypeddataphysical
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
 - IDebugSymbols2::OutputTypedDataPhysical
 - dbgeng/IDebugSymbols2::OutputTypedDataPhysical
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols.OutputTypedDataPhysical
 - IDebugSymbols2.OutputTypedDataPhysical
 - IDebugSymbols3.OutputTypedDataPhysical
---

# IDebugSymbols2::OutputTypedDataPhysical


## -description

The <b>OutputTypedDataPhysical</b> method formats the contents of a variable in the target computer's physical memory, and then sends this to the <a href="/windows-hardware/drivers/debugger/using-input-and-output">output callbacks</a>.

## -parameters

### -param OutputControl 

[in]
Specifies the output control used to determine which output callbacks can receive the output.  See <a href="/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a> for possible values.

### -param Offset 

[in]
Specifies the physical address in the target computer's memory of the variable.

### -param Module 

[in]
Specifies the base address of the module containing the type of the variable.

### -param TypeId 

[in]
Specifies the type ID of the type of the variable.

### -param Flags 

[in]
Specifies the bit-set containing the formatting options.  See <a href="/windows-hardware/drivers/debugger/debug-typeopts-xxx">DEBUG_TYPEOPTS_XXX</a> for possible values.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

This method is only available in kernel mode debugging.

The output produced by this method is the same as for the debugger command <b>DT</b>.  See <a href="/windows-hardware/drivers/debugger/dt--display-type-">dt (Display Type)</a>.

For more information about types, see <a href="/windows-hardware/drivers/debugger/types">Types</a>.  For information about output, see <a href="/windows-hardware/drivers/debugger/input-and-output">Input and Output</a>.
