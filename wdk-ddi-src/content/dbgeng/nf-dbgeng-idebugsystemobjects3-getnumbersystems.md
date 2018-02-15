---
UID: NF:dbgeng.IDebugSystemObjects3.GetNumberSystems
title: IDebugSystemObjects3::GetNumberSystems method
author: windows-driver-content
description: The GetNumberSystems method returns the number of targets to which the engine is currently connected.
old-location: debugger\getnumbersystems.htm
old-project: debugger
ms.assetid: 27465cd9-77bc-4c9e-bac6-bd471ca93261
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetNumberSystems, IDebugSystemObjects4 interface [Windows Debugging], GetNumberSystems method, GetNumberSystems method [Windows Debugging], IDebugSystemObjects4 interface, GetNumberSystems method [Windows Debugging], dbgeng/IDebugSystemObjects3::GetNumberSystems, debugger.getnumbersystems, dbgeng/IDebugSystemObjects4::GetNumberSystems, IDebugSystemObjects3 interface [Windows Debugging], GetNumberSystems method, IDebugSystemObjects_821c2f0e-0863-4300-b26e-93e86ad9f0dd.xml, GetNumberSystems method [Windows Debugging], IDebugSystemObjects3 interface, IDebugSystemObjects3, IDebugSystemObjects4::GetNumberSystems, IDebugSystemObjects3::GetNumberSystems
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
-	IDebugSystemObjects3.GetNumberSystems
-	IDebugSystemObjects4.GetNumberSystems
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSystemObjects3::GetNumberSystems method


## -description


The <b>GetNumberSystems</b> method returns the number of targets to which the engine is currently connected.


## -syntax


````
HRESULT GetNumberSystems(
  [out] PULONG Number
);
````


## -parameters




### -param Number [out]

Receives the number of targets.


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

<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects4.md">IDebugSystemObjects4</a>



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects3.md">IDebugSystemObjects3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSystemObjects3::GetNumberSystems method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

