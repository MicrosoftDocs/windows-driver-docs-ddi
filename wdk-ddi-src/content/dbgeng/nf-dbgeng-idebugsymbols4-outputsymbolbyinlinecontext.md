---
UID: NF:dbgeng.IDebugSymbols4.OutputSymbolByInlineContext
title: IDebugSymbols4::OutputSymbolByInlineContext (dbgeng.h)
description: Specifies an output symbol by using an inline context.
old-location: debugger\idebugsymbols4_outputsymbolbyinlinecontext.htm
tech.root: debugger
ms.assetid: 55BA214C-7161-4B2C-8107-11EE22D63CD6
ms.date: 05/03/2018
keywords: ["IDebugSymbols4::OutputSymbolByInlineContext"]
ms.keywords: IDebugSymbols4 interface [Windows Debugging],OutputSymbolByInlineContext method, IDebugSymbols4.OutputSymbolByInlineContext, IDebugSymbols4::OutputSymbolByInlineContext, OutputSymbolByInlineContext, OutputSymbolByInlineContext method [Windows Debugging], OutputSymbolByInlineContext method [Windows Debugging],IDebugSymbols4 interface, dbgeng/IDebugSymbols4::OutputSymbolByInlineContext, debugger.idebugsymbols4_outputsymbolbyinlinecontext
f1_keywords:
 - "dbgeng/IDebugSymbols4.OutputSymbolByInlineContext"
 - "IDebugSymbols4.OutputSymbolByInlineContext"
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
- IDebugSymbols4.OutputSymbolByInlineContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols4::OutputSymbolByInlineContext


## -description


Specifies an output symbol by using an inline context.


## -parameters




### -param OutputControl [in]

An output control.


### -param Flags [in]

A bit-set that contains options that affect the behavior of this method. 


### -param Offset [in]

An offset.


### -param InlineContext [in]

An inline context.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols4">IDebugSymbols4</a>
 

 

