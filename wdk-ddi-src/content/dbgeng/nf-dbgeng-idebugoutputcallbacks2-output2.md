---
UID: NF:dbgeng.IDebugOutputCallbacks2.Output2
title: IDebugOutputCallbacks2::Output2 (dbgeng.h)
description: Returns notifications for the IDebugOutputCallbacks2 interface.
old-location: debugger\idebugoutputcallbacks2_output2.htm
tech.root: debugger
ms.assetid: 2FFF9B54-6E77-4D46-B6C0-5BADD208BFCC
ms.date: 11/29/2018
keywords: ["IDebugOutputCallbacks2::Output2"]
ms.keywords: DEBUG_OUTCBI_ANY_FORMAT, DEBUG_OUTCBI_DML, DEBUG_OUTCBI_EXPLICIT_FLUSH, DEBUG_OUTCBI_TEXT, IDebugOutputCallbacks2 interface [Windows Debugging],Output2 method, IDebugOutputCallbacks2.Output2, IDebugOutputCallbacks2::Output2, Output2, Output2 method [Windows Debugging], Output2 method [Windows Debugging],IDebugOutputCallbacks2 interface, dbgeng/IDebugOutputCallbacks2::Output2, debugger.idebugoutputcallbacks2_output2
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
 - IDebugOutputCallbacks2::Output2
 - dbgeng/IDebugOutputCallbacks2::Output2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugOutputCallbacks2.Output2
---

# IDebugOutputCallbacks2::Output2


## -description

Returns notifications for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks2">IDebugOutputCallbacks2</a> interface.

## -parameters

### -param Which 

[in]
The kind of DEBUG_OUTCB_XXX notification that is coming in. The DEBUG_OUTCB_XXX notifications are defined in the dbgeng.h header using  #defines. For more information, see [DEBUG_OUTCB_XXX](https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outcb-xxx).

### -param Flags 

[in]
Flags that are part of the notification payload.

### -param Arg 

[in]
Arguments that are part of the notification payload.

### -param Text 

[in, optional]
A pointer to text that is part of the notification payload.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks2">IDebugOutputCallbacks2</a>

