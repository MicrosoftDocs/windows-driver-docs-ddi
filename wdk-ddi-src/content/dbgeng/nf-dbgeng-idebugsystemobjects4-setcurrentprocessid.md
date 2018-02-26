---
UID: NF:dbgeng.IDebugSystemObjects4.SetCurrentProcessId
title: IDebugSystemObjects4::SetCurrentProcessId method
author: windows-driver-content
description: The SetCurrentProcessId method makes the specified process the current process.
old-location: debugger\setcurrentprocessid.htm
old-project: debugger
ms.assetid: 65129c6e-5c69-409b-95f5-07b98a494533
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 4, :, C, D, I, IDebugSystemObjects, IDebugSystemObjects interface [Windows Debugging], SetCurrentProcessId method, IDebugSystemObjects2, IDebugSystemObjects2 interface [Windows Debugging], SetCurrentProcessId method, IDebugSystemObjects2::SetCurrentProcessId, IDebugSystemObjects3, IDebugSystemObjects3 interface [Windows Debugging], SetCurrentProcessId method, IDebugSystemObjects3::SetCurrentProcessId, IDebugSystemObjects4, IDebugSystemObjects4 interface [Windows Debugging], SetCurrentProcessId method, IDebugSystemObjects4::SetCurrentProcessId, IDebugSystemObjects::SetCurrentProcessId, IDebugSystemObjects_e588cabd-e079-4dc0-ab0f-085181414985.xml, O, P, S, SetCurrentProcessId method [Windows Debugging], SetCurrentProcessId method [Windows Debugging], IDebugSystemObjects interface, SetCurrentProcessId method [Windows Debugging], IDebugSystemObjects2 interface, SetCurrentProcessId method [Windows Debugging], IDebugSystemObjects3 interface, SetCurrentProcessId method [Windows Debugging], IDebugSystemObjects4 interface, SetCurrentProcessId,IDebugSystemObjects.SetCurrentProcessId, SetCurrentProcessId,IDebugSystemObjects2.SetCurrentProcessId, SetCurrentProcessId,IDebugSystemObjects3.SetCurrentProcessId, SetCurrentProcessId,IDebugSystemObjects4.SetCurrentProcessId, b, c, d, dbgeng/IDebugSystemObjects2::SetCurrentProcessId, dbgeng/IDebugSystemObjects3::SetCurrentProcessId, dbgeng/IDebugSystemObjects4::SetCurrentProcessId, dbgeng/IDebugSystemObjects::SetCurrentProcessId, debugger.setcurrentprocessid, e, g, j, m, n, o, r, s, t, u, y"
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
-	IDebugSystemObjects.SetCurrentProcessId
-	IDebugSystemObjects2.SetCurrentProcessId
-	IDebugSystemObjects3.SetCurrentProcessId
-	IDebugSystemObjects4.SetCurrentProcessId
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects4::SetCurrentProcessId method


## -description


The <b>SetCurrentProcessId</b> method makes the specified process the current process.


## -syntax


````
HRESULT SetCurrentProcessId(
  [in] ULONG Id
);
````


## -parameters




### -param Id [in]

Specifies the engine process ID for the process that is to become the current process.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No process with the given process ID was found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
No suitable candidate for the current thread could be found in the process.

</td>
</tr>
</table>
 




## -remarks



This method also changes the current thread, and may change the current target and current computer.

If the process is changed, the callback <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> will be called with the DEBUG_CES_CURRENT_THREAD bit set.

<div class="alert"><b>Note</b>    In kernel-mode debugging, the current process is a virtual process, it is not a system process.  This method cannot be used to change between system processes in kernel-mode debugging.  However, the implicit process may be changed by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff556713">SetImplicitProcessDataOffset</a>.</div>
<div> </div>
For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on monitoring events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.



