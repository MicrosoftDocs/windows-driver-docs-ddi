---
UID: NF:dbgeng.IDebugSymbols3.SetScopeFromJitDebugInfo
title: IDebugSymbols3::SetScopeFromJitDebugInfo method
author: windows-driver-content
description: Recovers just-in-time (JIT) debugging information and sets current debugger scope context based on that information.
old-location: debugger\idebugsymbols3_setscopefromjitdebuginfo.htm
old-project: debugger
ms.assetid: 75417373-AA1B-4297-863A-00EA97069573
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], SetScopeFromJitDebugInfo method, IDebugSymbols3::SetScopeFromJitDebugInfo, SetScopeFromJitDebugInfo method [Windows Debugging], SetScopeFromJitDebugInfo method [Windows Debugging], IDebugSymbols3 interface, SetScopeFromJitDebugInfo,IDebugSymbols3.SetScopeFromJitDebugInfo, dbgeng/IDebugSymbols3::SetScopeFromJitDebugInfo, debugger.idebugsymbols3_setscopefromjitdebuginfo
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
-	IDebugSymbols3.SetScopeFromJitDebugInfo
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::SetScopeFromJitDebugInfo method


## -description


Recovers just-in-time (JIT) debugging information and sets current
    debugger scope context based on that information.


## -syntax


````
HRESULT SetScopeFromJitDebugInfo(
  [in] ULONG   OutputControl,
  [in] ULONG64 InfoOffset
);
````


## -parameters




### -param OutputControl [in]

An output control.


### -param InfoOffset [in]

An offset for the debugging information. 


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

The method gets JUT debugging information from   a specified address from the debugging target, and then sets the current
    debugger scope context from that information. 

This method is equivalent to '.jdinfo' command.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 


