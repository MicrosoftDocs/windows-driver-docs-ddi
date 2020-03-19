---
UID: NN:dbgeng.IDebugEventContextCallbacks
title: IDebugEventContextCallbacks (dbgeng.h)
description: This interface supports event context callbacks and replaces the use of the IDebugClient::SetEventCallbacks method.
old-location: debugger\idebugeventcontextcallbacks.htm
tech.root: debugger
ms.assetid: F4FAA5C9-B7D9-43B6-8B1D-CA790522900C
ms.date: 05/03/2018
keywords: ["IDebugEventContextCallbacks interface"]
ms.keywords: IDebugEventContextCallbacks, IDebugEventContextCallbacks interface [Windows Debugging], IDebugEventContextCallbacks interface [Windows Debugging],described, dbgeng/IDebugEventContextCallbacks, debugger.idebugeventcontextcallbacks
f1_keywords:
 - "dbgeng/IDebugEventContextCallbacks"
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
- dbgeng.h
api_name:
- IDebugEventContextCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventContextCallbacks interface


## -description


This interface supports event context callbacks and replaces the use of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-seteventcallbacks">IDebugClient::SetEventCallbacks</a> method.

Set this interface on a debugger client by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient6-seteventcontextcallbacks">IDebugClient6::SetEventContextCallbacks</a> method.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient6-seteventcontextcallbacks">IDebugClient6::SetEventContextCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-seteventcallbacks">IDebugClient::SetEventCallbacks</a>
 

 

