---
UID: NF:dbgeng.IDebugSymbols5.GetCurrentScopeFrameIndexEx
title: IDebugSymbols5::GetCurrentScopeFrameIndexEx method
author: windows-driver-content
description: Gets the index of the current frame.
old-location: debugger\idebugsymbols5_getcurrentscopeframeindexex.htm
old-project: debugger
ms.assetid: 0D8198BB-583F-4828-8131-61EB17621F32
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetCurrentScopeFrameIndexEx method [Windows Debugging], GetCurrentScopeFrameIndexEx method [Windows Debugging], IDebugSymbols5 interface, GetCurrentScopeFrameIndexEx,IDebugSymbols5.GetCurrentScopeFrameIndexEx, IDebugSymbols5, IDebugSymbols5 interface [Windows Debugging], GetCurrentScopeFrameIndexEx method, IDebugSymbols5::GetCurrentScopeFrameIndexEx, dbgeng/IDebugSymbols5::GetCurrentScopeFrameIndexEx, debugger.idebugsymbols5_getcurrentscopeframeindexex
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
-	IDebugSymbols5.GetCurrentScopeFrameIndexEx
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols5::GetCurrentScopeFrameIndexEx method


## -description


Gets the index of the current frame.


## -syntax


````
HRESULT GetCurrentScopeFrameIndexEx(
  [in]  ULONG  Flags,
  [out] PULONG Index
);
````


## -parameters




### -param Flags [in]

A bit-set that contains options that affect the behavior of this method. 


### -param Index [out]

A pointer to an index that this function gets.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols5.md">IDebugSymbols5</a>



 

 


