---
UID: NF:dbgeng.IDebugClient5.GetQuitLockString
title: IDebugClient5::GetQuitLockString (dbgeng.h)
description: Gets a quit lock string.
old-location: debugger\idebugclient5_getquitlockstring.htm
tech.root: debugger
ms.assetid: 986C866E-D5AC-47CD-A666-EDF739E91761
ms.date: 05/03/2018
keywords: ["IDebugClient5::GetQuitLockString"]
ms.keywords: GetQuitLockString, GetQuitLockString method [Windows Debugging], GetQuitLockString method [Windows Debugging],IDebugClient5 interface, IDebugClient5 interface [Windows Debugging],GetQuitLockString method, IDebugClient5.GetQuitLockString, IDebugClient5::GetQuitLockString, dbgeng/IDebugClient5::GetQuitLockString, debugger.idebugclient5_getquitlockstring
f1_keywords:
 - "dbgeng/IDebugClient5.GetQuitLockString"
 - "IDebugClient5.GetQuitLockString"
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
- IDebugClient5.GetQuitLockString
targetos: Windows
req.typenames: 
---

# IDebugClient5::GetQuitLockString


## -description


Gets a quit lock string.


## -parameters




### -param Buffer 
[out]
The buffer in which to write the string.


### -param BufferSize 
[in]
The size of the buffer.


### -param StringSize 
[out, optional]
A pointer to the string size.


## -returns



If this method succeeds, it returns **S_OK**. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



    A quit lock string provides control to lock the session against
    undesired quits.  

The quit lock string
    cannot be retrieved from a secure session.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
 

 

