---
UID: NF:dbgeng.IDebugClient5.AbandonCurrentProcess
title: IDebugClient5::AbandonCurrentProcess method
author: windows-driver-content
description: The AbandonCurrentProcess method removes the current process from the debugger engine's process list without detaching or terminating the process.
old-location: debugger\abandoncurrentprocess.htm
old-project: debugger
ms.assetid: a6abbdb8-8d19-4ae0-8272-8faa87b8e409
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugClient5, IDebugClient5::AbandonCurrentProcess, AbandonCurrentProcess
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
req.alt-api: IDebugClient2.AbandonCurrentProcess,IDebugClient3.AbandonCurrentProcess,IDebugClient4.AbandonCurrentProcess,IDebugClient5.AbandonCurrentProcess
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

# IDebugClient5::AbandonCurrentProcess method



## -description
The <b>AbandonCurrentProcess</b> method removes the <a href="debugger.c#current_process#current_process"><i>current process</i></a> from the debugger engine's process list without detaching or terminating the process.



## -syntax

````
HRESULT AbandonCurrentProcess();
````


## -parameters


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
This method is only available for live user-mode debugging.  The target must be running on Windows XP or a later version of Windows.

Windows will continue to consider this process as being debugged, and so the process will remain suspended.  This method allows the debugger to be shut down and a new debugger to attach to the process.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a> and <a href="https://msdn.microsoft.com/cc137185-58a7-44bf-b262-2698c46730f6">Re-attaching to the Target Application</a> for more information.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541846">DetachCurrentProcess</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558866">TerminateCurrentProcess</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561508">.abandon (Abandon Process)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient2::AbandonCurrentProcess method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

