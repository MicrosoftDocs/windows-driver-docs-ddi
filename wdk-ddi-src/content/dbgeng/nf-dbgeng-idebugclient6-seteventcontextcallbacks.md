---
UID: NF:dbgeng.IDebugClient6.SetEventContextCallbacks
title: IDebugClient6::SetEventContextCallbacks (dbgeng.h)
description: Registers an event callbacks object with this client.
old-location: debugger\idebugclient6_seteventcontextcallbacks.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient6::SetEventContextCallbacks"]
ms.keywords: IDebugClient6 interface [Windows Debugging],SetEventContextCallbacks method, IDebugClient6.SetEventContextCallbacks, IDebugClient6::SetEventContextCallbacks, SetEventContextCallbacks, SetEventContextCallbacks method [Windows Debugging], SetEventContextCallbacks method [Windows Debugging],IDebugClient6 interface, dbgeng/IDebugClient6::SetEventContextCallbacks, debugger.idebugclient6_seteventcontextcallbacks
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugClient6::SetEventContextCallbacks
 - dbgeng/IDebugClient6::SetEventContextCallbacks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient6.SetEventContextCallbacks
---

# IDebugClient6::SetEventContextCallbacks


## -description

Registers an event callbacks object with this client.

## -parameters

### -param Callbacks 

[in, optional]
The interface pointer to the event callbacks object.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

This event interface replaces the use of <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-seteventcallbacks">IDebugClient::SetEventCallbacks</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient6">IDebugClient6</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-seteventcallbacks">IDebugClient::SetEventCallbacks</a>
