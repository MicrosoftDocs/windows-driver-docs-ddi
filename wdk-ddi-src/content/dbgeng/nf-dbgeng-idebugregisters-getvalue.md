---
UID: NF:dbgeng.IDebugRegisters.GetValue
title: IDebugRegisters::GetValue (dbgeng.h)
description: The GetValue method gets the value of one of the target's registers.
old-location: debugger\getvalue.htm
tech.root: debugger
ms.assetid: 227d7b4f-bf94-4763-bb1f-32efbc087bb1
ms.date: 05/03/2018
keywords: ["IDebugRegisters::GetValue"]
ms.keywords: GetValue, GetValue method [Windows Debugging], GetValue method [Windows Debugging],IDebugRegisters interface, GetValue method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters interface [Windows Debugging],GetValue method, IDebugRegisters.GetValue, IDebugRegisters2 interface [Windows Debugging],GetValue method, IDebugRegisters2::GetValue, IDebugRegisters::GetValue, IDebugRegisters_f3e89ca1-7516-476e-8c85-560d8f28f0a8.xml, dbgeng/IDebugRegisters2::GetValue, dbgeng/IDebugRegisters::GetValue, debugger.getvalue
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
 - IDebugRegisters::GetValue
 - dbgeng/IDebugRegisters::GetValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugRegisters.GetValue
 - IDebugRegisters2.GetValue
---

# IDebugRegisters::GetValue


## -description

The <b>GetValue</b> method gets the value of one of the target's <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registers">registers</a>.

## -parameters

### -param Register 

[in]
Specifies the index of the register whose value is requested.

### -param Value 

[out]
Receives the value of the register.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_value">DEBUG_VALUE</a> for a description of this parameter type.

## -returns

This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">HRESULT Values</a>.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
The target is not accessible, or the register could not be accessed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The value of Register is greater than the number of registers on the target machine.

</td>
</tr>
</table>

## -remarks

To receive the values of multiple registers, use the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getvalues">GetValues</a> method instead.

For an overview of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registers">Registers</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getvalues">GetValues</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getvalues2">GetValues2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters2">IDebugRegisters2</a>

