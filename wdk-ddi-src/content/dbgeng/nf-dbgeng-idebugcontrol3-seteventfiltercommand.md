---
UID: NF:dbgeng.IDebugControl3.SetEventFilterCommand
title: IDebugControl3::SetEventFilterCommand method
author: windows-driver-content
description: The SetEventFilterCommand method sets a debugger command for the engine to execute when a specified event occurs.
old-location: debugger\seteventfiltercommand.htm
old-project: debugger
ms.assetid: d68d0a98-ec93-4643-a6c1-eff9d5618e03
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl3, IDebugControl3 interface [Windows Debugging], SetEventFilterCommand method, IDebugControl::SetEventFilterCommand, IDebugControl interface [Windows Debugging], SetEventFilterCommand method, SetEventFilterCommand method [Windows Debugging], debugger.seteventfiltercommand, dbgeng/IDebugControl2::SetEventFilterCommand, IDebugControl3::SetEventFilterCommand, SetEventFilterCommand method [Windows Debugging], IDebugControl interface, dbgeng/IDebugControl::SetEventFilterCommand, dbgeng/IDebugControl3::SetEventFilterCommand, IDebugControl_b0661dd4-9ecd-49ac-93e1-86d3c6c2c3f6.xml, SetEventFilterCommand, SetEventFilterCommand method [Windows Debugging], IDebugControl2 interface, SetEventFilterCommand method [Windows Debugging], IDebugControl3 interface, IDebugControl2 interface [Windows Debugging], SetEventFilterCommand method, IDebugControl2::SetEventFilterCommand
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
-	dbgeng.h
apiname:
-	IDebugControl.SetEventFilterCommand
-	IDebugControl2.SetEventFilterCommand
-	IDebugControl3.SetEventFilterCommand
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::SetEventFilterCommand method


## -description


The <b>SetEventFilterCommand</b>  method sets a debugger command for the engine to execute when a specified event occurs.


## -syntax


````
HRESULT SetEventFilterCommand(
  [in] ULONG Index,
  [in] PCSTR Command
);
````


## -parameters




### -param Index [in]

Specifies the index of the event filter.  <i>Index</i> can take any value between zero and one less than the total number of event filters returned by <b>GetNumberEventFilters</b> (inclusive).  For more information about the index of the filters, see Index and Exception Code.


### -param Command [in]

Specifies the debugger command for the engine to execute when the event occurs.


## -returns


This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
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


For more information about event filters, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546611">GetEventFilterCommand</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556687">SetExceptionFilterSecondCommand</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::SetEventFilterCommand method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

