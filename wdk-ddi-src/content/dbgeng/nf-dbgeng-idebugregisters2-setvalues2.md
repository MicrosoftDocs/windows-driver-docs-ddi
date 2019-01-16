---
UID: NF:dbgeng.IDebugRegisters2.SetValues2
title: IDebugRegisters2::SetValues2
description: The SetValues2 method sets the value of several of the target's registers.
old-location: debugger\setvalues2.htm
tech.root: debugger
ms.assetid: 9505a0ce-4f4e-43af-97a2-653b5776c423
ms.date: 05/03/2018
ms.keywords: IDebugRegisters2 interface [Windows Debugging],SetValues2 method, IDebugRegisters2.SetValues2, IDebugRegisters2::SetValues2, IDebugRegisters_4e5c8f37-a5ad-4083-adb9-e75ec18542b2.xml, SetValues2, SetValues2 method [Windows Debugging], SetValues2 method [Windows Debugging],IDebugRegisters2 interface, dbgeng/IDebugRegisters2::SetValues2, debugger.setvalues2
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
-	IDebugRegisters2.SetValues2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugRegisters2::SetValues2


## -description


The <b>SetValues2</b> method sets the value of several of the target's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">registers</a>.


## -parameters




### -param Source [in]

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
Fetch register information from the current explicit <a href="https://msdn.microsoft.com/3690903c-4281-4c65-98b0-00ca22206168">register context</a>.

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
 


### -param Count [in]

Specifies the number of registers for which to set the values.


### -param Indices [in, optional]

Specifies an array that contains the indices of the registers for which to set the values.  The number of elements in this array is <i>Count</i>.  If <i>Indices</i> is <b>NULL</b>, <i>Start</i> is used instead.


### -param Start [in]

If <i>Indices</i> is <b>NULL</b>, the registers will be set consecutively starting at this index.  Otherwise, it is ignored.


### -param Values [in]

An array that contains the values to which to set the registers.  The number of elements that this array holds is <i>Count</i>.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541719">DEBUG_VALUE</a> for a description of this parameter type.


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
</table>
 




## -remarks



The engine does its best to cast the values in <i>Values</i> into the type of the registers; this conversion is the same as that performed by <a href="https://msdn.microsoft.com/library/windows/hardware/ff539158">CoerceValue</a>.  If the value is larger than what the register can hold, the least significant bits are dropped.  Floating-point and integer conversions will also be performed if necessary.  

If the return value is not S_OK, some of the registers still might have been set.  

When a subregister is altered, the register that contains it is also altered.

The method <a href="https://msdn.microsoft.com/library/windows/hardware/ff556883">SetValues</a> performs the same task as this method but always uses the target as the register source.

For an overview of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550825">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550835">IDebugRegisters2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff597642">SetValue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556883">SetValues</a>
 

 

