---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntryStringWide
title: IDebugSymbols3::GetSourceEntryStringWide (dbgeng.h)
description: Queries symbol information and returns locations in the target's memory.
old-location: debugger\idebugsymbols3_getsourceentrystringwide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetSourceEntryStringWide"]
ms.keywords: GetSourceEntryStringWide, GetSourceEntryStringWide method [Windows Debugging], GetSourceEntryStringWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSourceEntryStringWide method, IDebugSymbols3.GetSourceEntryStringWide, IDebugSymbols3::GetSourceEntryStringWide, dbgeng/IDebugSymbols3::GetSourceEntryStringWide, debugger.idebugsymbols3_getsourceentrystringwide
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
 - IDebugSymbols3::GetSourceEntryStringWide
 - dbgeng/IDebugSymbols3::GetSourceEntryStringWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbols3.GetSourceEntryStringWide
---

# IDebugSymbols3::GetSourceEntryStringWide


## -description

Queries symbol information and returns locations in the target's memory.

## -parameters

### -param Entry 

[in]
An entry as a <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_source_entry">DEBUG_SYMBOL_SOURCE_ENTRY</a> structure.

### -param Which 

[in]
A value that determines which types to return.

### -param Buffer 

[out]
 A pointer to a Unicode character string buffer for the results.

### -param BufferSize 

[in]
The size of the buffer.

### -param StringSize 

[out, optional]
Pointer to the size of the string.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

This method can return multiple results for a source lookup. This allows for all possible results to be returned.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
