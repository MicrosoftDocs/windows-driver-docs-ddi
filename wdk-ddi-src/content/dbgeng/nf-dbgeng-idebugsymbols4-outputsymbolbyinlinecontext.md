---
UID: NF:dbgeng.IDebugSymbols4.OutputSymbolByInlineContext
title: IDebugSymbols4::OutputSymbolByInlineContext method
author: windows-driver-content
description: Specifies an output symbol by using an inline context.
old-location: debugger\idebugsymbols4_outputsymbolbyinlinecontext.htm
old-project: debugger
ms.assetid: 55BA214C-7161-4B2C-8107-11EE22D63CD6
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugSymbols4, IDebugSymbols4 interface [Windows Debugging], OutputSymbolByInlineContext method, IDebugSymbols4::OutputSymbolByInlineContext, OutputSymbolByInlineContext method [Windows Debugging], OutputSymbolByInlineContext method [Windows Debugging], IDebugSymbols4 interface, OutputSymbolByInlineContext,IDebugSymbols4.OutputSymbolByInlineContext, dbgeng/IDebugSymbols4::OutputSymbolByInlineContext, debugger.idebugsymbols4_outputsymbolbyinlinecontext
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
-	IDebugSymbols4.OutputSymbolByInlineContext
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols4::OutputSymbolByInlineContext method


## -description


Specifies an output symbol by using an inline context.


## -syntax


````
HRESULT OutputSymbolByInlineContext(
  [in] ULONG   OutputControl,
  [in] ULONG   Flags,
  [in] ULONG64 Offset,
  [in] ULONG   InlineContext
);
````


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

<a href="..\dbgeng\nn-dbgeng-idebugsymbols4.md">IDebugSymbols4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols4::OutputSymbolByInlineContext method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

