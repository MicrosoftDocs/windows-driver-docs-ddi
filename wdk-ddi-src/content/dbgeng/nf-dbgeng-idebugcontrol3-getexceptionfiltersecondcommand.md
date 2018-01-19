---
UID: NF:dbgeng.IDebugControl3.GetExceptionFilterSecondCommand
title: IDebugControl3::GetExceptionFilterSecondCommand method
author: windows-driver-content
description: The GetExceptionFilterSecondCommand method returns the command that will be executed by the debugger engine upon the second chance of a specified exception.
old-location: debugger\getexceptionfiltersecondcommand.htm
old-project: debugger
ms.assetid: 1ea607e2-76a2-4f78-87ca-bf3242f39433
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::GetExceptionFilterSecondCommand, GetExceptionFilterSecondCommand
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
req.alt-api: IDebugControl.GetExceptionFilterSecondCommand,IDebugControl2.GetExceptionFilterSecondCommand,IDebugControl3.GetExceptionFilterSecondCommand
req.alt-loc: dbgeng.h
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

# IDebugControl3::GetExceptionFilterSecondCommand method



## -description
The <b>GetExceptionFilterSecondCommand</b>  method returns the command that will be executed by the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a> upon the second chance of a specified <a href="wdkgloss.e#wdkgloss.exception#wdkgloss.exception"><i>exception</i></a>.



## -syntax

````
HRESULT GetExceptionFilterSecondCommand(
  [in]            ULONG  Index,
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG CommandSize
);
````


## -parameters

### -param Index [in]

Specifies the index of the exception filter whose second-chance command will be returned.  <i>Index</i> can also refer to the default exception filter to return the second-chance command for those exceptions that do not have a specific or arbitrary exception filter.


### -param Buffer [out, optional]

Receives the second-chance command for the exception filter.


### -param BufferSize [in]

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.


### -param CommandSize [out, optional]

Receives the size, in characters, of the second-chance command for the exception filter.  If <i>CommandSize</i> is <b>NULL</b>, this information is not returned.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
Only exception filters support a second-chance command.  If <i>Index</i> refers to a <a href="debugger.debug_filter_xxx#specific_event_filter#specific_event_filter">specific event filter</a>, the command returned to <i>Buffer</i> will be empty.  The returned command will also be empty if no second-chance command has been set for the specified exception.

For more information about <a href="debugger.events#event_filters#event_filters">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.


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
<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556687">SetExceptionFilterSecondCommand</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546611">GetEventFilterCommand</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetExceptionFilterSecondCommand method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

