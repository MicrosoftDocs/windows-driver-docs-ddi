---
UID: NF:dbgeng.IDebugSystemObjects3.GetCurrentSystemServer
title: IDebugSystemObjects3::GetCurrentSystemServer (dbgeng.h)
description: Gets the server for the current process.
old-location: debugger\idebugsystemobjects3_getcurrentsystemserver.htm
tech.root: debugger
ms.assetid: 7956E4F6-7FB5-4349-81D2-4953108557D2
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects3::GetCurrentSystemServer"]
ms.keywords: GetCurrentSystemServer, GetCurrentSystemServer method [Windows Debugging], GetCurrentSystemServer method [Windows Debugging],IDebugSystemObjects3 interface, IDebugSystemObjects3 interface [Windows Debugging],GetCurrentSystemServer method, IDebugSystemObjects3.GetCurrentSystemServer, IDebugSystemObjects3::GetCurrentSystemServer, dbgeng/IDebugSystemObjects3::GetCurrentSystemServer, debugger.idebugsystemobjects3_getcurrentsystemserver
f1_keywords:
 - "dbgeng/IDebugSystemObjects3.GetCurrentSystemServer"
 - "IDebugSystemObjects3.GetCurrentSystemServer"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Dbgeng.h
api_name:
- IDebugSystemObjects3.GetCurrentSystemServer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects3::GetCurrentSystemServer


## -description


Gets the server for the current process.


## -parameters




### -param Server [out]

A pointer to the returned server value. 


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
 

 

