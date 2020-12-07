---
UID: NF:dbgeng.IDebugClient5.SetQuitLockString
title: IDebugClient5::SetQuitLockString (dbgeng.h)
description: Sets a quit lock string.
old-location: debugger\idebugclient5_setquitlockstring.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient5::SetQuitLockString"]
ms.keywords: IDebugClient5 interface [Windows Debugging],SetQuitLockString method, IDebugClient5.SetQuitLockString, IDebugClient5::SetQuitLockString, SetQuitLockString, SetQuitLockString method [Windows Debugging], SetQuitLockString method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::SetQuitLockString, debugger.idebugclient5_setquitlockstring
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
 - IDebugClient5::SetQuitLockString
 - dbgeng/IDebugClient5::SetQuitLockString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient5.SetQuitLockString
---

# IDebugClient5::SetQuitLockString


## -description

Sets a quit lock string.

## -parameters

### -param String 

[in]
A pointer to the quit lock string.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

    This function provides control over locking the session against
    undesired quits.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
