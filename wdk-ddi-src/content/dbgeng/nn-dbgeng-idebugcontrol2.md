---
UID: NN:dbgeng.IDebugControl2
title: IDebugControl2
author: windows-driver-content
description: IDebugControl2 interface
old-location: debugger\idebugcontrol2.htm
old-project: debugger
ms.assetid: c8371bbc-cbd1-4ff4-a055-99cc6cd6f8c6
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugControl2, IDebugControl2 interface [Windows Debugging], IDebugControl2 interface [Windows Debugging],described, dbgeng/IDebugControl2, debugger.idebugcontrol2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
-	IDebugControl2
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugControl2</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>. <b>IDebugControl2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugControl2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545883">GetCurrentSystemUpTime</a>
</td>
<td align="left" width="63%">
Returns the number of seconds the current target's computer has been running since it was last started.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546553">GetCurrentTimeDate</a>
</td>
<td align="left" width="63%">
Returns the time of the current target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546592">GetDumpFormatFlags</a>
</td>
<td align="left" width="63%">
Returns the flags that describe what information is available in a dump file target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547988">GetNumberTextReplacements</a>
</td>
<td align="left" width="63%">
Returns the number of currently defined user-named and automatic aliases.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549280">GetTextReplacement</a>
</td>
<td align="left" width="63%">
Returns the value of a user-named alias or an automatic alias.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553268">OutputTextReplacements</a>
</td>
<td align="left" width="63%">
Prints all the currently defined user-named aliases to the debugger's output stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554548">RemoveTextReplacements</a>
</td>
<td align="left" width="63%">
Removes all user-named aliases.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556818">SetTextReplacement</a>
</td>
<td align="left" width="63%">
Sets the value of a user-named alias.  

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
 

 

