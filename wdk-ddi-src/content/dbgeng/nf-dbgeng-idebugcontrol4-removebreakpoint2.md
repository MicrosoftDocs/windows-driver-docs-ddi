---
UID: NF:dbgeng.IDebugControl4.RemoveBreakpoint2
title: IDebugControl4::RemoveBreakpoint2 method
author: windows-driver-content
description: The RemoveBreakpoint2 method removes a breakpoint.
old-location: debugger\removebreakpoint2.htm
old-project: debugger
ms.assetid: e1c77758-0249-4ec6-9244-329c0b823e44
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugControl4, IDebugControl4 interface [Windows Debugging], RemoveBreakpoint2 method, IDebugControl4::RemoveBreakpoint2, RemoveBreakpoint2 method [Windows Debugging], RemoveBreakpoint2 method [Windows Debugging], IDebugControl4 interface, RemoveBreakpoint2,IDebugControl4.RemoveBreakpoint2, dbgeng/IDebugControl4::RemoveBreakpoint2, debugger.removebreakpoint2
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl4.RemoveBreakpoint2
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::RemoveBreakpoint2 method


## -description


The <b>RemoveBreakpoint2</b>  method removes a breakpoint.


## -syntax


````
HRESULT RemoveBreakpoint2(
  [in] PDEBUG_BREAKPOINT2 Bp
);
````


## -parameters




### -param Bp [in]

Specifies an interface pointer to breakpoint to remove.


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
 

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



After <b>RemoveBreakpoint</b> and <b>RemoveBreakpoint2</b> are called, the breakpoint object specified in the <i>Bp</i> parameter must not be used again.

<div class="alert"><b>Note</b>    Even though <a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a> extends the COM interface <b>IUnknown</b>, the lifetime of the breakpoint is not controlled using the <b>IUnknown</b> interface.  Instead, the breakpoint is deleted after <b>RemoveBreakpoint</b> and <b>RemoveBreakpoint2</b> are called.</div>
<div> </div>
For more details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537856">AddBreakpoint</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::RemoveBreakpoint2 method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

