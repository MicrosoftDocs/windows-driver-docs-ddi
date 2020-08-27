---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryOffsetRegions
title: IDebugSymbols3::GetSymbolEntryOffsetRegions (dbgeng.h)
description: Returns all the memory regions known to be associated with a symbol.
old-location: debugger\idebugsymbols3_getsymbolentryoffsetregions.htm
tech.root: debugger
ms.assetid: 986774F6-5256-4703-990A-EAB4AB09AF55
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetSymbolEntryOffsetRegions"]
ms.keywords: GetSymbolEntryOffsetRegions, GetSymbolEntryOffsetRegions method [Windows Debugging], GetSymbolEntryOffsetRegions method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSymbolEntryOffsetRegions method, IDebugSymbols3.GetSymbolEntryOffsetRegions, IDebugSymbols3::GetSymbolEntryOffsetRegions, dbgeng/IDebugSymbols3::GetSymbolEntryOffsetRegions, debugger.idebugsymbols3_getsymbolentryoffsetregions
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetSymbolEntryOffsetRegions"
 - "IDebugSymbols3.GetSymbolEntryOffsetRegions"
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
- Dbgeng.h
api_name:
- IDebugSymbols3.GetSymbolEntryOffsetRegions
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSymbolEntryOffsetRegions


## -description


Returns all the memory regions known to be associated
    with a symbol.  


## -parameters




### -param Id 
[in]
The ID of a module as a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_module_and_id">DEBUG_MODULE_AND_ID</a> structure. 


### -param Flags 
[in]
A bit-set that contains options that affect the behavior of this method. 


### -param Regions 
[out]
The memory regions associated with the symbol. 


### -param RegionsCount 
[in]
The number of regions associated with the symbol.


### -param RegionsAvail 
[out, optional]
A pointer to the number of regions available to the symbol. 


## -returns



If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

This function returns all known memory regions that associated
    with a specified symbol.  Simple symbols have a single region that starts from their base. More complicated regions, such as functions that have multiple code areas, can have an arbitrarily
    large number of regions.

The quality of information returned is highly
    dependent on the symbolic information available.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_module_and_id">DEBUG_MODULE_AND_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsourceentryoffsetregions">IDebugSymbols3::GetSourceEntryOffsetRegions</a>
 

 

