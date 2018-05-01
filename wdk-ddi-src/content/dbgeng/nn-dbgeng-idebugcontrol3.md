---
UID: NN:dbgeng.IDebugControl3
title: IDebugControl3
author: windows-driver-content
description: IDebugControl3 interface
old-location: debugger\idebugcontrol3.htm
old-project: debugger
ms.assetid: 95e714b4-4167-41a1-ab2c-b088dbaf5fe2
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugControl3, IDebugControl3 interface [Windows Debugging], IDebugControl3 interface [Windows Debugging],described, dbgeng/IDebugControl3, debugger.idebugcontrol3
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl3
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugControl3</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>. <b>IDebugControl3</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugControl3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537852">AddAssemblyOptions</a>
</td>
<td align="left" width="63%">
Turns on some of the assembly and disassembly options.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>
</td>
<td align="left" width="63%">
Returns the assembly and disassembly options that affect how the debugger engine assembles and disassembles processor instructions for the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545755">GetCurrentEventIndex</a>
</td>
<td align="left" width="63%">
Returns the index of the current event within the current list of events for the current target, if such a list exists.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546630">GetEventIndexDescription</a>
</td>
<td align="left" width="63%">
Describes the specified event in a static list of events for the current target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546701">GetExpressionSyntax</a>
</td>
<td align="left" width="63%">
Returns the current syntax that the engine is using for evaluating expressions.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546708">GetExpressionSyntaxNames</a>
</td>
<td align="left" width="63%">
Returns the full and abbreviated names of an expression syntax.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547906">GetNumberEvents</a>
</td>
<td align="left" width="63%">
Returns the number of events for the current target, if the number of events is fixed.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547913">GetNumberExpressionSyntaxes</a>
</td>
<td align="left" width="63%">
Returns the number of expression syntaxes that are supported by the engine.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554483">RemoveAssemblyOptions</a>
</td>
<td align="left" width="63%">
 Turns off some of the assembly and disassembly options.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556626">SetAssemblyOptions</a>
</td>
<td align="left" width="63%">
Sets the assembly and disassembly options that affect how the debugger engine assembles and disassembles processor instructions for the target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556696">SetExpressionSyntax</a>
</td>
<td align="left" width="63%">
Sets the syntax that the engine will use to evaluate expressions.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556697">SetExpressionSyntaxByName</a>
</td>
<td align="left" width="63%">
Sets the syntax that the engine will use to evaluate expressions.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556737">SetNextEventIndex</a>
</td>
<td align="left" width="63%">
Sets the next event for the current target by selecting the event from the static list of events for the target, if such a list exists.


</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
 

 

