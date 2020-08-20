---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryByToken
title: IDebugSymbols3::GetSymbolEntryByToken (dbgeng.h)
description: Looks up a symbol by using a managed metadata token.
old-location: debugger\idebugsymbols3_getsymbolentrybytoken.htm
tech.root: debugger
ms.assetid: C5BAED6C-223F-4D1B-A9A4-323C93DD5AD9
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetSymbolEntryByToken"]
ms.keywords: GetSymbolEntryByToken, GetSymbolEntryByToken method [Windows Debugging], GetSymbolEntryByToken method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSymbolEntryByToken method, IDebugSymbols3.GetSymbolEntryByToken, IDebugSymbols3::GetSymbolEntryByToken, dbgeng/IDebugSymbols3::GetSymbolEntryByToken, debugger.idebugsymbols3_getsymbolentrybytoken
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetSymbolEntryByToken"
 - "IDebugSymbols3.GetSymbolEntryByToken"
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
- IDebugSymbols3.GetSymbolEntryByToken
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSymbolEntryByToken


## -description


Looks up a symbol by using a managed metadata token.


## -parameters




### -param ModuleBase 
[in]
The base of the module.


### -param Token 
[in]
The token to use to look up the symbol.


### -param Id 
[out]
A pointer to the module as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_module_and_id">DEBUG_MODULE_AND_ID</a> structure. 


## -returns



If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_module_and_id">DEBUG_MODULE_AND_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

