---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryOffsetRegions
title: IDebugSymbols3::GetSymbolEntryOffsetRegions method
author: windows-driver-content
description: Returns all the memory regions known to be associated with a symbol.
old-location: debugger\idebugsymbols3_getsymbolentryoffsetregions.htm
old-project: debugger
ms.assetid: 986774F6-5256-4703-990A-EAB4AB09AF55
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetSymbolEntryOffsetRegions, dbgeng/IDebugSymbols3::GetSymbolEntryOffsetRegions, IDebugSymbols3::GetSymbolEntryOffsetRegions, IDebugSymbols3 interface [Windows Debugging], GetSymbolEntryOffsetRegions method, GetSymbolEntryOffsetRegions method [Windows Debugging], IDebugSymbols3 interface, debugger.idebugsymbols3_getsymbolentryoffsetregions, GetSymbolEntryOffsetRegions method [Windows Debugging], IDebugSymbols3
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Dbgeng.h
apiname:
-	IDebugSymbols3.GetSymbolEntryOffsetRegions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetSymbolEntryOffsetRegions method


## -description


Returns all the memory regions known to be associated
    with a symbol.  


## -syntax


````
HRESULT GetSymbolEntryOffsetRegions(
  [in]            PDEBUG_MODULE_AND_ID                            Id,
  [in]            ULONG                                           Flags,
  [out]           _writes_opt_(RegionsCount) PDEBUG_OFFSET_REGION Regions,
  [in]            ULONG                                           RegionsCount,
  [out, optional] PULONG                                          RegionsAvail
);
````


## -parameters




### -param Id [in]

The ID of a module as a pointer to a <a href="..\dbgeng\ns-dbgeng-_debug_module_and_id.md">DEBUG_MODULE_AND_ID</a> structure. 


### -param Flags [in]

A bit-set that contains options that affect the behavior of this method. 


### -param Regions [out]

The memory regions associated with the symbol. 


### -param RegionsCount [in]

The number of regions associated with the symbol.


### -param RegionsAvail [out, optional]

A pointer to the number of regions available to the symbol. 


## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

This function returns all known memory regions that associated
    with a specified symbol.  Simple symbols have a single region that starts from their base. More complicated regions, such as functions that have multiple code areas, can have an arbitrarily
    large number of regions.

The quality of information returned is highly
    dependent on the symbolic information available.



## -see-also

<a href="..\dbgeng\ns-dbgeng-_debug_module_and_id.md">DEBUG_MODULE_AND_ID</a>

<a href="https://msdn.microsoft.com/A39FF088-1AA3-4E2F-8EF6-AD7F79FBBC92">IDebugSymbols3::GetSourceEntryOffsetRegions</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSymbolEntryOffsetRegions method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

