---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntryBySourceEntry
title: IDebugSymbols3::GetSourceEntryBySourceEntry (dbgeng.h)
description: Allows navigation within the source entries.
old-location: debugger\idebugsymbols3_getsourceentrybysourceentry.htm
tech.root: debugger
ms.assetid: 4ED5D2DC-8D31-458A-80F2-F681DC375769
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetSourceEntryBySourceEntry"]
ms.keywords: GetSourceEntryBySourceEntry, GetSourceEntryBySourceEntry method [Windows Debugging], GetSourceEntryBySourceEntry method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSourceEntryBySourceEntry method, IDebugSymbols3.GetSourceEntryBySourceEntry, IDebugSymbols3::GetSourceEntryBySourceEntry, dbgeng/IDebugSymbols3::GetSourceEntryBySourceEntry, debugger.idebugsymbols3_getsourceentrybysourceentry
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
 - IDebugSymbols3::GetSourceEntryBySourceEntry
 - dbgeng/IDebugSymbols3::GetSourceEntryBySourceEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbols3.GetSourceEntryBySourceEntry
---

# IDebugSymbols3::GetSourceEntryBySourceEntry


## -description

Allows navigation within the
    source entries.

## -parameters

### -param FromEntry 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_source_entry">DEBUG_SYMBOL_SOURCE_ENTRY</a> as the input entry.

### -param Flags 

[in]
A bit-set that contains options that affect the behavior of this method.

### -param ToEntry 

[out]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_source_entry">DEBUG_SYMBOL_SOURCE_ENTRY</a> as the output entry.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_source_entry">DEBUG_SYMBOL_SOURCE_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>

