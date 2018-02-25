---
UID: NF:dbgeng.IDebugControl3.GetInterrupt
title: IDebugControl3::GetInterrupt method
author: windows-driver-content
description: The GetInterrupt method checks whether a user interrupt was issued.
old-location: debugger\getinterrupt.htm
old-project: debugger
ms.assetid: 597bff1e-0bc1-4c18-9156-661a46cf8e7a
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 3, :, C, D, G, GetInterrupt method [Windows Debugging], GetInterrupt method [Windows Debugging], IDebugControl interface, GetInterrupt method [Windows Debugging], IDebugControl2 interface, GetInterrupt method [Windows Debugging], IDebugControl3 interface, GetInterrupt,IDebugControl.GetInterrupt, GetInterrupt,IDebugControl2.GetInterrupt, GetInterrupt,IDebugControl3.GetInterrupt, I, IDebugControl, IDebugControl interface [Windows Debugging], GetInterrupt method, IDebugControl2, IDebugControl2 interface [Windows Debugging], GetInterrupt method, IDebugControl2::GetInterrupt, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetInterrupt method, IDebugControl3::GetInterrupt, IDebugControl::GetInterrupt, IDebugControl_059bd637-c75b-4b52-a382-c645cb4b25b9.xml, b, dbgeng/IDebugControl2::GetInterrupt, dbgeng/IDebugControl3::GetInterrupt, dbgeng/IDebugControl::GetInterrupt, debugger.getinterrupt, e, g, l, n, o, p, r, t, u"
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
-	IDebugControl.GetInterrupt
-	IDebugControl2.GetInterrupt
-	IDebugControl3.GetInterrupt
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetInterrupt method


## -description


The <b>GetInterrupt</b> method checks whether a user interrupt was issued.


## -syntax


````
HRESULT GetInterrupt();
````


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

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556722">SetInterrupt</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetInterrupt method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

