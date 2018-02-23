---
UID: NF:dbgeng.IDebugControl3.SetInterruptTimeout
title: IDebugControl3::SetInterruptTimeout method
author: windows-driver-content
description: The SetInterruptTimeout method sets the number of seconds that the debugger engine should wait when requesting a break into the debugger.
old-location: debugger\setinterrupttimeout.htm
old-project: Debugger
ms.assetid: 93bc2a07-a6f7-45df-945d-81c6c53adb47
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugControl3, IDebugControl, SetInterruptTimeout method [Windows Debugging], IDebugControl interface, IDebugControl3 interface [Windows Debugging], SetInterruptTimeout method, dbgeng/IDebugControl2::SetInterruptTimeout, IDebugControl2 interface [Windows Debugging], SetInterruptTimeout method, debugger.setinterrupttimeout, IDebugControl2::SetInterruptTimeout, IDebugControl2, dbgeng/IDebugControl::SetInterruptTimeout, IDebugControl_c16219f4-97b7-451d-8f04-30aa262667f6.xml, IDebugControl::SetInterruptTimeout, dbgeng/IDebugControl3::SetInterruptTimeout, SetInterruptTimeout method [Windows Debugging], IDebugControl3 interface, SetInterruptTimeout, SetInterruptTimeout method [Windows Debugging], IDebugControl3::SetInterruptTimeout, SetInterruptTimeout method [Windows Debugging], IDebugControl2 interface, IDebugControl interface [Windows Debugging], SetInterruptTimeout method
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
-	IDebugControl.SetInterruptTimeout
-	IDebugControl2.SetInterruptTimeout
-	IDebugControl3.SetInterruptTimeout
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::SetInterruptTimeout method


## -description


The <b>SetInterruptTimeout</b> method sets the number of seconds that the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> should wait when requesting a break into the debugger.


## -syntax


````
HRESULT SetInterruptTimeout(
  [in] ULONG Seconds
);
````


## -parameters




### -param Seconds [in]

Specifies the number of seconds that the engine should wait for the target when requesting a break into the debugger.


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



The engine requests a break into the debugger when <a href="https://msdn.microsoft.com/library/windows/hardware/ff556722">SetInterrupt</a> is called with the DEBUG_INTERRUPT_ACTIVE flag.  

If an interrupt times out, the engine will generate a synthetic exception event.  This event will be sent to <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">event callback objects</a>'s <a href="https://msdn.microsoft.com/library/windows/hardware/ff550717">IDebugEventCallbacks::Exception</a> method.

Most targets do not support interrupt time-outs.  Live user-mode debugging is one of the targets that does support them.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556722">SetInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546955">GetInterruptTimeout</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556722">SetInterrupt</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl::SetInterruptTimeout method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

