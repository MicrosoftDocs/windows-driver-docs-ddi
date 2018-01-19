---
UID: NF:dbgeng.IDebugControl3.CoerceValues
title: IDebugControl3::CoerceValues method
author: windows-driver-content
description: The CoerceValues method converts an array of values into an array of values of different types.
old-location: debugger\coercevalues.htm
old-project: debugger
ms.assetid: d5374177-fddd-4f35-8cad-10be762ef4d8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::CoerceValues, CoerceValues
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl.CoerceValues,IDebugControl2.CoerceValues,IDebugControl3.CoerceValues
req.alt-loc: Dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl3::CoerceValues method



## -description
The <b>CoerceValues</b> method converts an array of values into an array of values of different types.



## -syntax

````
HRESULT CoerceValues(
  [in]  ULONG        Count,
  [in]  PDEBUG_VALUE In,
  [in]  PULONG       OutType,
  [out] PDEBUG_VALUE Out
);
````


## -parameters

### -param Count [in]

Specifies the number of values to convert.


### -param In [in]

Specifies the array of values to convert.  The number of elements that this array holds is <i>Count</i>.


### -param OutType [in]

Specifies the array of desired types for the converted values. For possible values, see <a href="..\dbgeng\ns-dbgeng-_debug_value.md">DEBUG_VALUE</a>.  The number of elements that this array holds is <i>Count</i>.


### -param Out [out]

Specifies the array to be populated by the converted values.  The types of these values are specified by <i>OutType</i>.  The number of elements that this array holds is <i>Count</i>.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
This method converts an array of values of one type into values of another type.  Some of these conversions can result in loss of precision.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539158">CoerceValue</a>
</dt>
<dt>
<a href="..\dbgeng\ns-dbgeng-_debug_value.md">DEBUG_VALUE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::CoerceValues method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

