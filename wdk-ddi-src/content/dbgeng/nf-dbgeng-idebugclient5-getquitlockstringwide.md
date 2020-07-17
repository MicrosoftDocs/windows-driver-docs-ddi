---
UID: NF:dbgeng.IDebugClient5.GetQuitLockStringWide
title: IDebugClient5::GetQuitLockStringWide (dbgeng.h)
description: Gets a Unicode character quit lock string.
old-location: debugger\idebugclient5_getquitlockstringwide.htm
tech.root: debugger
ms.assetid: 0C69F19C-D048-47EB-9286-6F8C6E3398CC
ms.date: 05/03/2018
keywords: ["IDebugClient5::GetQuitLockStringWide"]
ms.keywords: GetQuitLockStringWide, GetQuitLockStringWide method [Windows Debugging], GetQuitLockStringWide method [Windows Debugging],IDebugClient5 interface, IDebugClient5 interface [Windows Debugging],GetQuitLockStringWide method, IDebugClient5.GetQuitLockStringWide, IDebugClient5::GetQuitLockStringWide, dbgeng/IDebugClient5::GetQuitLockStringWide, debugger.idebugclient5_getquitlockstringwide
f1_keywords:
 - "dbgeng/IDebugClient5.GetQuitLockStringWide"
 - "IDebugClient5.GetQuitLockStringWide"
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
- IDebugClient5.GetQuitLockStringWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::GetQuitLockStringWide


## -description


Gets a Unicode character quit lock string.


## -parameters




### -param Buffer [out]

The buffer in which to write the Unicode character string.


### -param BufferSize [in]

The size of the buffer.


### -param StringSize [out, optional]

A pointer to the string size.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



    A quit lock string provides control to lock the session against
    undesired quits.  

The quit lock string
    cannot be retrieved from a secure session.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
 

 

