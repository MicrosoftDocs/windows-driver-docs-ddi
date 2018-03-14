---
UID: NF:dbgeng.IDebugClient7.SetClientContext
title: IDebugClient7::SetClientContext method
author: windows-driver-content
description: The SetClientContext method is reserved for internal use.
old-location: debugger\idebugclient7_setclientcontext.htm
old-project: debugger
ms.assetid: 235DA791-D4D1-486C-B136-3703E62E91E2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugClient7, IDebugClient7 interface [Windows Debugging], SetClientContext method, IDebugClient7::SetClientContext, SetClientContext method [Windows Debugging], SetClientContext method [Windows Debugging], IDebugClient7 interface, SetClientContext,IDebugClient7.SetClientContext, dbgeng/IDebugClient7::SetClientContext, debugger.idebugclient7_setclientcontext
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

<a href="..\dbgeng\nn-dbgeng-idebugclient7.md">IDebugClient7</a>



<a href="..\dbgeng\ns-dbgeng-_debug_client_context.md">DEBUG_CLIENT_CONTEXT</a>



 

 


