---
UID: NF:dbgeng.IDebugClient5.AttachProcess
title: IDebugClient5::AttachProcess method
author: windows-driver-content
description: The AttachProcess method connects the debugger engine to a user-modeprocess.
old-location: debugger\attachprocess.htm
old-project: debugger
ms.assetid: 0787da49-23e0-43e3-bb32-1221db32a449
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugClient5, IDebugClient5::AttachProcess, AttachProcess
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
req.alt-api: IDebugClient.AttachProcess,IDebugClient2.AttachProcess,IDebugClient3.AttachProcess,IDebugClient4.AttachProcess,IDebugClient5.AttachProcess
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

# IDebugClient5::AttachProcess method



## -description
The <b>AttachProcess</b> method connects the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a> to a user-modeprocess.



## -syntax

````
HRESULT AttachProcess(
  [in] ULONG64 Server,
  [in] ULONG   ProcessId,
  [in] ULONG   AttachFlags
);
````


## -parameters

### -param Server [in]

Specifies the process server to use to attach to the process.  If <i>Server</i> is zero, the engine will connect to a local process without using a process server.


### -param ProcessId [in]

Specifies the process ID of the target process the debugger will attach to.


### -param AttachFlags [in]

Specifies the flags that control how the debugger attaches to the target process.  For details on these flags, see Remarks.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
This method is available only for live user-mode debugging.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.

The DEBUG_ATTACH_<i>XXX</i> bit-flags control how the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a> attaches to a user-mode process.  For the DEBUG_ATTACH_<i>XXX</i> options used when attaching to a kernel target, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538145">AttachKernel</a>.

The following table describes the possible flag values.



<b>DEBUG_ATTACH_NONINVASIVE</b>

Attach to the target noninvasively.  For more information about noninvasive debugging, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552274">Noninvasive Debugging (User Mode)</a>.

If this flag is set, then the flags DEBUG_ATTACH_EXISTING, DEBUG_ATTACH_INVASIVE_NO_INITIAL_BREAK, and DEBUG_ATTACH_INVASIVE_RESUME_PROCESS must not be set.

<b>DEBUG_ATTACH_EXISTING</b>

Re-attach to an application to which a debugger has already attached (and possibly abandoned).  For more information about re-attaching to targets, see <a href="https://msdn.microsoft.com/cc137185-58a7-44bf-b262-2698c46730f6">Re-attaching to the Target Application</a>.

If this flag is set, then the other DEBUG_ATTACH_<i>XXX</i> flags must not be set.

<b>DEBUG_ATTACH_NONINVASIVE_NO_SUSPEND</b>

Do not suspend the target's threads when attaching noninvasively.

If this flag is set, then the flag DEBUG_ATTACH_NONINVASIVE must also be set.

<b>DEBUG_ATTACH_INVASIVE_NO_INITIAL_BREAK</b>

(Windows XP and later)  Do not request an initial break-in when attaching to the target.

If this flag is set, then the flags DEBUG_ATTACH_NONINVASIVE and DEBUG_ATTACH_EXISTING must not be set.

<b>DEBUG_ATTACH_INVASIVE_RESUME_PROCESS</b>


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>
</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562135">.attach (Attach to Process)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538145">AttachKernel</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539323">CreateProcess2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>
</dt>
<dt><a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a></dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548265">GetRunningProcessSystemIds</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548243">GetRunningProcessDescription</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541846">DetachCurrentProcess</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558866">TerminateCurrentProcess</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537786">AbandonCurrentProcess</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::AttachProcess method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

