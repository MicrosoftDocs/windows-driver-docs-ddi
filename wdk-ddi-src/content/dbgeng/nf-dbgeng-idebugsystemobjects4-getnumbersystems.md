---
UID: NF:dbgeng.IDebugSystemObjects4.GetNumberSystems
title: IDebugSystemObjects4::GetNumberSystems (dbgeng.h)
description: The GetNumberSystems method returns the number of targets to which the engine is currently connected.
old-location: debugger\getnumbersystems.htm
tech.root: debugger
ms.assetid: 27465cd9-77bc-4c9e-bac6-bd471ca93261
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects4::GetNumberSystems"]
ms.keywords: GetNumberSystems, GetNumberSystems method [Windows Debugging], GetNumberSystems method [Windows Debugging],IDebugSystemObjects3 interface, GetNumberSystems method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects3 interface [Windows Debugging],GetNumberSystems method, IDebugSystemObjects3::GetNumberSystems, IDebugSystemObjects4 interface [Windows Debugging],GetNumberSystems method, IDebugSystemObjects4.GetNumberSystems, IDebugSystemObjects4::GetNumberSystems, IDebugSystemObjects_821c2f0e-0863-4300-b26e-93e86ad9f0dd.xml, dbgeng/IDebugSystemObjects3::GetNumberSystems, dbgeng/IDebugSystemObjects4::GetNumberSystems, debugger.getnumbersystems
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugSystemObjects4::GetNumberSystems
 - dbgeng/IDebugSystemObjects4::GetNumberSystems
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
---

# IDebugSystemObjects4::GetNumberSystems


## -description

The <b>GetNumberSystems</b> method returns the number of targets to which the engine is currently connected.

## -parameters

### -param Number 

[out]
Receives the number of targets.

## -returns

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-session-and-execution-model">Debugging Session and Execution Model</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsystemobjects3">IDebugSystemObjects3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsystemobjects4">IDebugSystemObjects4</a>

