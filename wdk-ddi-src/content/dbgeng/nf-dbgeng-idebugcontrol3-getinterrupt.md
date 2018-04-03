---
UID: NF:dbgeng.IDebugControl3.GetInterrupt
title: IDebugControl3::GetInterrupt method
author: windows-driver-content
description: The GetInterrupt method checks whether a user interrupt was issued.
old-location: debugger\getinterrupt.htm
old-project: debugger
ms.assetid: 597bff1e-0bc1-4c18-9156-661a46cf8e7a
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetInterrupt method [Windows Debugging], GetInterrupt method [Windows Debugging], IDebugControl interface, GetInterrupt method [Windows Debugging], IDebugControl2 interface, GetInterrupt method [Windows Debugging], IDebugControl3 interface, GetInterrupt,IDebugControl3.GetInterrupt, IDebugControl interface [Windows Debugging], GetInterrupt method, IDebugControl2 interface [Windows Debugging], GetInterrupt method, IDebugControl2::GetInterrupt, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetInterrupt method, IDebugControl3::GetInterrupt, IDebugControl::GetInterrupt, IDebugControl_059bd637-c75b-4b52-a382-c645cb4b25b9.xml, dbgeng/IDebugControl2::GetInterrupt, dbgeng/IDebugControl3::GetInterrupt, dbgeng/IDebugControl::GetInterrupt, debugger.getinterrupt
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Dbgeng.h
api_name:
-	IDebugControl.GetInterrupt
-	IDebugControl2.GetInterrupt
-	IDebugControl3.GetInterrupt
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetInterrupt method


## -description


The <b>GetInterrupt</b> method checks whether a user interrupt was issued.


## -parameters






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
The method was successful and an interrupt has been requested.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful and an interrupt was not requested.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



If a user interrupt was issued, it is cleared when this method is called.

Examples of user interrupts include pressing Ctrl+C or pressing the <b>Stop</b> button in a debugger.  Calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff556722">SetInterrupt</a> also causes a user interrupt.

<div class="alert"><b>Note</b>    It is recommended that debugger extensions call <b>GetInterrupt</b> while undertaking long tasks.</div>
<div> </div>
This method can be called at any time and from any thread.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556722">SetInterrupt</a>
 

 

