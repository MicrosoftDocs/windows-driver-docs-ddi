---
UID: NF:dbgeng.IDebugControl3.AddBreakpoint
title: IDebugControl3::AddBreakpoint method
author: windows-driver-content
description: The AddBreakpoint method creates a new breakpoint for the current target.
old-location: debugger\addbreakpoint.htm
old-project: debugger
ms.assetid: 08452b54-158f-4dca-86d8-34cc3f96bc62
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl::AddBreakpoint, AddBreakpoint method [Windows Debugging], IDebugControl3 interface, IDebugControl3, AddBreakpoint method [Windows Debugging], IDebugControl interface, dbgeng/IDebugControl3::AddBreakpoint, debugger.addbreakpoint, IDebugControl interface [Windows Debugging], AddBreakpoint method, AddBreakpoint method [Windows Debugging], IDebugControl2 interface, dbgeng/IDebugControl2::AddBreakpoint, IDebugControl3::AddBreakpoint, AddBreakpoint, IDebugControl2 interface [Windows Debugging], AddBreakpoint method, dbgeng/IDebugControl::AddBreakpoint, AddBreakpoint method [Windows Debugging], IDebugControl2, IDebugControl, IDebugControl_3d11665a-ec78-4742-8195-2798601814e9.xml, IDebugControl2::AddBreakpoint, IDebugControl3 interface [Windows Debugging], AddBreakpoint method
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
-	IDebugControl.AddBreakpoint
-	IDebugControl2.AddBreakpoint
-	IDebugControl3.AddBreakpoint
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl3::AddBreakpoint method


## -description


The <b>AddBreakpoint</b>  method creates a new breakpoint for the current target.


## -syntax


````
HRESULT AddBreakpoint(
  [in]  ULONG            Type,
  [in]  ULONG            DesiredId,
  [out] IDebugBreakpoint **Bp
);
````


## -parameters




### -param Type [in]

Specifies the breakpoint type of the new breakpoint.  This can be either of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_BREAKPOINT_CODE

</td>
<td>
<a href="https://msdn.microsoft.com/94cbf33b-e975-49eb-a266-774798955a48">software breakpoint</a>

</td>
</tr>
<tr>
<td>
DEBUG_BREAKPOINT_DATA

</td>
<td>
<a href="https://msdn.microsoft.com/4cfad26c-d8c0-4f80-aa54-b9cadbc84df3">processor breakpoint</a>

</td>
</tr>
</table>
 


### -param DesiredId [in]

Specifies the desired ID of the new breakpoint.  If it is DEBUG_ANY_ID, the engine will pick an unused ID.


### -param Bp [out]

Receives an interface pointer to the new breakpoint.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The breakpoint couldn't be created with the desired ID or the value of <i>Type</i> was not recognized.

</td>
</tr>
</table>
 

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



If <i>DesiredId</i> is not DEBUG_ANY_ID and another breakpoint already uses the ID <i>DesiredId</i>, these methods will fail.

Breakpoints are created empty and disabled.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a> for details on configuring and enabling the breakpoint.

The client is saved as the adder of the new breakpoint. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff545576">GetAdder</a>. 

<div class="alert"><b>Note</b>    Even though <a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a> extends the COM interface <b>IUnknown</b>, the lifetime of the breakpoint is not controlled using the <b>IUnknown</b> interface.  Instead, the breakpoint is deleted after <a href="https://msdn.microsoft.com/library/windows/hardware/ff554487">RemoveBreakpoint</a> is called.</div>
<div> </div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538928">Breakpoints</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554487">RemoveBreakpoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>



<a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::AddBreakpoint method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

