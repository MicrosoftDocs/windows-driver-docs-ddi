---
UID: NF:dbgeng.IDebugRegisters2.OutputRegisters2
title: IDebugRegisters2::OutputRegisters2 (dbgeng.h)
description: The OutputRegisters2 method formats and outputs the target's registers.
old-location: debugger\outputregisters2.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugRegisters2::OutputRegisters2"]
ms.keywords: IDebugRegisters2 interface [Windows Debugging],OutputRegisters2 method, IDebugRegisters2.OutputRegisters2, IDebugRegisters2::OutputRegisters2, IDebugRegisters_ecc2b40a-622b-4f1f-867b-2eb6b575559d.xml, OutputRegisters2, OutputRegisters2 method [Windows Debugging], OutputRegisters2 method [Windows Debugging],IDebugRegisters2 interface, dbgeng/IDebugRegisters2::OutputRegisters2, debugger.outputregisters2
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
 - IDebugRegisters2::OutputRegisters2
 - dbgeng/IDebugRegisters2::OutputRegisters2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugRegisters2.OutputRegisters2
---

# IDebugRegisters2::OutputRegisters2


## -description

The <b>OutputRegisters2</b> method formats and outputs the target's <a href="/windows-hardware/drivers/debugger/registers">registers</a>.

## -parameters

### -param OutputControl 

[in]
Specifies which clients should be sent the output of the formatted registers.  See <a href="/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a> for possible values.

### -param Source 

[in]
Specifies the register source to query.

The possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Register source</th>
</tr>
<tr>
<td>
DEBUG_REGSRC_DEBUGGEE

</td>
<td>
Fetch register information from the target.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_EXPLICIT

</td>
<td>
Fetch register information from the current explicit <a href="/windows-hardware/drivers/debugger/changing-contexts">register context</a>.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_FRAME

</td>
<td>
Fetch register information from the current scope's register context.

<div class="alert"><b>Note</b>    Stack unwinding does not guarantee accurate updating of the register context, so the scope frame's register context might not be accurate in all cases.</div>
<div> </div>
</td>
</tr>
</table>

### -param Flags 

[in]
Specifies which register sets to print.  This can either be DEBUG_REGISTERS_DEFAULT to print commonly used registers, DEBUG_REGISTERS_ALL to print all of the register sets, or a combination of the values listed in the following table.

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

The method <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-outputregisters">OutputRegisters</a> performs the same task as this method but always uses the target as the register source.

For an overview of the <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="/windows-hardware/drivers/debugger/registers">Registers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters2">IDebugRegisters2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-outputregisters">OutputRegisters</a>
