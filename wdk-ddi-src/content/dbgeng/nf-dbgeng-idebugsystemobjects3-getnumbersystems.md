---
UID: NF:dbgeng.IDebugSystemObjects3.GetNumberSystems
title: IDebugSystemObjects3::GetNumberSystems (dbgeng.h)
description: The GetNumberSystems method returns the number of targets to which the engine is currently connected.
old-location: debugger\getnumbersystems.htm
tech.root: debugger
ms.assetid: 27465cd9-77bc-4c9e-bac6-bd471ca93261
ms.date: 05/03/2018
ms.keywords: GetNumberSystems, GetNumberSystems method [Windows Debugging], GetNumberSystems method [Windows Debugging],IDebugSystemObjects3 interface, GetNumberSystems method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects3 interface [Windows Debugging],GetNumberSystems method, IDebugSystemObjects3.GetNumberSystems, IDebugSystemObjects3::GetNumberSystems, IDebugSystemObjects4 interface [Windows Debugging],GetNumberSystems method, IDebugSystemObjects4::GetNumberSystems, IDebugSystemObjects_821c2f0e-0863-4300-b26e-93e86ad9f0dd.xml, dbgeng/IDebugSystemObjects3::GetNumberSystems, dbgeng/IDebugSystemObjects4::GetNumberSystems, debugger.getnumbersystems
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugSystemObjects3.GetNumberSystems
- IDebugSystemObjects4.GetNumberSystems
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects3::GetNumberSystems


## -description


The <b>GetNumberSystems</b> method returns the number of targets to which the engine is currently connected.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550892">IDebugSystemObjects3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550893">IDebugSystemObjects4</a>
 

 

