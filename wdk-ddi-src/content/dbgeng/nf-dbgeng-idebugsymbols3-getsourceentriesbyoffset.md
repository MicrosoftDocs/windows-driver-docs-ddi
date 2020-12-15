---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntriesByOffset
title: IDebugSymbols3::GetSourceEntriesByOffset (dbgeng.h)
description: Queries symbol information and returns locations in the target's memory by using an offset.
old-location: debugger\idebugsymbols3_getsourceentriesbyoffset.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetSourceEntriesByOffset"]
ms.keywords: GetSourceEntriesByOffset, GetSourceEntriesByOffset method [Windows Debugging], GetSourceEntriesByOffset method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSourceEntriesByOffset method, IDebugSymbols3.GetSourceEntriesByOffset, IDebugSymbols3::GetSourceEntriesByOffset, dbgeng/IDebugSymbols3::GetSourceEntriesByOffset, debugger.idebugsymbols3_getsourceentriesbyoffset
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
 - IDebugSymbols3::GetSourceEntriesByOffset
 - dbgeng/IDebugSymbols3::GetSourceEntriesByOffset
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbols3.GetSourceEntriesByOffset
---

# IDebugSymbols3::GetSourceEntriesByOffset


## -description

Queries symbol information and returns locations in the target's memory by using an offset.

## -parameters

### -param Offset 

[in]
The  offset of the entry.

### -param Flags 

[in]
A bit-set that contains options that affect the behavior of this method.

### -param Entries 

[out]
A pointer to a returned entry as a <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_source_entry">DEBUG_SYMBOL_SOURCE_ENTRY</a> structure.

### -param EntriesCount 

[in]
The number of entries.

### -param EntriesAvail 

[out, optional]
A pointer to the number of entries available.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

    This method can return multiple results for a source lookup. This allows for all possible results to be returned.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_source_entry">DEBUG_SYMBOL_SOURCE_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
