---
UID: NF:dbgeng.IDebugClient6.SetEventContextCallbacks
title: IDebugClient6::SetEventContextCallbacks (dbgeng.h)
description: Registers an event callbacks object with this client.
old-location: debugger\idebugclient6_seteventcontextcallbacks.htm
tech.root: debugger
ms.assetid: 246573DB-5FEB-4068-8DB8-950F5EDFD1A9
ms.date: 05/03/2018
ms.keywords: IDebugClient6 interface [Windows Debugging],SetEventContextCallbacks method, IDebugClient6.SetEventContextCallbacks, IDebugClient6::SetEventContextCallbacks, SetEventContextCallbacks, SetEventContextCallbacks method [Windows Debugging], SetEventContextCallbacks method [Windows Debugging],IDebugClient6 interface, dbgeng/IDebugClient6::SetEventContextCallbacks, debugger.idebugclient6_seteventcontextcallbacks
ms.topic: method
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
- IDebugClient6.SetEventContextCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient6::SetEventContextCallbacks


## -description


Registers an event callbacks object with this client. 


## -parameters




### -param Callbacks [in, optional]

The interface pointer to the event callbacks object.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

This event interface replaces the use of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-seteventcallbacks">IDebugClient::SetEventCallbacks</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient6">IDebugClient6</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-seteventcallbacks">IDebugClient::SetEventCallbacks</a>
 

 

