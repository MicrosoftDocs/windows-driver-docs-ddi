---
UID: NF:dbgeng.IDebugControl2.CoerceValue
title: IDebugControl2::CoerceValue (dbgeng.h)
description: The CoerceValue method converts a value of one type into a value of another type.
old-location: debugger\coercevalue.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl2::CoerceValue"]
ms.keywords: CoerceValue, CoerceValue method [Windows Debugging], CoerceValue method [Windows Debugging],IDebugControl interface, CoerceValue method [Windows Debugging],IDebugControl2 interface, CoerceValue method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],CoerceValue method, IDebugControl2 interface [Windows Debugging],CoerceValue method, IDebugControl2.CoerceValue, IDebugControl2::CoerceValue, IDebugControl3 interface [Windows Debugging],CoerceValue method, IDebugControl3::CoerceValue, IDebugControl::CoerceValue, IDebugControl_034a690e-25bb-40a1-b788-7b148ba0d9cd.xml, dbgeng/IDebugControl2::CoerceValue, dbgeng/IDebugControl3::CoerceValue, dbgeng/IDebugControl::CoerceValue, debugger.coercevalue
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
 - IDebugControl2::CoerceValue
 - dbgeng/IDebugControl2::CoerceValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugControl2::CoerceValue
---

# IDebugControl2::CoerceValue


## -description

The <b>CoerceValue</b> method converts a value of one type into a value of another type.

## -parameters

### -param In 

[in]
Specifies the value to be converted

### -param OutType 

[in]
Specifies the desired type for the converted value. See <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_value">DEBUG_VALUE</a> for possible values.

### -param Out 

[out]
Receives the converted value.  The type of this value will be the type specified by <i>OutType</i>.

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
 

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

This method converts a value of one type into a value of another type.  If the specified <i>OutType</i> is not capable of containing the information supplied by the <i>In</i> variable, data will be lost.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_value">DEBUG_VALUE</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>

