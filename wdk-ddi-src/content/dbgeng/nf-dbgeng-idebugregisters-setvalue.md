---
UID: NF:dbgeng.IDebugRegisters.SetValue
title: IDebugRegisters::SetValue
author: windows-driver-content
description: The SetValue method sets the value of one of the target's registers.
old-location: debugger\setvalue.htm
tech.root: debugger
ms.assetid: 78c7bdea-cba5-40df-b9d7-09c7d98b0403
ms.date: 5/3/2018
ms.keywords: IDebugRegisters interface [Windows Debugging],SetValue method, IDebugRegisters.SetValue, IDebugRegisters2 interface [Windows Debugging],SetValue method, IDebugRegisters2::SetValue, IDebugRegisters::SetValue, IDebugRegisters_f704c31f-5062-47d7-9f44-35bc85e0d0aa.xml, SetValue, SetValue method [Windows Debugging], SetValue method [Windows Debugging],IDebugRegisters interface, SetValue method [Windows Debugging],IDebugRegisters2 interface, dbgeng/IDebugRegisters2::SetValue, dbgeng/IDebugRegisters::SetValue, debugger.setvalue
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugRegisters.SetValue
-	IDebugRegisters2.SetValue
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugRegisters::SetValue


## -description


The <b>SetValue</b> method sets the value of one of the target's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">registers</a>.


## -parameters




### -param Register [in]

Specifies the index of the register whose value is to be set.


### -param Value [in]

Specifies the value to which to set the register.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541719">DEBUG_VALUE</a> for a description of this parameter type.


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
The value of <i>Register</i> is greater than the number of registers on the target machine.

</td>
</tr>
</table>
 




## -remarks



The engine does its best to coerce the value of <i>Value</i> into the type of the register; this coercion is the same as that performed by <a href="https://msdn.microsoft.com/library/windows/hardware/ff539158">CoerceValue</a>.  If the value is larger than what the register can hold, the least significant bits are dropped.  Floating-point and integer conversions will also be performed if necessary.  

When a subregister is altered, the register containing it is also altered.

To set the values of multiple registers, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556883">SetValues</a> method instead.

For an overview of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550825">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550825">IDebugRegisters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550835">IDebugRegisters2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556883">SetValues</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556884">SetValues2</a>
 

 

