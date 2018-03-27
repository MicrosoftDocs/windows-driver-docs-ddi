---
UID: NF:dbgeng.IDebugControl3.GetExceptionFilterSecondCommand
title: IDebugControl3::GetExceptionFilterSecondCommand method
author: windows-driver-content
description: The GetExceptionFilterSecondCommand method returns the command that will be executed by the debugger engine upon the second chance of a specified exception.
old-location: debugger\getexceptionfiltersecondcommand.htm
old-project: debugger
ms.assetid: 1ea607e2-76a2-4f78-87ca-bf3242f39433
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetExceptionFilterSecondCommand method [Windows Debugging], GetExceptionFilterSecondCommand method [Windows Debugging], IDebugControl interface, GetExceptionFilterSecondCommand method [Windows Debugging], IDebugControl2 interface, GetExceptionFilterSecondCommand method [Windows Debugging], IDebugControl3 interface, GetExceptionFilterSecondCommand,IDebugControl3.GetExceptionFilterSecondCommand, IDebugControl interface [Windows Debugging], GetExceptionFilterSecondCommand method, IDebugControl2 interface [Windows Debugging], GetExceptionFilterSecondCommand method, IDebugControl2::GetExceptionFilterSecondCommand, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetExceptionFilterSecondCommand method, IDebugControl3::GetExceptionFilterSecondCommand, IDebugControl::GetExceptionFilterSecondCommand, IDebugControl_fba6b716-8dba-4581-87c3-b808d3ab40a1.xml, dbgeng/IDebugControl2::GetExceptionFilterSecondCommand, dbgeng/IDebugControl3::GetExceptionFilterSecondCommand, dbgeng/IDebugControl::GetExceptionFilterSecondCommand, debugger.getexceptionfiltersecondcommand
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
-	dbgeng.h
api_name:
-	IDebugControl.GetExceptionFilterSecondCommand
-	IDebugControl2.GetExceptionFilterSecondCommand
-	IDebugControl3.GetExceptionFilterSecondCommand
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetExceptionFilterSecondCommand method


## -description


The <b>GetExceptionFilterSecondCommand</b>  method returns the command that will be executed by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> upon the second chance of a specified <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exception</a>.


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



Only exception filters support a second-chance command.  If <i>Index</i> refers to a <a href="https://msdn.microsoft.com/1f8f738b-7b2b-419a-949e-b71f937de02d">specific event filter</a>, the command returned to <i>Buffer</i> will be empty.  The returned command will also be empty if no second-chance command has been set for the specified exception.

For more information about <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546611">GetEventFilterCommand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556687">SetExceptionFilterSecondCommand</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetExceptionFilterSecondCommand method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

