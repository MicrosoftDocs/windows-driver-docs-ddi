---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryBySymbolEntry
title: IDebugSymbols3::GetSymbolEntryBySymbolEntry method
author: windows-driver-content
description: Allows navigation within the symbol entry hierarchy.
old-location: debugger\idebugsymbols3_getsymbolentrybysymbolentry.htm
old-project: Debugger
ms.assetid: 39AD3C10-C6E8-463F-BDDE-5941CB4B2830
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GetSymbolEntryBySymbolEntry, dbgeng/IDebugSymbols3::GetSymbolEntryBySymbolEntry, IDebugSymbols3::GetSymbolEntryBySymbolEntry, GetSymbolEntryBySymbolEntry method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging], GetSymbolEntryBySymbolEntry method, IDebugSymbols3, debugger.idebugsymbols3_getsymbolentrybysymbolentry, GetSymbolEntryBySymbolEntry method [Windows Debugging]
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
-	IDebugSymbols3.GetSymbolEntryBySymbolEntry
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetSymbolEntryBySymbolEntry method


## -description


Allows navigation within the
    symbol entry hierarchy.


## -syntax


````
HRESULT GetSymbolEntryBySymbolEntry(
  [in]  PDEBUG_MODULE_AND_ID FromId,
  [in]  ULONG                Flags,
  [out] PDEBUG_MODULE_AND_ID ToId
);
````


## -parameters




### -param FromId [in]

A pointer to a <a href="..\dbgeng\ns-dbgeng-_debug_module_and_id.md">DEBUG_MODULE_AND_ID</a> structure as the input ID.


### -param Flags [in]

A bit-set that contains options that affect the behavior of this method. 


### -param ToId [out]

A pointer to a <a href="..\dbgeng\ns-dbgeng-_debug_module_and_id.md">DEBUG_MODULE_AND_ID</a> structure as the output ID.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\dbgeng\ns-dbgeng-_debug_module_and_id.md">DEBUG_MODULE_AND_ID</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugSymbols3::GetSymbolEntryBySymbolEntry method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

