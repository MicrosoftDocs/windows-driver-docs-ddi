---
UID: NF:dbgeng.IDebugControl.SetExceptionFilterSecondCommand
title: IDebugControl::SetExceptionFilterSecondCommand method
author: windows-driver-content
description: The SetExceptionFilterSecondCommand method sets the command that will be executed by the debugger engine on the second chance of a specified exception.
old-location: debugger\setexceptionfiltersecondcommand.htm
old-project: debugger
ms.assetid: c95fa025-9455-4a8e-99ef-84030255575c
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: SetExceptionFilterSecondCommand method [Windows Debugging], IDebugControl2 interface, IDebugControl3 interface [Windows Debugging], SetExceptionFilterSecondCommand method, debugger.setexceptionfiltersecondcommand, IDebugControl, SetExceptionFilterSecondCommand method [Windows Debugging], dbgeng/IDebugControl::SetExceptionFilterSecondCommand, IDebugControl3::SetExceptionFilterSecondCommand, dbgeng/IDebugControl2::SetExceptionFilterSecondCommand, IDebugControl interface [Windows Debugging], SetExceptionFilterSecondCommand method, IDebugControl2::SetExceptionFilterSecondCommand, dbgeng/IDebugControl3::SetExceptionFilterSecondCommand, SetExceptionFilterSecondCommand method [Windows Debugging], IDebugControl interface, SetExceptionFilterSecondCommand method [Windows Debugging], IDebugControl3 interface, IDebugControl::SetExceptionFilterSecondCommand, IDebugControl_39380f22-4c68-40fe-b277-f7eace77bcee.xml, IDebugControl2 interface [Windows Debugging], SetExceptionFilterSecondCommand method, SetExceptionFilterSecondCommand
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
-	IDebugControl.SetExceptionFilterSecondCommand
-	IDebugControl2.SetExceptionFilterSecondCommand
-	IDebugControl3.SetExceptionFilterSecondCommand
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl::SetExceptionFilterSecondCommand method


## -description


The <b>SetExceptionFilterSecondCommand</b>  method sets the command that will be executed by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> on the second chance of a specified <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exception</a>.


## -syntax


````
HRESULT SetExceptionFilterSecondCommand(
  [in] ULONG Index,
  [in] PCSTR Command
);
````


## -parameters




### -param Index [in]

Specifies the index of the exception filter whose second-chance command will be set.  <i>Index</i> must not refer to the specific event filters as these are not exception filters and only exception events get a second chance.  If <i>Index</i> refers to the default exception filter, the second-chance command is set for all exceptions that do not have an exception filter.


### -param Command [in]

Receives the second-chance command for the exception filter.


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



For more information about <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556678">SetEventFilterCommand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546653">GetExceptionFilterSecondCommand</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::SetExceptionFilterSecondCommand method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

