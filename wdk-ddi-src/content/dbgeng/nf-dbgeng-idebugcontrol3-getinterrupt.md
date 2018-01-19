---
UID: NF:dbgeng.IDebugControl3.GetInterrupt
title: IDebugControl3::GetInterrupt method
author: windows-driver-content
description: The GetInterrupt method checks whether a user interrupt was issued.
old-location: debugger\getinterrupt.htm
old-project: debugger
ms.assetid: 597bff1e-0bc1-4c18-9156-661a46cf8e7a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::GetInterrupt, GetInterrupt
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
req.alt-api: IDebugControl.GetInterrupt,IDebugControl2.GetInterrupt,IDebugControl3.GetInterrupt
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

# IDebugControl3::GetInterrupt method



## -description
The <b>GetInterrupt</b> method checks whether a user interrupt was issued.



## -syntax

````
HRESULT GetInterrupt();
````


## -parameters


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful and an interrupt has been requested.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful and an interrupt was not requested.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful and an interrupt has been requested.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful and an interrupt was not requested.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful and an interrupt has been requested.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful and an interrupt was not requested.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
If a user interrupt was issued, it is cleared when this method is called.

Examples of user interrupts include pressing Ctrl+C or pressing the <b>Stop</b> button in a debugger.  Calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff556722">SetInterrupt</a> also causes a user interrupt.

This method can be called at any time and from any thread.


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556722">SetInterrupt</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetInterrupt method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

