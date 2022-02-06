---
UID: NF:dbgeng.IDebugSymbols4.GetNameByInlineContextWide
title: IDebugSymbols4::GetNameByInlineContextWide (dbgeng.h)
description: The GetNameByInlineContextWide method gets a name by inline context. This method belongs to the IDebugSymbols4 interface.
old-location: debugger\idebugsymbols4_getnamebyinlinecontextwide.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugSymbols4::GetNameByInlineContextWide"]
ms.keywords: GetNameByInlineContextWide, GetNameByInlineContextWide method [Windows Debugging], GetNameByInlineContextWide method [Windows Debugging],IDebugSymbols4 interface, IDebugSymbols4 interface [Windows Debugging],GetNameByInlineContextWide method, IDebugSymbols4.GetNameByInlineContextWide, IDebugSymbols4::GetNameByInlineContextWide, dbgeng/IDebugSymbols4::GetNameByInlineContextWide, debugger.idebugsymbols4_getnamebyinlinecontextwide
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
 - IDebugSymbols4::GetNameByInlineContextWide
 - dbgeng/IDebugSymbols4::GetNameByInlineContextWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbols4::GetNameByInlineContextWide
---

# IDebugSymbols4::GetNameByInlineContextWide


## -description

Gets a name by inline context.

## -parameters

### -param Offset [in]


An offset for the inline context.

### -param InlineContext [in]


The inline context.

### -param NameBuffer [out]


A pointer an output buffer for a Unicode character string.

### -param NameBufferSize [in]


The size of the name buffer. This size includes the space for the '\0' terminating character.

### -param NameSize [out, optional]


A pointer to the length of the name. This size includes the space for the '\0' terminating character.

### -param Displacement [out, optional]


A pointer to the displacement value of the name.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols4">IDebugSymbols4</a>

