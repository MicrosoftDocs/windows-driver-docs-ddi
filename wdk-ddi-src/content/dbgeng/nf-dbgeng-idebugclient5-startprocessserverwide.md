---
UID: NF:dbgeng.IDebugClient5.StartProcessServerWide
title: IDebugClient5::StartProcessServerWide method
author: windows-driver-content
description: The StartProcessServerWide method starts a process server.
old-location: debugger\startprocessserverwide.htm
old-project: debugger
ms.assetid: 1e72578c-9359-4275-a4f2-2b5ae4dbf2b7
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 5, :, C, D, I, IDebugClient5, IDebugClient5 interface [Windows Debugging], StartProcessServerWide method, IDebugClient5::StartProcessServerWide, P, S, StartProcessServerWide method [Windows Debugging], StartProcessServerWide method [Windows Debugging], IDebugClient5 interface, StartProcessServerWide,IDebugClient5.StartProcessServerWide, W, a, b, c, d, dbgeng/IDebugClient5::StartProcessServerWide, debugger.startprocessserverwide, e, g, i, l, n, o, r, s, t, u, v"
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
-	IDebugClient5.StartProcessServerWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::StartProcessServerWide method


## -description


The <b>StartProcessServerWide</b> method starts a process server.


## -syntax


````
HRESULT StartProcessServerWide(
  [in]           ULONG  Flags,
  [in]           PCWSTR Options,
  [in, optional] PVOID  Reserved
);
````


## -parameters




### -param Flags [in]

Specifies the class of the targets that will be available through the process server.  This must be set to DEBUG_CLASS_USER_WINDOWS.


### -param Options [in]

Specifies the connections options for this process server.  These are the same options given to the <b>-t</b> option of the DbgSrv command line.  For details on the syntax of this string, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537832">Activating a Process Server</a>.


### -param Reserved [in, optional]

Set to <b>NULL</b>.


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



The process server that is started will be accessible by remote clients through the transport specified in the <i>Options</i> parameter.

To stop the process server from the smart client, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542993">EndProcessServer</a> method. To shut down the process server from the computer that it is running on, use Task Manager to end the process. If the instance of the debugger engine that used <b>StartProcessServer</b> is still running, it can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff543208">Execute</a> to issue the debugger command <a href="https://msdn.microsoft.com/6be6c774-fe6b-4bd4-8174-55ef207db3e6">.endsrv 0</a>, which will end the process server (this is an exception to the usual behavior of <b>.endsrv</b>, which generally does not affect process servers). 

For more information about process servers and remote debugging, see <a href="https://msdn.microsoft.com/ed7ea3dc-07d1-481c-90e0-7f0b0e77ad42">Process Servers, Kernel Connection Servers, and Smart Clients</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561230">WaitForProcessServerEnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542993">EndProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541969">DisconnectProcessServer</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::StartProcessServerWide method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

