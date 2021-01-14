---
UID: NF:dbgeng.IDebugRegisters2.OutputRegisters
title: IDebugRegisters2::OutputRegisters (dbgeng.h)
description: The OutputRegisters method formats and sends the target's registers to the clients as output.
old-location: debugger\outputregisters.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugRegisters2::OutputRegisters"]
ms.keywords: IDebugRegisters interface [Windows Debugging],OutputRegisters method, IDebugRegisters2 interface [Windows Debugging],OutputRegisters method, IDebugRegisters2.OutputRegisters, IDebugRegisters2::OutputRegisters, IDebugRegisters::OutputRegisters, IDebugRegisters_65d62961-afc5-4609-86d2-c55757fe6ce1.xml, OutputRegisters, OutputRegisters method [Windows Debugging], OutputRegisters method [Windows Debugging],IDebugRegisters interface, OutputRegisters method [Windows Debugging],IDebugRegisters2 interface, dbgeng/IDebugRegisters2::OutputRegisters, dbgeng/IDebugRegisters::OutputRegisters, debugger.outputregisters
req.header: dbgeng.h
req.include-header: DbgEng.h
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
 - IDebugRegisters2::OutputRegisters
 - dbgeng/IDebugRegisters2::OutputRegisters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugRegisters2::OutputRegisters
---

# IDebugRegisters2::OutputRegisters


## -description

The <b>OutputRegisters</b> method formats and sends the target's <a href="/windows-hardware/drivers/debugger/registers">registers</a> to the clients as output.

## -parameters

### -param OutputControl 

[in]
Specifies which clients should be sent the output of the formatted registers.  See <a href="/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a> for possible values.

### -param Flags 

[in]
Specifies which set of registers to print.  This can either be DEBUG_REGISTERS_DEFAULT to print commonly used registers, DEBUG_REGISTERS_ALL to print all the sets of registers, or a combination of the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_REGISTERS_INT32

</td>
<td>
Print the 32-bit register set.

</td>
</tr>
<tr>
<td>
DEBUG_REGISTERS_INT64

</td>
<td>
Print the 64-bit register set.

</td>
</tr>
<tr>
<td>
DEBUG_REGISTERS_FLOAT

</td>
<td>
Print the floating-point register set.

</td>
</tr>
</table>

## -returns

This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="/windows-hardware/drivers/debugger/hresult-values">HRESULT Values</a>.

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

The registers are formatted in a way that is specific to the target architecture's register set.

The method <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-outputregisters2">OutputRegisters2</a> performs the same task as this method but also allows the register source to be specified.

For an overview of the <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="/windows-hardware/drivers/debugger/registers">Registers</a>.  For details on sending output to the clients, see <a href="/windows-hardware/drivers/debugger/input-and-output">Input and Output</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters2">IDebugRegisters2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-outputregisters2">OutputRegisters2</a>

