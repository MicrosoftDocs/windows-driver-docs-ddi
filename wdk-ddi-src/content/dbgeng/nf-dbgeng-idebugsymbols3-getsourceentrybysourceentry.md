---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntryBySourceEntry
title: IDebugSymbols3::GetSourceEntryBySourceEntry method
author: windows-driver-content
description: Allows navigation within the source entries.
old-location: debugger\idebugsymbols3_getsourceentrybysourceentry.htm
old-project: debugger
ms.assetid: 4ED5D2DC-8D31-458A-80F2-F681DC375769
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetSourceEntryBySourceEntry method [Windows Debugging], GetSourceEntryBySourceEntry method [Windows Debugging], IDebugSymbols3 interface, GetSourceEntryBySourceEntry,IDebugSymbols3.GetSourceEntryBySourceEntry, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSourceEntryBySourceEntry method, IDebugSymbols3::GetSourceEntryBySourceEntry, dbgeng/IDebugSymbols3::GetSourceEntryBySourceEntry, debugger.idebugsymbols3_getsourceentrybysourceentry
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
-	IDebugSymbols3.GetSourceEntryBySourceEntry
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetSourceEntryBySourceEntry method


## -description


Allows navigation within the
    source entries.


## -syntax


````
HRESULT GetSourceEntryBySourceEntry(
  [in]  PDEBUG_SYMBOL_SOURCE_ENTRY FromEntry,
  [in]  ULONG                      Flags,
  [out] PDEBUG_SYMBOL_SOURCE_ENTRY ToEntry
);
````


## -parameters




### -param FromEntry [in]

A pointer to a <a href="..\dbgeng\ns-dbgeng-_debug_symbol_source_entry.md">DEBUG_SYMBOL_SOURCE_ENTRY</a> as the input entry.


### -param Flags [in]

A bit-set that contains options that affect the behavior of this method. 


### -param ToEntry [out]

A pointer to a <a href="..\dbgeng\ns-dbgeng-_debug_symbol_source_entry.md">DEBUG_SYMBOL_SOURCE_ENTRY</a> as the output entry.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\dbgeng\ns-dbgeng-_debug_symbol_source_entry.md">DEBUG_SYMBOL_SOURCE_ENTRY</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 


