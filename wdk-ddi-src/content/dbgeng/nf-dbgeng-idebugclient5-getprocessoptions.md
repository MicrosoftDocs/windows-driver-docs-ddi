---
UID: NF:dbgeng.IDebugClient5.GetProcessOptions
title: IDebugClient5::GetProcessOptions method
author: windows-driver-content
description: The GetProcessOptions method retrieves the process options affecting the current process.
old-location: debugger\getprocessoptions.htm
old-project: debugger
ms.assetid: ff2d4da4-5a10-4196-92bd-ac4b244a2257
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 5, :, C, D, G, GetProcessOptions method [Windows Debugging], GetProcessOptions method [Windows Debugging], IDebugClient interface, GetProcessOptions method [Windows Debugging], IDebugClient2 interface, GetProcessOptions method [Windows Debugging], IDebugClient3 interface, GetProcessOptions method [Windows Debugging], IDebugClient4 interface, GetProcessOptions method [Windows Debugging], IDebugClient5 interface, GetProcessOptions,IDebugClient.GetProcessOptions, GetProcessOptions,IDebugClient2.GetProcessOptions, GetProcessOptions,IDebugClient3.GetProcessOptions, GetProcessOptions,IDebugClient4.GetProcessOptions, GetProcessOptions,IDebugClient5.GetProcessOptions, I, IDebugClient, IDebugClient interface [Windows Debugging], GetProcessOptions method, IDebugClient2, IDebugClient2 interface [Windows Debugging], GetProcessOptions method, IDebugClient2::GetProcessOptions, IDebugClient3, IDebugClient3 interface [Windows Debugging], GetProcessOptions method, IDebugClient3::GetProcessOptions, IDebugClient4, IDebugClient4 interface [Windows Debugging], GetProcessOptions method, IDebugClient4::GetProcessOptions, IDebugClient5, IDebugClient5 interface [Windows Debugging], GetProcessOptions method, IDebugClient5::GetProcessOptions, IDebugClient::GetProcessOptions, IDebugClient_5d54bc2a-5691-4a3a-b3c9-92fc577cdabb.xml, O, P, b, c, dbgeng/IDebugClient2::GetProcessOptions, dbgeng/IDebugClient3::GetProcessOptions, dbgeng/IDebugClient4::GetProcessOptions, dbgeng/IDebugClient5::GetProcessOptions, dbgeng/IDebugClient::GetProcessOptions, debugger.getprocessoptions, e, g, i, l, n, o, p, r, s, t, u"
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
-	IDebugClient.GetProcessOptions
-	IDebugClient2.GetProcessOptions
-	IDebugClient3.GetProcessOptions
-	IDebugClient4.GetProcessOptions
-	IDebugClient5.GetProcessOptions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::GetProcessOptions method


## -description


The <b>GetProcessOptions</b> method retrieves the process options affecting the current process.


## -syntax


````
HRESULT GetProcessOptions(
  [out] PULONG Options
);
````


## -parameters




### -param Options [out]

Receives a set of flags representing the process options for the current process.  For details on these options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541534">DEBUG_PROCESS_XXX</a>.


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



This method is only available in live user-mode debugging.

Some of the process options are global options, others are specific to the current process.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554505">RemoveProcessOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541534">DEBUG_PROCESS_XXX</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537917">AddProcessOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556765">SetProcessOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::GetProcessOptions method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

