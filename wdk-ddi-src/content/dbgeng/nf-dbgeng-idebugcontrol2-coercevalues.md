---
UID: NF:dbgeng.IDebugControl2.CoerceValues
title: IDebugControl2::CoerceValues (dbgeng.h)
description: The CoerceValues method converts an array of values into an array of values of different types.
old-location: debugger\coercevalues.htm
tech.root: debugger
ms.assetid: d5374177-fddd-4f35-8cad-10be762ef4d8
ms.date: 05/03/2018
keywords: ["IDebugControl2::CoerceValues"]
ms.keywords: CoerceValues, CoerceValues method [Windows Debugging], CoerceValues method [Windows Debugging],IDebugControl interface, CoerceValues method [Windows Debugging],IDebugControl2 interface, CoerceValues method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],CoerceValues method, IDebugControl2 interface [Windows Debugging],CoerceValues method, IDebugControl2.CoerceValues, IDebugControl2::CoerceValues, IDebugControl3 interface [Windows Debugging],CoerceValues method, IDebugControl3::CoerceValues, IDebugControl::CoerceValues, IDebugControl_a17ec845-aaf3-4480-a0fd-79fb515c48d5.xml, dbgeng/IDebugControl2::CoerceValues, dbgeng/IDebugControl3::CoerceValues, dbgeng/IDebugControl::CoerceValues, debugger.coercevalues
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
 - IDebugControl2::CoerceValues
 - dbgeng/IDebugControl2::CoerceValues
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugControl.CoerceValues
 - IDebugControl2.CoerceValues
 - IDebugControl3.CoerceValues
---

# IDebugControl2::CoerceValues


## -description

The <b>CoerceValues</b> method converts an array of values into an array of values of different types.

## -parameters

### -param Count 

[in]
Specifies the number of values to convert.

### -param In 

[in]
Specifies the array of values to convert.  The number of elements that this array holds is <i>Count</i>.

### -param OutTypes

### -param Out 

[out]
Specifies the array to be populated by the converted values.  The types of these values are specified by <i>OutType</i>.  The number of elements that this array holds is <i>Count</i>.


#### - OutType [in]

Specifies the array of desired types for the converted values. For possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_value">DEBUG_VALUE</a>.  The number of elements that this array holds is <i>Count</i>.

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
 

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

This method converts an array of values of one type into values of another type.  Some of these conversions can result in loss of precision.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-coercevalue">CoerceValue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_value">DEBUG_VALUE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>

