---
UID: NF:dbgeng.IDebugSymbols4.GetLineByInlineContextWide
title: IDebugSymbols4::GetLineByInlineContextWide (dbgeng.h)
description: Gets a line by inline context.
old-location: debugger\idebugsymbols4_getlinebyinlinecontextwide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols4::GetLineByInlineContextWide"]
ms.keywords: GetLineByInlineContextWide, GetLineByInlineContextWide method [Windows Debugging], GetLineByInlineContextWide method [Windows Debugging],IDebugSymbols4 interface, IDebugSymbols4 interface [Windows Debugging],GetLineByInlineContextWide method, IDebugSymbols4.GetLineByInlineContextWide, IDebugSymbols4::GetLineByInlineContextWide, dbgeng/IDebugSymbols4::GetLineByInlineContextWide, debugger.idebugsymbols4_getlinebyinlinecontextwide
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
 - IDebugSymbols4::GetLineByInlineContextWide
 - dbgeng/IDebugSymbols4::GetLineByInlineContextWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbols4::GetLineByInlineContextWide
---

# IDebugSymbols4::GetLineByInlineContextWide


## -description

Gets a line by inline context.

## -parameters

### -param Offset 

[in]
An offset for the line.

### -param InlineContext 

[in]
The inline context.

### -param Line 

[out, optional]
A pointer to the returned line.

### -param FileBuffer 

[out]
A pointer to a buffer for a Unicode character string.

### -param FileBufferSize 

[in]
The size of the file buffer.

### -param FileSize 

[out, optional]
A pointer to the length of the file.

### -param Displacement 

[out, optional]
A pointer to the displacement value of the file.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols4">IDebugSymbols4</a>

