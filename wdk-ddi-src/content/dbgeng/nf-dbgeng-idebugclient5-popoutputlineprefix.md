---
UID: NF:dbgeng.IDebugClient5.PopOutputLinePrefix
title: IDebugClient5::PopOutputLinePrefix (dbgeng.h)
description: Restores a previously saved output line prefix.
old-location: debugger\idebugclient5_popoutputlineprefix.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient5::PopOutputLinePrefix"]
ms.keywords: IDebugClient5 interface [Windows Debugging],PopOutputLinePrefix method, IDebugClient5.PopOutputLinePrefix, IDebugClient5::PopOutputLinePrefix, PopOutputLinePrefix, PopOutputLinePrefix method [Windows Debugging], PopOutputLinePrefix method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::PopOutputLinePrefix, debugger.idebugclient5_popoutputlineprefix
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
 - IDebugClient5::PopOutputLinePrefix
 - dbgeng/IDebugClient5::PopOutputLinePrefix
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient5.PopOutputLinePrefix
---

# IDebugClient5::PopOutputLinePrefix


## -description

  Restores a previously saved output line prefix.

## -parameters

### -param Handle 

[in]
The handle of a previously pushed prefix.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
