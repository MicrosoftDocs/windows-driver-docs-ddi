---
UID: NF:dbgeng.IDebugSystemObjects4.GetEventSystem
title: IDebugSystemObjects4::GetEventSystem method
author: windows-driver-content
description: The GetEventSystem method returns the engine target ID for the target in which the last event occurred.
old-location: debugger\geteventsystem.htm
old-project: debugger
ms.assetid: b0a3ce92-b29a-4c5e-8cab-18fc92787e2e
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects3::GetEventSystem, GetEventSystem method [Windows Debugging], IDebugSystemObjects4 interface, IDebugSystemObjects4, dbgeng/IDebugSystemObjects3::GetEventSystem, IDebugSystemObjects4::GetEventSystem, IDebugSystemObjects3 interface [Windows Debugging], GetEventSystem method, dbgeng/IDebugSystemObjects4::GetEventSystem, GetEventSystem, IDebugSystemObjects_6cb96e5a-e9a5-4ff7-9f36-a7770bc77ef1.xml, GetEventSystem method [Windows Debugging], IDebugSystemObjects3 interface, debugger.geteventsystem, GetEventSystem method [Windows Debugging], IDebugSystemObjects4 interface [Windows Debugging], GetEventSystem method
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
-	IDebugSystemObjects3.GetEventSystem
-	IDebugSystemObjects4.GetEventSystem
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugSystemObjects4::GetEventSystem method


## -description


The <b>GetEventSystem</b> method returns the engine target ID for the target in which the last event occurred.


## -syntax


````
HRESULT GetEventSystem(
  [out] PULONG Id
);
````


## -parameters




### -param Id [out]

Receives the engine target ID.


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



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>

<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects3.md">IDebugSystemObjects3</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>

<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects4.md">IDebugSystemObjects4</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSystemObjects3::GetEventSystem method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

