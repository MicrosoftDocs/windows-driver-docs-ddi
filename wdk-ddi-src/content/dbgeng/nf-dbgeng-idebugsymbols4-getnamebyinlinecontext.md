---
UID: NF:dbgeng.IDebugSymbols4.GetNameByInlineContext
title: IDebugSymbols4::GetNameByInlineContext
author: windows-driver-content
description: Gets a name by inline context.
old-location: debugger\idebugsymbols4_getnamebyinlinecontext.htm
old-project: debugger
ms.assetid: C87E70ED-FCB0-47B6-B6A3-A8EBC8E84058
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetNameByInlineContext, GetNameByInlineContext method [Windows Debugging], GetNameByInlineContext method [Windows Debugging],IDebugSymbols4 interface, IDebugSymbols4 interface [Windows Debugging],GetNameByInlineContext method, IDebugSymbols4.GetNameByInlineContext, IDebugSymbols4::GetNameByInlineContext, dbgeng/IDebugSymbols4::GetNameByInlineContext, debugger.idebugsymbols4_getnamebyinlinecontext
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
-	IDebugSymbols4.GetNameByInlineContext
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols4::GetNameByInlineContext


## -description


Gets a name by inline context.


## -parameters




### -param Offset [in]

An offset for the name.


### -param InlineContext [in]

The inline context.


### -param NameBuffer [out]

A pointer an output buffer.


### -param NameBufferSize [in]

The size of the name buffer.


### -param NameSize [out, optional]

A pointer to the length of the name.


### -param Displacement [out, optional]

A pointer to the displacement value of the name.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/BE2734B5-1E67-4E38-B4DF-0C353BFB1F0B">IDebugSymbols4</a>
 

 

