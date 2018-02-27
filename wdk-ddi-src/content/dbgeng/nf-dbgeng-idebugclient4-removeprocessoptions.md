---
UID: NF:dbgeng.IDebugClient4.RemoveProcessOptions
title: IDebugClient4::RemoveProcessOptions method
author: windows-driver-content
description: The RemoveProcessOptions method removes process options from those options that affect the current process.
old-location: debugger\removeprocessoptions.htm
old-project: debugger
ms.assetid: 8b2cf167-d1bd-440e-beb4-5159b8b13073
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IDebugClient interface [Windows Debugging], RemoveProcessOptions method, IDebugClient2 interface [Windows Debugging], RemoveProcessOptions method, IDebugClient2::RemoveProcessOptions, IDebugClient3 interface [Windows Debugging], RemoveProcessOptions method, IDebugClient3::RemoveProcessOptions, IDebugClient4, IDebugClient4 interface [Windows Debugging], RemoveProcessOptions method, IDebugClient4::RemoveProcessOptions, IDebugClient5 interface [Windows Debugging], RemoveProcessOptions method, IDebugClient5::RemoveProcessOptions, IDebugClient::RemoveProcessOptions, IDebugClient_eafb8a9c-18a4-4737-8ece-955596338fe5.xml, RemoveProcessOptions method [Windows Debugging], RemoveProcessOptions method [Windows Debugging], IDebugClient interface, RemoveProcessOptions method [Windows Debugging], IDebugClient2 interface, RemoveProcessOptions method [Windows Debugging], IDebugClient3 interface, RemoveProcessOptions method [Windows Debugging], IDebugClient4 interface, RemoveProcessOptions method [Windows Debugging], IDebugClient5 interface, RemoveProcessOptions,IDebugClient4.RemoveProcessOptions, dbgeng/IDebugClient2::RemoveProcessOptions, dbgeng/IDebugClient3::RemoveProcessOptions, dbgeng/IDebugClient4::RemoveProcessOptions, dbgeng/IDebugClient5::RemoveProcessOptions, dbgeng/IDebugClient::RemoveProcessOptions, debugger.removeprocessoptions
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
-	IDebugClient.RemoveProcessOptions
-	IDebugClient2.RemoveProcessOptions
-	IDebugClient3.RemoveProcessOptions
-	IDebugClient4.RemoveProcessOptions
-	IDebugClient5.RemoveProcessOptions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient4::RemoveProcessOptions method


## -description


The <b>RemoveProcessOptions</b> method removes process options from those options that affect the current process.


## -syntax


````
HRESULT RemoveProcessOptions(
  [in] ULONG Options
);
````


## -parameters




### -param Options [in]

Specifies the process options to remove from those affecting the current process.  For details on these options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541534">DEBUG_PROCESS_XXX</a>.


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
</table>
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



This method is available only in live user-mode debugging.

Some of the process options are global options, others are specific to the current process.

If any process options are modified, the engine will notify the event callbacks by calling their <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> method with the DEBUG_CES_PROCESS_OPTIONS flag set.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548163">GetProcessOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541534">DEBUG_PROCESS_XXX</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556765">SetProcessOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537917">AddProcessOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::RemoveProcessOptions method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

