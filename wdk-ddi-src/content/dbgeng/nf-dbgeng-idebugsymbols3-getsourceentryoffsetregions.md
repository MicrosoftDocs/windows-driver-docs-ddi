---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntryOffsetRegions
title: IDebugSymbols3::GetSourceEntryOffsetRegions (dbgeng.h)
description: Returns all memory regions known to be associated with a source entry.
old-location: debugger\idebugsymbols3_getsourceentryoffsetregions.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetSourceEntryOffsetRegions"]
ms.keywords: GetSourceEntryOffsetRegions, GetSourceEntryOffsetRegions method [Windows Debugging], GetSourceEntryOffsetRegions method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSourceEntryOffsetRegions method, IDebugSymbols3.GetSourceEntryOffsetRegions, IDebugSymbols3::GetSourceEntryOffsetRegions, dbgeng/IDebugSymbols3::GetSourceEntryOffsetRegions, debugger.idebugsymbols3_getsourceentryoffsetregions
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
 - IDebugSymbols3::GetSourceEntryOffsetRegions
 - dbgeng/IDebugSymbols3::GetSourceEntryOffsetRegions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbols3::GetSourceEntryOffsetRegions
---

# IDebugSymbols3::GetSourceEntryOffsetRegions


## -description

 Returns all memory regions known to be associated
    with a source entry.

## -parameters

### -param Entry [in]


An entry as a <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_source_entry">DEBUG_SYMBOL_SOURCE_ENTRY</a> structure.

### -param Flags [in]


A bit-set that contains options that affect the behavior of this method.

### -param Regions [out]


The memory regions associated with the source entry.

### -param RegionsCount [in]


The number of regions associated with the entry.

### -param RegionsAvail [out, optional]


A pointer to the number of regions available to the entry.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

This function returns all known memory regions that associated
    with a specified source entry.  Simple symbols have a single region that starts from their base. More complicated regions, such as functions that have multiple code areas, can have an arbitrarily
    large number of regions.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_source_entry">DEBUG_SYMBOL_SOURCE_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolentryoffsetregions">IDebugSymbols3::GetSymbolEntryOffsetRegions</a>

