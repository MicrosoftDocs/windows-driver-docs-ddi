---
UID: NF:dbgeng.IDebugAdvanced3.SetThreadContext
title: IDebugAdvanced3::SetThreadContext method
author: windows-driver-content
description: The SetThreadContext method sets the current thread context.
old-location: debugger\setthreadcontext.htm
old-project: debugger
ms.assetid: eaaaa9d7-ba6d-4379-b721-74c92375ea05
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugAdvanced interface [Windows Debugging], SetThreadContext method, IDebugAdvanced2 interface [Windows Debugging], SetThreadContext method, IDebugAdvanced2::SetThreadContext, IDebugAdvanced3, IDebugAdvanced3 interface [Windows Debugging], SetThreadContext method, IDebugAdvanced3::SetThreadContext, IDebugAdvanced::SetThreadContext, IDebugAdvanced_08e9f1e1-7af3-4cdf-9550-7d22fa5a59da.xml, SetThreadContext method [Windows Debugging], SetThreadContext method [Windows Debugging], IDebugAdvanced interface, SetThreadContext method [Windows Debugging], IDebugAdvanced2 interface, SetThreadContext method [Windows Debugging], IDebugAdvanced3 interface, SetThreadContext,IDebugAdvanced3.SetThreadContext, dbgeng/IDebugAdvanced2::SetThreadContext, dbgeng/IDebugAdvanced3::SetThreadContext, dbgeng/IDebugAdvanced::SetThreadContext, debugger.setthreadcontext
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
-	IDebugAdvanced.SetThreadContext
-	IDebugAdvanced2.SetThreadContext
-	IDebugAdvanced3.SetThreadContext
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugAdvanced3::SetThreadContext method


## -description


The <b>SetThreadContext</b> method sets the current <a href="https://msdn.microsoft.com/f14b6361-9962-4fa3-bb1a-dfde066754b9">thread context</a>.


## -parameters




### -param Context [in]

Specifies the thread context. The type of the thread context is the CONTEXT structure for the target's effective processor.  The buffer <i>Context</i> must be large enough to hold this structure.


### -param ContextSize [in]

Specifies the size of the buffer <i>Context</i>.


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



For more information about the thread context, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.

<div class="alert"><b>Note</b>    The CONTEXT structure varies with operating system and platform.  Care should be taken when using the CONTEXT structure.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549291">GetThreadContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549798">IDebugAdvanced</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549803">IDebugAdvanced2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549807">IDebugAdvanced3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556773">SetScope</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugAdvanced::SetThreadContext method%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

