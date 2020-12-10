---
UID: NS:dbgeng._DEBUG_CLIENT_CONTEXT
title: _DEBUG_CLIENT_CONTEXT (dbgeng.h)
description: Contains a debug client constant to provide to the IDebugClient7::SetClientContext method.
old-location: debugger\debug_client_context.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["DEBUG_CLIENT_CONTEXT structure"]
ms.keywords: "*PDEBUG_CLIENT_CONTEXT, DEBUG_CLIENT_CONTEXT, DEBUG_CLIENT_CONTEXT structure [Windows Debugging], PDEBUG_CLIENT_CONTEXT, PDEBUG_CLIENT_CONTEXT structure pointer [Windows Debugging], _DEBUG_CLIENT_CONTEXT, dbgeng/DEBUG_CLIENT_CONTEXT, dbgeng/PDEBUG_CLIENT_CONTEXT, debugger.debug_client_context"
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
targetos: Windows
req.typenames: DEBUG_CLIENT_CONTEXT, *PDEBUG_CLIENT_CONTEXT
f1_keywords:
 - _DEBUG_CLIENT_CONTEXT
 - dbgeng/_DEBUG_CLIENT_CONTEXT
 - PDEBUG_CLIENT_CONTEXT
 - dbgeng/PDEBUG_CLIENT_CONTEXT
 - DEBUG_CLIENT_CONTEXT
 - dbgeng/DEBUG_CLIENT_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - DbgEng.h
api_name:
 - DEBUG_CLIENT_CONTEXT
---

# _DEBUG_CLIENT_CONTEXT structure


## -description

Contains a debug client constant to provide to the <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient7-setclientcontext">IDebugClient7::SetClientContext</a>  method.

## -struct-fields

### -field cbSize

A size value.

### -field eClient

A client value.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient7-setclientcontext">IDebugClient7::SetClientContext</a>
