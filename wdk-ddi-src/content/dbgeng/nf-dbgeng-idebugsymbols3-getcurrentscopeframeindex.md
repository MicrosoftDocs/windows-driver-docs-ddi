---
UID: NF:dbgeng.IDebugSymbols3.GetCurrentScopeFrameIndex
title: IDebugSymbols3::GetCurrentScopeFrameIndex method
author: windows-driver-content
description: The GetCurrentScopeFrameIndex method returns the index of the current stack frame in the call stack.
old-location: debugger\getcurrentscopeframeindex.htm
old-project: debugger
ms.assetid: 735934c5-70c4-4bd5-a5ff-e2d313191b69
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetCurrentScopeFrameIndex method [Windows Debugging], GetCurrentScopeFrameIndex method [Windows Debugging], IDebugSymbols3 interface, GetCurrentScopeFrameIndex,IDebugSymbols3.GetCurrentScopeFrameIndex, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetCurrentScopeFrameIndex method, IDebugSymbols3::GetCurrentScopeFrameIndex, IDebugSymbols_293a8676-cbda-4b24-a6e0-d80f365cb283.xml, dbgeng/IDebugSymbols3::GetCurrentScopeFrameIndex, debugger.getcurrentscopeframeindex
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
-	IDebugSymbols3.GetCurrentScopeFrameIndex
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetCurrentScopeFrameIndex method


## -description


The <b>GetCurrentScopeFrameIndex</b> method returns the index of the current stack frame in the call stack.


## -parameters




### -param Index [out]

Receives the index of the stack frame corresponding to the current scope.  The index counts the number of frames from the top of the call stack.  The frame at the top of the stack, representing the current call, has index zero.


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



If the current scope was set using <a href="https://msdn.microsoft.com/library/windows/hardware/ff556773">SetScope</a>, <i>Index</i> receives the value of the <b>FrameNumber</b> member of the DEBUG_STACK_TRACE structure passed to the <i>ScopeFrame</i> parameter of <b>SetScope</b>.

For more information about scopes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563155">.frame (Set Local Context)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548270">GetScope</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556774">SetScopeFrameByIndex</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetCurrentScopeFrameIndex method%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

