---
UID: NF:dbgeng.IDebugSymbols4.GetNameByInlineContext
title: IDebugSymbols4::GetNameByInlineContext (dbgeng.h)
description: Gets a name by inline context.
old-location: debugger\idebugsymbols4_getnamebyinlinecontext.htm
tech.root: debugger
ms.assetid: C87E70ED-FCB0-47B6-B6A3-A8EBC8E84058
ms.date: 05/03/2018
keywords: ["IDebugSymbols4::GetNameByInlineContext"]
ms.keywords: GetNameByInlineContext, GetNameByInlineContext method [Windows Debugging], GetNameByInlineContext method [Windows Debugging],IDebugSymbols4 interface, IDebugSymbols4 interface [Windows Debugging],GetNameByInlineContext method, IDebugSymbols4.GetNameByInlineContext, IDebugSymbols4::GetNameByInlineContext, dbgeng/IDebugSymbols4::GetNameByInlineContext, debugger.idebugsymbols4_getnamebyinlinecontext
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
 - IDebugSymbols4::GetNameByInlineContext
 - dbgeng/IDebugSymbols4::GetNameByInlineContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbols4.GetNameByInlineContext
---

# IDebugSymbols4::GetNameByInlineContext


## -description

Gets a name by inline context.

## -parameters

### -param Offset 

[in]
An offset for the name.

### -param InlineContext 

[in]
The inline context.

### -param NameBuffer 

[out]
A pointer an output buffer.

### -param NameBufferSize 

[in]
The size of the name buffer.

### -param NameSize 

[out, optional]
A pointer to the length of the name.

### -param Displacement 

[out, optional]
A pointer to the displacement value of the name.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols4">IDebugSymbols4</a>