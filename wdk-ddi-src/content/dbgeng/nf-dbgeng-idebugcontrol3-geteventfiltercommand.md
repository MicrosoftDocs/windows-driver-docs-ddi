---
UID: NF:dbgeng.IDebugControl3.GetEventFilterCommand
title: IDebugControl3::GetEventFilterCommand method
author: windows-driver-content
description: The GetEventFilterCommand method returns the debugger command that the engine will execute when a specified event occurs.
old-location: debugger\geteventfiltercommand.htm
old-project: debugger
ms.assetid: ea88d1de-70c1-424a-a3a0-cce46cc3fe39
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetEventFilterCommand method [Windows Debugging], IDebugControl3 interface, IDebugControl_a0acf45f-8741-48a0-9eb0-f8a9aa55c476.xml, GetEventFilterCommand method [Windows Debugging], IDebugControl2 interface, IDebugControl2::GetEventFilterCommand, debugger.geteventfiltercommand, IDebugControl::GetEventFilterCommand, GetEventFilterCommand, IDebugControl3, GetEventFilterCommand method [Windows Debugging], IDebugControl interface, IDebugControl2 interface [Windows Debugging], GetEventFilterCommand method, GetEventFilterCommand method [Windows Debugging], dbgeng/IDebugControl2::GetEventFilterCommand, IDebugControl3::GetEventFilterCommand, dbgeng/IDebugControl::GetEventFilterCommand, IDebugControl3 interface [Windows Debugging], GetEventFilterCommand method, dbgeng/IDebugControl3::GetEventFilterCommand, IDebugControl interface [Windows Debugging], GetEventFilterCommand method
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
-	IDebugControl.GetEventFilterCommand
-	IDebugControl2.GetEventFilterCommand
-	IDebugControl3.GetEventFilterCommand
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetEventFilterCommand method


## -description


The <b>GetEventFilterCommand</b>  method returns the debugger command that the engine will execute when a specified event occurs.


## -syntax


````
HRESULT GetEventFilterCommand(
  [in]            ULONG  Index,
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG CommandSize
);
````


## -parameters




### -param Index [in]

Specifies the index of the event filter.  <i>Index</i> can take any value between zero and one less than the total number of event filters returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547899">GetNumberEventFilters</a> (inclusive).  For more information about the index of the filters, see Index and Exception Code.


### -param Buffer [out, optional]

Receives the debugger command that the engine will execute when the event occurs.


### -param BufferSize [in]

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.


### -param CommandSize [out, optional]

Receives the size in characters of the command.  If <i>CommandSize</i> is <b>NULL</b>, this information is not returned.


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

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556678">SetEventFilterCommand</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546653">GetExceptionFilterSecondCommand</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetEventFilterCommand method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

