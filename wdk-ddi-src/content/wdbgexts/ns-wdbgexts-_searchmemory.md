---
UID: NS:wdbgexts._SEARCHMEMORY
title: _SEARCHMEMORY (wdbgexts.h)
description: Learn how the SearchMemory function searches the target's virtual memory for a specified pattern of bytes.
old-location: debugger\searchmemory.htm
tech.root: debugger
ms.date: 07/27/2023
keywords: ["SEARCHMEMORY structure"]
ms.keywords: "*PSEARCHMEMORY, SEARCHMEMORY, SearchMemory, SearchMemory function [Windows Debugging], WdbgExts_Ref_4eb909e5-edfd-487c-851c-812b15274c66.xml, _SEARCHMEMORY, debugger.searchmemory, wdbgexts/SearchMemory"
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
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
req.typenames: SEARCHMEMORY, *PSEARCHMEMORY
f1_keywords:
 - _SEARCHMEMORY
 - wdbgexts/_SEARCHMEMORY
 - PSEARCHMEMORY
 - wdbgexts/PSEARCHMEMORY
 - SEARCHMEMORY
 - wdbgexts/SEARCHMEMORY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdbgexts.h
api_name:
 - _SEARCHMEMORY
 - PSEARCHMEMORY
 - SEARCHMEMORY
---

# _SEARCHMEMORY structure

## -description

The <b>SearchMemory</b> function searches the target's virtual memory for a specified pattern of bytes.

## -struct-fields

### -field SearchAddress

Specifies the address in the target's virtual memory from which to start the search.

### -field SearchLength

Specifies the size, in bytes, of the memory to search.  For a successful match, the pattern must be found before <i>SearchLength</i> bytes have been examined.

### -field FoundAddress

Receives the location of the pattern, found in the target's virtual memory.  If the pattern was not found, the value in <i>FoundAddress</i> is unchanged by this function.

### -field PatternLength

Specifies the size, in bytes, of the pattern to search for.

### -field Pattern

Specifies the pattern to search for.
