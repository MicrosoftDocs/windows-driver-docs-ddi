---
UID: NN:dbgeng.IDebugRegisters
title: IDebugRegisters
author: windows-driver-content
description: IDebugRegisters interface
old-location: debugger\idebugregisters.htm
old-project: debugger
ms.assetid: a2587ea7-20cd-43be-ba71-750e699ee0ce
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.idebugregisters, IDebugRegisters interface [Windows Debugging], IDebugRegisters interface [Windows Debugging], described, IDebugRegisters, dbgeng/IDebugRegisters, IDebugRegisters_ca710692-a977-4276-b779-2b66311938dc.xml
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
-	IDebugRegisters
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugRegisters interface


## -description




## -members

The <b>IDebugRegisters</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546575">GetDescription</a>
</td>
<td align="left" width="63%">
Returns the description of a register.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546806">GetFrameOffset</a>
</td>
<td align="left" width="63%">
Returns the location of the stack frame for the current function.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546881">GetIndexByName</a>
</td>
<td align="left" width="63%">
Returns the index of the named register.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546916">GetInstructionOffset</a>
</td>
<td align="left" width="63%">
Returns the location of the current thread's current instruction.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547960">GetNumberRegisters</a>
</td>
<td align="left" width="63%">
Returns the number of registers on the target computer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548403">GetStackOffset</a>
</td>
<td align="left" width="63%">
Returns the current thread's current stack location.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597624">GetValue</a>
</td>
<td align="left" width="63%">
Gets the value of one of the target's registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549480">GetValues</a>
</td>
<td align="left" width="63%">
Gets the value of several of the target's registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553242">OutputRegisters</a>
</td>
<td align="left" width="63%">
Formats and sends the target's registers to the clients as output.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597642">SetValue</a>
</td>
<td align="left" width="63%">
Sets the value of one of the target's registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556883">SetValues</a>
</td>
<td align="left" width="63%">
Sets the value of several of the target's registers.

</td>
</tr>
</table>Returns the description of a register.

Returns the location of the stack frame for the current function.

Returns the index of the named register.

Returns the location of the current thread's current instruction.

Returns the number of registers on the target computer.

Returns the current thread's current stack location.

Gets the value of one of the target's registers.

Gets the value of several of the target's registers.

Formats and sends the target's registers to the clients as output.

Sets the value of one of the target's registers.

Sets the value of several of the target's registers.

 


## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugRegisters interface%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

