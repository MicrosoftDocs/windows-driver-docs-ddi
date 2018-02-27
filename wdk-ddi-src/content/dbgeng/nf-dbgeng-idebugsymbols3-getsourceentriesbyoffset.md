---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntriesByOffset
title: IDebugSymbols3::GetSourceEntriesByOffset method
author: windows-driver-content
description: Queries symbol information and returns locations in the target's memory by using an offset.
old-location: debugger\idebugsymbols3_getsourceentriesbyoffset.htm
old-project: debugger
ms.assetid: CA84F931-5EB9-49D0-9EA5-288900A8DE46
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetSourceEntriesByOffset method [Windows Debugging], GetSourceEntriesByOffset method [Windows Debugging], IDebugSymbols3 interface, GetSourceEntriesByOffset,IDebugSymbols3.GetSourceEntriesByOffset, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSourceEntriesByOffset method, IDebugSymbols3::GetSourceEntriesByOffset, dbgeng/IDebugSymbols3::GetSourceEntriesByOffset, debugger.idebugsymbols3_getsourceentriesbyoffset
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
-	IDebugSymbols3.GetSourceEntriesByOffset
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetSourceEntriesByOffset method


## -description


Queries symbol information and returns locations in the target's memory by using an offset.


## -syntax


````
HRESULT GetSourceEntriesByOffset(
  [in]            ULONG64                                               Offset,
  [in]            ULONG                                                 Flags,
  [out]           _writes_opt_(EntriesCount) PDEBUG_SYMBOL_SOURCE_ENTRY Entries,
  [in]            ULONG                                                 EntriesCount,
  [out, optional] PULONG                                                EntriesAvail
);
````


## -parameters




### -param Offset [in]

The  offset of the entry.


### -param Flags [in]

A bit-set that contains options that affect the behavior of this method.


### -param Entries [out]

A pointer to a returned entry as a <a href="..\dbgeng\ns-dbgeng-_debug_symbol_source_entry.md">DEBUG_SYMBOL_SOURCE_ENTRY</a> structure.


### -param EntriesCount [in]

The number of entries.


### -param EntriesAvail [out, optional]

A pointer to the number of entries available. 


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



    This method can return multiple results for a source lookup. This allows for all possible results to be returned.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="..\dbgeng\ns-dbgeng-_debug_symbol_source_entry.md">DEBUG_SYMBOL_SOURCE_ENTRY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSourceEntriesByOffset method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

