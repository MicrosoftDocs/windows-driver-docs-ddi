---
UID: NS:dbgeng._DEBUG_CLIENT_CONTEXT
title: "_DEBUG_CLIENT_CONTEXT"
author: windows-driver-content
description: Contains a debug client constant to provide to the IDebugClient7::SetClientContext method.
old-location: debugger\debug_client_context.htm
old-project: debugger
ms.assetid: 69CE0535-3ADD-481C-A016-695A7303BBA5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDEBUG_CLIENT_CONTEXT, DEBUG_CLIENT_CONTEXT, DEBUG_CLIENT_CONTEXT structure [Windows Debugging], PDEBUG_CLIENT_CONTEXT, PDEBUG_CLIENT_CONTEXT structure pointer [Windows Debugging], _DEBUG_CLIENT_CONTEXT, dbgeng/DEBUG_CLIENT_CONTEXT, dbgeng/PDEBUG_CLIENT_CONTEXT, debugger.debug_client_context"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
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
-	HeaderDef
api_location:
-	DbgEng.h
api_name:
-	DEBUG_CLIENT_CONTEXT
product: Windows
targetos: Windows
req.typenames: DEBUG_CLIENT_CONTEXT, *PDEBUG_CLIENT_CONTEXT
---

# _DEBUG_CLIENT_CONTEXT structure


## -description


Contains a debug client constant to provide to the <a href="https://msdn.microsoft.com/235DA791-D4D1-486C-B136-3703E62E91E2">IDebugClient7::SetClientContext</a>  method. 


## -syntax


````
typedef struct _DEBUG_CLIENT_CONTEXT {
  UINT cbSize;
  UINT eClient;
} DEBUG_CLIENT_CONTEXT, *PDEBUG_CLIENT_CONTEXT;
````


## -struct-fields




### -field cbSize

A size value.


### -field eClient

A client value.


## -see-also

<a href="https://msdn.microsoft.com/235DA791-D4D1-486C-B136-3703E62E91E2">IDebugClient7::SetClientContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_CLIENT_CONTEXT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

