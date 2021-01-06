---
UID: NF:dbgeng.IDebugSymbols5.GetCurrentScopeFrameIndexEx
title: IDebugSymbols5::GetCurrentScopeFrameIndexEx (dbgeng.h)
description: Gets the index of the current frame.
old-location: debugger\idebugsymbols5_getcurrentscopeframeindexex.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols5::GetCurrentScopeFrameIndexEx"]
ms.keywords: GetCurrentScopeFrameIndexEx, GetCurrentScopeFrameIndexEx method [Windows Debugging], GetCurrentScopeFrameIndexEx method [Windows Debugging],IDebugSymbols5 interface, IDebugSymbols5 interface [Windows Debugging],GetCurrentScopeFrameIndexEx method, IDebugSymbols5.GetCurrentScopeFrameIndexEx, IDebugSymbols5::GetCurrentScopeFrameIndexEx, dbgeng/IDebugSymbols5::GetCurrentScopeFrameIndexEx, debugger.idebugsymbols5_getcurrentscopeframeindexex
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
 - IDebugSymbols5::GetCurrentScopeFrameIndexEx
 - dbgeng/IDebugSymbols5::GetCurrentScopeFrameIndexEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbols5.GetCurrentScopeFrameIndexEx
---

# IDebugSymbols5::GetCurrentScopeFrameIndexEx


## -description

Gets the index of the current frame.

## -parameters

### -param Flags 

[in]
A bit-set that contains options that affect the behavior of this method.

### -param Index 

[out]
A pointer to an index that this function gets.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols5">IDebugSymbols5</a>
