---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntryOffsetRegions
title: IDebugSymbols3::GetSourceEntryOffsetRegions method
author: windows-driver-content
description: Returns all memory regions known to be associated with a source entry.
old-location: debugger\idebugsymbols3_getsourceentryoffsetregions.htm
old-project: debugger
ms.assetid: A39FF088-1AA3-4E2F-8EF6-AD7F79FBBC92
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetSourceEntryOffsetRegions method [Windows Debugging], GetSourceEntryOffsetRegions method [Windows Debugging], IDebugSymbols3 interface, GetSourceEntryOffsetRegions,IDebugSymbols3.GetSourceEntryOffsetRegions, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSourceEntryOffsetRegions method, IDebugSymbols3::GetSourceEntryOffsetRegions, dbgeng/IDebugSymbols3::GetSourceEntryOffsetRegions, debugger.idebugsymbols3_getsourceentryoffsetregions
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: dbgeng.h
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
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetSourceEntryOffsetRegions method


## -description


 Returns all memory regions known to be associated
    with a source entry.  


## -syntax


````
HRESULT GetSourceEntryOffsetRegions(
  [in]            PDEBUG_SYMBOL_SOURCE_ENTRY                      Entry,
  [in]            ULONG                                           Flags,
  [out]           _writes_opt_(RegionsCount) PDEBUG_OFFSET_REGION Regions,
  [in]            ULONG                                           RegionsCount,
  [out, optional] PULONG                                          RegionsAvail
);
````


## -parameters




### -param Entry [in]

An entry as a <a href="..\dbgeng\ns-dbgeng-_debug_symbol_source_entry.md">DEBUG_SYMBOL_SOURCE_ENTRY</a> structure. 


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

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="..\dbgeng\ns-dbgeng-_debug_symbol_source_entry.md">DEBUG_SYMBOL_SOURCE_ENTRY</a>



<a href="https://msdn.microsoft.com/986774F6-5256-4703-990A-EAB4AB09AF55">IDebugSymbols3::GetSymbolEntryOffsetRegions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSourceEntryOffsetRegions method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

