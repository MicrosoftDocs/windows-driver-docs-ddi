---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntryStringWide
title: IDebugSymbols3::GetSourceEntryStringWide method
author: windows-driver-content
description: Queries symbol information and returns locations in the target's memory.
old-location: debugger\idebugsymbols3_getsourceentrystringwide.htm
old-project: debugger
ms.assetid: CDB72C6A-43E5-463B-97E5-44D22214C071
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::GetSourceEntryStringWide, GetSourceEntryStringWide
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
req.alt-api: IDebugSymbols3.GetSourceEntryStringWide
req.alt-loc: Dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugSymbols3::GetSourceEntryStringWide method



## -description
Queries symbol information and returns locations in the target's memory.



## -syntax

````
HRESULT GetSourceEntryStringWide(
  [in]            PDEBUG_SYMBOL_SOURCE_ENTRY     Entry,
  [in]            ULONG                          Which,
  [out]           _writes_opt_(BufferSize) PWSTR Buffer,
  [in]            ULONG                          BufferSize,
  [out, optional] PULONG                         StringSize
);
````


## -parameters

### -param Entry [in]

An entry as a <a href="..\dbgeng\ns-dbgeng-_debug_symbol_source_entry.md">DEBUG_SYMBOL_SOURCE_ENTRY</a> structure. 


### -param Which [in]

A value that determines which types to return.


### -param Buffer [out]

 A pointer to a Unicode character string buffer for the results.


### -param BufferSize [in]

The size of the buffer.


### -param StringSize [out, optional]

Pointer to the size of the string. 


## -returns
If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

    This method can return multiple results for a source lookup. This allows for all possible results to be returned.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSourceEntryStringWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

