---
UID: NF:dbgeng.IDebugClient6.SetEventContextCallbacks
title: IDebugClient6::SetEventContextCallbacks method
author: windows-driver-content
description: Registers an event callbacks object with this client.
old-location: debugger\idebugclient6_seteventcontextcallbacks.htm
old-project: debugger
ms.assetid: 246573DB-5FEB-4068-8DB8-950F5EDFD1A9
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugClient6, IDebugClient6 interface [Windows Debugging], SetEventContextCallbacks method, IDebugClient6::SetEventContextCallbacks, SetEventContextCallbacks method [Windows Debugging], SetEventContextCallbacks method [Windows Debugging], IDebugClient6 interface, SetEventContextCallbacks,IDebugClient6.SetEventContextCallbacks, dbgeng/IDebugClient6::SetEventContextCallbacks, debugger.idebugclient6_seteventcontextcallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient6.SetEventContextCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient6::SetEventContextCallbacks method


## -description


Registers an event callbacks object with this client. 


## -parameters




### -param Callbacks [in, optional]

The interface pointer to the event callbacks object.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

This event interface replaces the use of <a href="https://msdn.microsoft.com/c741777b-dfaf-42b0-9dd7-6678281b6359">IDebugClient::SetEventCallbacks</a>. 




## -see-also




<a href="https://msdn.microsoft.com/9F8DFF33-DE07-4061-9A9E-3C8172F75EB5">IDebugClient6</a>



<a href="https://msdn.microsoft.com/c741777b-dfaf-42b0-9dd7-6678281b6359">IDebugClient::SetEventCallbacks</a>
 

 

