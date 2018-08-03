---
UID: NF:dbgeng.IDebugSystemObjects3.SetCurrentSystemId
title: IDebugSystemObjects3::SetCurrentSystemId
author: windows-driver-content
description: The SetCurrentSystemId method makes the specified target the current target.
old-location: debugger\setcurrentsystemid.htm
tech.root: debugger
ms.assetid: 95b761ff-ca78-4793-b5eb-a9ff35a963d3
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: IDebugSystemObjects3 interface [Windows Debugging],SetCurrentSystemId method, IDebugSystemObjects3.SetCurrentSystemId, IDebugSystemObjects3::SetCurrentSystemId, IDebugSystemObjects4 interface [Windows Debugging],SetCurrentSystemId method, IDebugSystemObjects4::SetCurrentSystemId, IDebugSystemObjects_70a23767-a18b-4920-828a-34fe863fec4a.xml, SetCurrentSystemId, SetCurrentSystemId method [Windows Debugging], SetCurrentSystemId method [Windows Debugging],IDebugSystemObjects3 interface, SetCurrentSystemId method [Windows Debugging],IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects3::SetCurrentSystemId, dbgeng/IDebugSystemObjects4::SetCurrentSystemId, debugger.setcurrentsystemid
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
-	IDebugSystemObjects3.SetCurrentSystemId
-	IDebugSystemObjects4.SetCurrentSystemId
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects3::SetCurrentSystemId


## -description


The <b>SetCurrentSystemId</b> method makes the specified target the current target.


## -parameters




### -param Id [in]

Specifies the engine target ID for the target that is to become the current target.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No process with the given ID was found.

</td>
</tr>
</table>
 




## -remarks



This method also sets the current thread and current process, and may change the current computer.

If the current target is changed, the callback <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> will be called with the DEBUG_CES_CURRENT_THREAD bit set.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550892">IDebugSystemObjects3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550893">IDebugSystemObjects4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>
 

 

