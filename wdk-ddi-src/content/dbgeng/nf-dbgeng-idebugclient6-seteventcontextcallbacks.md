---
UID: NF:dbgeng.IDebugClient6.SetEventContextCallbacks
title: IDebugClient6::SetEventContextCallbacks method
author: windows-driver-content
description: Registers an event callbacks object with this client.
old-location: debugger\idebugclient6_seteventcontextcallbacks.htm
old-project: debugger
ms.assetid: 246573DB-5FEB-4068-8DB8-950F5EDFD1A9
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient6 interface [Windows Debugging], SetEventContextCallbacks method, SetEventContextCallbacks, IDebugClient6, IDebugClient6::SetEventContextCallbacks, SetEventContextCallbacks method [Windows Debugging], dbgeng/IDebugClient6::SetEventContextCallbacks, debugger.idebugclient6_seteventcontextcallbacks, SetEventContextCallbacks method [Windows Debugging], IDebugClient6 interface
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
-	IDebugClient6.SetEventContextCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient6::SetEventContextCallbacks method


## -description


Registers an event callbacks object with this client. 


## -syntax


````
HRESULT SetEventContextCallbacks(
  [in, optional] PDEBUG_EVENT_CONTEXT_CALLBACKS Callbacks

);
````


## -parameters




### -param Callbacks [in, optional]

The interface pointer to the event callbacks object.


## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

This event interface replaces the use of <a href="https://msdn.microsoft.com/c741777b-dfaf-42b0-9dd7-6678281b6359">IDebugClient::SetEventCallbacks</a>. 



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugclient6.md">IDebugClient6</a>

<a href="https://msdn.microsoft.com/c741777b-dfaf-42b0-9dd7-6678281b6359">IDebugClient::SetEventCallbacks</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient6::SetEventContextCallbacks method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

