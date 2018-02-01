---
UID: NF:dbgeng.IDebugClient7.SetClientContext
title: IDebugClient7::SetClientContext method
author: windows-driver-content
description: The SetClientContext method is reserved for internal use.
old-location: debugger\idebugclient7_setclientcontext.htm
old-project: debugger
ms.assetid: 235DA791-D4D1-486C-B136-3703E62E91E2
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient7 interface [Windows Debugging], SetClientContext method, dbgeng/IDebugClient7::SetClientContext, debugger.idebugclient7_setclientcontext, SetClientContext method [Windows Debugging], IDebugClient7 interface, SetClientContext method [Windows Debugging], IDebugClient7::SetClientContext, IDebugClient7, SetClientContext
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
-	IDebugClient7.SetClientContext
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient7::SetClientContext method


## -description


The <b>SetClientContext</b> method is reserved for internal use.


## -syntax


````
HRESULT SetClientContext(
  [in] _reads_bytes_(ContextSize) PVOID Context,
  [in] ULONG                            ContextSize
);
````


## -parameters




### -param Context [in]

The <b>SetClientContext</b> method is reserved for internal use.


### -param ContextSize [in]

The <b>SetClientContext</b> method is reserved for internal use.


## -returns


The <b>SetClientContext</b> method is reserved for internal use.



## -see-also

<a href="..\dbgeng\ns-dbgeng-_debug_client_context.md">DEBUG_CLIENT_CONTEXT</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient7.md">IDebugClient7</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient7::SetClientContext method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

