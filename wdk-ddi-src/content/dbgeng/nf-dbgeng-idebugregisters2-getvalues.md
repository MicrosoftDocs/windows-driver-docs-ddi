---
UID: NF:dbgeng.IDebugRegisters2.GetValues
title: IDebugRegisters2::GetValues (dbgeng.h)
description: The GetValues method gets the value of several of the target's registers.
old-location: debugger\getvalues.htm
tech.root: debugger
ms.assetid: d78c54a7-04a5-4c51-bf33-a5b7fb937897
ms.date: 05/03/2018
ms.keywords: GetValues, GetValues method [Windows Debugging], GetValues method [Windows Debugging],IDebugRegisters interface, GetValues method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters interface [Windows Debugging],GetValues method, IDebugRegisters2 interface [Windows Debugging],GetValues method, IDebugRegisters2.GetValues, IDebugRegisters2::GetValues, IDebugRegisters::GetValues, IDebugRegisters_46e390ee-fd0c-4f5f-babc-d76c10ca2780.xml, dbgeng/IDebugRegisters2::GetValues, dbgeng/IDebugRegisters::GetValues, debugger.getvalues
ms.topic: method
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
- IDebugRegisters.GetValues
- IDebugRegisters2.GetValues
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugRegisters2::GetValues


## -description


The <b>GetValues</b> method gets the value of several of the target's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">registers</a>.


## -parameters




### -param Count [in]

Specifies the number of registers whose values are requested.


### -param Indices [in, optional]

Specifies an array that contains the indices of the registers from which to get the values.  The number of elements in this array is <i>Count</i>.  If <i>Indices</i> is <b>NULL</b>, <i>Start</i> is used instead.


### -param Start [in]

If <i>Indices</i> is <b>NULL</b>, the registers will be read consecutively starting at this index.  Otherwise it is ignored.


### -param Values [out]

Receives the values of the registers.  The number of elements this array holds is <i>Count</i>.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541719">DEBUG_VALUE</a> for a description of this parameter type.


## -returns



This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.

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
The target is not accessible, or one of the registers could not be accessed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The value of the index of one of the registers is greater than the number of registers on the target machine.  Partial results might have been obtained; those registers that could not be read will have the type DEBUG_VALUE_INVALID.

</td>
</tr>
</table>
 




## -remarks



<b>GetValues</b> gets the value of several of the target's registers.

If the return value is not S_OK, some of the registers still might have been read.  If the target was not accessible, the return type is E_UNEXPECTED and <i>Values</i> is unchanged; otherwise, <i>Values</i> will contain partial results and the registers that could not be read will have type DEBUG_VALUE_INVALID.  Ambiguity in the case of the return value E_UNEXPECTED can be avoided by setting the memory of <i>Values</i> to zero before calling this method.

To receive the value of only a single register, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff597624">GetValue</a> method instead.

The method <a href="https://msdn.microsoft.com/library/windows/hardware/ff549487">GetValues2</a> performs the same task as this method but also allows the register source to be specified.

For an overview of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550825">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff597624">GetValue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549487">GetValues2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550825">IDebugRegisters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550835">IDebugRegisters2</a>
 

 

