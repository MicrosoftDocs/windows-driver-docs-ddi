---
UID: NF:dbgeng.IDebugClient5.PushOutputLinePrefix
title: IDebugClient5::PushOutputLinePrefix (dbgeng.h)
description: Saves an output line prefix.
old-location: debugger\idebugclient5_pushoutputlineprefix.htm
tech.root: debugger
ms.assetid: 20446E2D-94D3-43D6-ABBF-2FA15F089659
ms.date: 05/03/2018
ms.keywords: IDebugClient5 interface [Windows Debugging],PushOutputLinePrefix method, IDebugClient5.PushOutputLinePrefix, IDebugClient5::PushOutputLinePrefix, PushOutputLinePrefix, PushOutputLinePrefix method [Windows Debugging], PushOutputLinePrefix method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::PushOutputLinePrefix, debugger.idebugclient5_pushoutputlineprefix
f1_keywords:
 - "dbgeng/IDebugClient5.PushOutputLinePrefix"
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
- IDebugClient5.PushOutputLinePrefix
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::PushOutputLinePrefix


## -description


    Saves an output line prefix.


## -parameters




### -param NewPrefix [in, optional]

A pointer to the new output line prefix.


### -param Handle [out]

The handle of the previous output line prefix.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
 

 

