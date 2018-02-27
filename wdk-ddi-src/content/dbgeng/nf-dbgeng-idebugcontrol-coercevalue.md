---
UID: NF:dbgeng.IDebugControl.CoerceValue
title: IDebugControl::CoerceValue method
author: windows-driver-content
description: The CoerceValue method converts a value of one type into a value of another type.
old-location: debugger\coercevalue.htm
old-project: debugger
ms.assetid: db037fc8-d503-4a72-b6bc-d5189f6786d4
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: CoerceValue method [Windows Debugging], CoerceValue method [Windows Debugging], IDebugControl interface, CoerceValue method [Windows Debugging], IDebugControl2 interface, CoerceValue method [Windows Debugging], IDebugControl3 interface, CoerceValue,IDebugControl.CoerceValue, IDebugControl, IDebugControl interface [Windows Debugging], CoerceValue method, IDebugControl2 interface [Windows Debugging], CoerceValue method, IDebugControl2::CoerceValue, IDebugControl3 interface [Windows Debugging], CoerceValue method, IDebugControl3::CoerceValue, IDebugControl::CoerceValue, IDebugControl_034a690e-25bb-40a1-b788-7b148ba0d9cd.xml, dbgeng/IDebugControl2::CoerceValue, dbgeng/IDebugControl3::CoerceValue, dbgeng/IDebugControl::CoerceValue, debugger.coercevalue
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Dbgeng.h
apiname:
-	IDebugControl.CoerceValue
-	IDebugControl2.CoerceValue
-	IDebugControl3.CoerceValue
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl::CoerceValue method


## -description


The <b>CoerceValue</b> method converts a value of one type into a value of another type.


## -syntax


````
HRESULT CoerceValue(
  [in]  PDEBUG_VALUE In,
  [in]  ULONG        OutType,
  [out] PDEBUG_VALUE Out
);
````


## -parameters




### -param In [in]

Specifies the value to be converted


### -param OutType [in]

Specifies the desired type for the converted value. See <a href="..\dbgeng\ns-dbgeng-_debug_value.md">DEBUG_VALUE</a> for possible values.


### -param Out [out]

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
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



This method converts a value of one type into a value of another type.  If the specified <i>OutType</i> is not capable of containing the information supplied by the <i>In</i> variable, data will be lost.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="..\dbgeng\ns-dbgeng-_debug_value.md">DEBUG_VALUE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::CoerceValue method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

