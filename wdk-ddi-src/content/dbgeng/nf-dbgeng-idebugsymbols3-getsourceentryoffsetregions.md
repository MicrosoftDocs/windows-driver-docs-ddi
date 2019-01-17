---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntryOffsetRegions
title: IDebugSymbols3::GetSourceEntryOffsetRegions
description: Returns all memory regions known to be associated with a source entry.
old-location: debugger\idebugsymbols3_getsourceentryoffsetregions.htm
tech.root: debugger
ms.assetid: A39FF088-1AA3-4E2F-8EF6-AD7F79FBBC92
ms.date: 05/03/2018
ms.keywords: GetSourceEntryOffsetRegions, GetSourceEntryOffsetRegions method [Windows Debugging], GetSourceEntryOffsetRegions method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSourceEntryOffsetRegions method, IDebugSymbols3.GetSourceEntryOffsetRegions, IDebugSymbols3::GetSourceEntryOffsetRegions, dbgeng/IDebugSymbols3::GetSourceEntryOffsetRegions, debugger.idebugsymbols3_getsourceentryoffsetregions
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Dbgeng.h
api_name:
-	IDebugSymbols3.GetSourceEntryOffsetRegions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSourceEntryOffsetRegions


## -description


 Returns all memory regions known to be associated
    with a source entry.  


## -parameters




### -param Entry [in]

An entry as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541680">DEBUG_SYMBOL_SOURCE_ENTRY</a> structure. 


### -param Flags [in]

A bit-set that contains options that affect the behavior of this method. 


### -param Regions [out]

The memory regions associated with the source entry. 


### -param RegionsCount [in]

The number of regions associated with the entry.


### -param RegionsAvail [out, optional]

A pointer to the number of regions available to the entry.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

This function returns all known memory regions that associated
    with a specified source entry.  Simple symbols have a single region that starts from their base. More complicated regions, such as functions that have multiple code areas, can have an arbitrarily
    large number of regions.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541680">DEBUG_SYMBOL_SOURCE_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/986774F6-5256-4703-990A-EAB4AB09AF55">IDebugSymbols3::GetSymbolEntryOffsetRegions</a>
 

 

