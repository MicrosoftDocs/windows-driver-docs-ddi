---
UID: NF:dbgeng.IDebugControl3.GetInterruptTimeout
title: IDebugControl3::GetInterruptTimeout
author: windows-driver-content
description: The GetInterruptTimeout method returns the number of seconds that the engine will wait when requesting a break into the debugger.
old-location: debugger\getinterrupttimeout.htm
old-project: debugger
ms.assetid: 8faf167e-3110-453f-8234-32dfa543b520
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetInterruptTimeout, GetInterruptTimeout method [Windows Debugging], GetInterruptTimeout method [Windows Debugging],IDebugControl interface, GetInterruptTimeout method [Windows Debugging],IDebugControl2 interface, GetInterruptTimeout method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetInterruptTimeout method, IDebugControl2 interface [Windows Debugging],GetInterruptTimeout method, IDebugControl2::GetInterruptTimeout, IDebugControl3 interface [Windows Debugging],GetInterruptTimeout method, IDebugControl3.GetInterruptTimeout, IDebugControl3::GetInterruptTimeout, IDebugControl::GetInterruptTimeout, IDebugControl_33383d54-faba-46a1-8e14-8a3215b0d2f7.xml, dbgeng/IDebugControl2::GetInterruptTimeout, dbgeng/IDebugControl3::GetInterruptTimeout, dbgeng/IDebugControl::GetInterruptTimeout, debugger.getinterrupttimeout
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
-	IDebugControl.GetInterruptTimeout
-	IDebugControl2.GetInterruptTimeout
-	IDebugControl3.GetInterruptTimeout
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetInterruptTimeout


## -description


The <b>GetInterruptTimeout</b> method returns the number of seconds that the engine will wait when requesting a break into the debugger.


## -parameters




### -param Seconds [out]

Receives the number of seconds that the engine will wait for the target when requesting a break into the debugger.


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



The engine requests a break into the debugger when <a href="https://msdn.microsoft.com/library/windows/hardware/ff556722">SetInterrupt</a> is called with DEBUG_INTERRUPT_ACTIVE.  If this interrupt times out, the engine will generate a synthetic exception event.  This event will be sent to <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">event callback objects</a>'s <a href="https://msdn.microsoft.com/library/windows/hardware/ff550717">IDebugEventCallbacks::Exception</a> method.

Most targets do not support interrupt time-outs.  Live user-mode debugging is one of the targets that does support them.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550717">IDebugEventCallbacks::Exception</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556722">SetInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556725">SetInterruptTimeout</a>
 

 

