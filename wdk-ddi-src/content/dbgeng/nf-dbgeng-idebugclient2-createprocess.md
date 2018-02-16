---
UID: NF:dbgeng.IDebugClient2.CreateProcess
title: IDebugClient2::CreateProcess method
author: windows-driver-content
description: The CreateProcess method creates a process from the specified command line.
old-location: debugger\createprocess.htm
old-project: debugger
ms.assetid: 0c70c1f8-3c1c-4401-a7c4-14dc9bd0af04
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugClient4::CreateProcess, CreateProcess method [Windows Debugging], IDebugClient2 interface, CreateProcess method [Windows Debugging], IDebugClient5 interface, IDebugClient4::CreateProcess, IDebugClient2 interface [Windows Debugging], CreateProcess method, IDebugClient, IDebugClient3 interface [Windows Debugging], CreateProcess method, IDebugClient4 interface [Windows Debugging], CreateProcess method, IDebugClient2, dbgeng/IDebugClient::CreateProcess, CreateProcess method [Windows Debugging], IDebugClient4 interface, CreateProcess method [Windows Debugging], debugger.createprocess, IDebugClient2::CreateProcess, IDebugClient3::CreateProcess, dbgeng/IDebugClient5::CreateProcess, IDebugClient interface [Windows Debugging], CreateProcess method, IDebugClient5::CreateProcess, CreateProcess, CreateProcess method [Windows Debugging], IDebugClient3 interface, IDebugClient::CreateProcess, IDebugClient_6411b416-f861-4c99-94bc-ceffd54acce0.xml, dbgeng/IDebugClient3::CreateProcess, IDebugClient5 interface [Windows Debugging], CreateProcess method, dbgeng/IDebugClient2::CreateProcess, CreateProcess method [Windows Debugging], IDebugClient interface
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
-	IDebugClient.CreateProcess
-	IDebugClient2.CreateProcess
-	IDebugClient3.CreateProcess
-	IDebugClient4.CreateProcess
-	IDebugClient5.CreateProcess
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugClient2::CreateProcess method


## -description


The <b>CreateProcess</b>  method creates a process from the specified command line.


## -syntax


````
HRESULT CreateProcess(
  [in] ULONG64 Server,
  [in] PSTR    CommandLine,
  [in] ULONG   CreateFlags
);
````


## -parameters




### -param Server [in]

Specifies the process server to use to attach to the process.  If <i>Server</i> is zero, the engine will create a local process without using a process server.


### -param CommandLine [in]

Specifies the command line to execute to create the new process.


### -param CreateFlags [in]

Specifies the flags to use when creating the process.  For details on these flags, see the <b>CreateFlags</b> member of the <a href="..\dbgeng\ns-dbgeng-_debug_create_process_options.md">DEBUG_CREATE_PROCESS_OPTIONS</a> structure.


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



This method is available only for live user-mode debugging.

If <i>CreateFlags</i> contains either of the flags DEBUG_PROCESS or DEBUG_ONLY_THIS_PROCESS, the engine will also attach to the newly created process; this is similar to the behavior of <a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a> with its argument <i>ProcessId</i> set to zero.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539323">CreateProcess2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562280">.create (Create Process)</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::CreateProcess method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

