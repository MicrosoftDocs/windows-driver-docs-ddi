---
UID: NF:dbgeng.IDebugSymbols4.GetLineByInlineContext
title: IDebugSymbols4::GetLineByInlineContext method
author: windows-driver-content
description: Gets a line by inline context.
old-location: debugger\idebugsymbols4_getlinebyinlinecontext.htm
old-project: debugger
ms.assetid: AFDB4DB4-3C63-44A0-88D7-C8047ECB2261
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetLineByInlineContext method [Windows Debugging], GetLineByInlineContext method [Windows Debugging], IDebugSymbols4 interface, GetLineByInlineContext,IDebugSymbols4.GetLineByInlineContext, IDebugSymbols4, IDebugSymbols4 interface [Windows Debugging], GetLineByInlineContext method, IDebugSymbols4::GetLineByInlineContext, dbgeng/IDebugSymbols4::GetLineByInlineContext, debugger.idebugsymbols4_getlinebyinlinecontext
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
-	IDebugSymbols4.GetLineByInlineContext
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols4::GetLineByInlineContext method


## -description


Gets a line by inline context.


## -syntax


````
HRESULT GetLineByInlineContext(
  [in]            ULONG64                           Offset,
  [in]            ULONG                             InlineContext,
  [out, optional] PULONG                            Line,
  [out]           _writes_opt_(FileBufferSize) PSTR FileBuffer,
  [in]            FileBufferSize                    FileBufferSize,
  [out, optional] PULONG                            FileSize,
  [out, optional] PULONG64                          Displacement
);
````


## -parameters




### -param Offset [in]

An offset for the line.


### -param InlineContext [in]

The inline context. 


### -param Line [out, optional]

A pointer to the returned line.


### -param FileBuffer [out]

A pointer to an output buffer.


### -param FileBufferSize [in]

The size of the file buffer.


### -param FileSize [out, optional]

A pointer to the length of the file.


### -param Displacement [out, optional]

A pointer to the displacement value of the file.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols4.md">IDebugSymbols4</a>



 

 


