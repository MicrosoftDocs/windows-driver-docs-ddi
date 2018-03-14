---
UID: NN:dbgeng.IDebugRegisters2
title: IDebugRegisters2
author: windows-driver-content
description: IDebugRegisters2 interface
old-location: debugger\idebugregisters2.htm
old-project: debugger
ms.assetid: f92a75a9-6578-4bbf-8d80-680493b4d284
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugRegisters2, IDebugRegisters2 interface [Windows Debugging], IDebugRegisters2 interface [Windows Debugging], described, dbgeng/IDebugRegisters2, debugger.idebugregisters2
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
-	IDebugRegisters2
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugRegisters2 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugRegisters2</b> interface inherits from <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a>. <b>IDebugRegisters2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugRegisters2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546578">GetDescriptionWide</a>
</td>
<td align="left" width="63%">
Returns the description of a register.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546815">GetFrameOffset2</a>
</td>
<td align="left" width="63%">
Returns the location of the stack frame for the current function.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546889">GetIndexByNameWide</a>
</td>
<td align="left" width="63%">
Returns the index of the named register.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546933">GetInstructionOffset2</a>
</td>
<td align="left" width="63%">
Returns the location of the current thread's current instruction.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547957">GetNumberPseudoRegisters</a>
</td>
<td align="left" width="63%">
Returns the number of pseudo-registers that are maintained by the debugger engine.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548189">GetPseudoDescription</a>
</td>
<td align="left" width="63%">
Returns a description of a pseudo-register, including its name and type. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548194">GetPseudoDescriptionWide</a>
</td>
<td align="left" width="63%">
Returns a description of a pseudo-register, including its name and type. (Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548206">GetPseudoIndexByName</a>
</td>
<td align="left" width="63%">
Returns the index of a pseudo-register. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548211">GetPseudoIndexByNameWide</a>
</td>
<td align="left" width="63%">
Returns the index of a pseudo-register. (Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548215">GetPseudoValues</a>
</td>
<td align="left" width="63%">
Returns the values of a number of pseudo-registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548414">GetStackOffset2</a>
</td>
<td align="left" width="63%">
Returns the current thread's current stack location.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549487">GetValues2</a>
</td>
<td align="left" width="63%">
Fetches the value of several of the target's registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553245">OutputRegisters2</a>
</td>
<td align="left" width="63%">
Formats and outputs the target's registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556767">SetPseudoValues</a>
</td>
<td align="left" width="63%">
Sets the value of several pseudo-registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556884">SetValues2</a>
</td>
<td align="left" width="63%">
Sets the value of several of the target's registers.

</td>
</tr>
</table> 


## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugRegisters2 interface%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

