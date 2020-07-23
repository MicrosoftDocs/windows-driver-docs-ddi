---
UID: NF:dbgeng.IDebugRegisters2.SetValues
title: IDebugRegisters2::SetValues (dbgeng.h)
description: The SetValues method sets the value of several of the target's registers.
old-location: debugger\setvalues.htm
tech.root: debugger
ms.assetid: 8f3817e7-8409-4b75-be28-ac7fe32145cb
ms.date: 05/03/2018
keywords: ["IDebugRegisters2::SetValues"]
ms.keywords: IDebugRegisters interface [Windows Debugging],SetValues method, IDebugRegisters2 interface [Windows Debugging],SetValues method, IDebugRegisters2.SetValues, IDebugRegisters2::SetValues, IDebugRegisters::SetValues, IDebugRegisters_0c188698-35b8-4c8f-ad8c-1218695845a8.xml, SetValues, SetValues method [Windows Debugging], SetValues method [Windows Debugging],IDebugRegisters interface, SetValues method [Windows Debugging],IDebugRegisters2 interface, dbgeng/IDebugRegisters2::SetValues, dbgeng/IDebugRegisters::SetValues, debugger.setvalues
f1_keywords:
 - "dbgeng/IDebugRegisters.SetValues"
 - "IDebugRegisters.SetValues"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugRegisters.SetValues
- IDebugRegisters2.SetValues
targetos: Windows
req.typenames: 
---

# IDebugRegisters2::SetValues


## -description


The <b>SetValues</b> method sets the value of several of the target's <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registers">registers</a>.


## -parameters




### -param Count [in]

Specifies the number of registers for which to set the values.


### -param Indices [in, optional]

Specifies an array that contains the indices of the registers for which to set the values.  The number of elements in this array is <i>Count</i>.  If <i>Indices</i> is <b>NULL</b>, <i>Start</i> is used instead.


### -param Start [in]

If <i>Indices</i> is <b>NULL</b>, the registers will be set consecutively starting at this index.  Otherwise it is ignored.


### -param Values [in]

Specifies the array that contains values to which to set the registers.  The number of elements this array holds is <i>Count</i>.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_value">DEBUG_VALUE</a> for a description of this parameter type.


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
The target is not accessible, or one or more of the registers could not be accessed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The value of the index of one or more of the registers is greater than the number of registers on the target machine.

</td>
</tr>
</table>
 




## -remarks



The engine does its best to coerce the values in <i>Values</i> into the type of the registers; this coercion is the same as that performed by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-coercevalue">CoerceValue</a>.  If the value is larger than what the register can hold, the least significant bits are dropped.  Floating-point and integer conversions will also be performed if necessary.  

If the return value is not S_OK, some of the registers still might have been set.  

When a subregister is altered, the register containing it is also altered.

To set the value of only a single register, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setvalue">SetValue</a> method instead.

The method <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-setvalues2">SetValues2</a> performs the same task as this method but also allows the register source to be specified.

For an overview of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registers">Registers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters2">IDebugRegisters2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setvalue">SetValue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-setvalues2">SetValues2</a>
 

 

