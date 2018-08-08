---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryBySymbolEntry
title: IDebugSymbols3::GetSymbolEntryBySymbolEntry
author: windows-driver-content
description: Allows navigation within the symbol entry hierarchy.
old-location: debugger\idebugsymbols3_getsymbolentrybysymbolentry.htm
tech.root: debugger
ms.assetid: 39AD3C10-C6E8-463F-BDDE-5941CB4B2830
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: GetSymbolEntryBySymbolEntry, GetSymbolEntryBySymbolEntry method [Windows Debugging], GetSymbolEntryBySymbolEntry method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSymbolEntryBySymbolEntry method, IDebugSymbols3.GetSymbolEntryBySymbolEntry, IDebugSymbols3::GetSymbolEntryBySymbolEntry, dbgeng/IDebugSymbols3::GetSymbolEntryBySymbolEntry, debugger.idebugsymbols3_getsymbolentrybysymbolentry
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
-	IDebugSymbols3.GetSymbolEntryBySymbolEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSymbolEntryBySymbolEntry


## -description


Allows navigation within the
    symbol entry hierarchy.


## -parameters




### -param FromId [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541511">DEBUG_MODULE_AND_ID</a> structure as the input ID.


### -param Flags [in]

A bit-set that contains options that affect the behavior of this method. 


### -param ToId [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541511">DEBUG_MODULE_AND_ID</a> structure as the output ID.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541511">DEBUG_MODULE_AND_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

