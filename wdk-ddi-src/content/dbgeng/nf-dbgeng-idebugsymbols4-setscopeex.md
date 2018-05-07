---
UID: NF:dbgeng.IDebugSymbols4.SetScopeEx
title: IDebugSymbols4::SetScopeEx
author: windows-driver-content
description: Sets the scope as an extended frame structure.
old-location: debugger\idebugsymbols4_setscopeex.htm
old-project: debugger
ms.assetid: 22844EBB-9BE7-47C0-BE1F-075473430F11
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugSymbols4 interface [Windows Debugging],SetScopeEx method, IDebugSymbols4.SetScopeEx, IDebugSymbols4::SetScopeEx, SetScopeEx, SetScopeEx method [Windows Debugging], SetScopeEx method [Windows Debugging],IDebugSymbols4 interface, dbgeng/IDebugSymbols4::SetScopeEx, debugger.idebugsymbols4_setscopeex
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
-	IDebugSymbols4.SetScopeEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols4::SetScopeEx


## -description


Sets the scope as an extended frame structure. 


## -parameters




### -param InstructionOffset [in]

The offset of the instruction for the scope. 


### -param ScopeFrame [in, optional]

The scope frame to set as a <a href="https://msdn.microsoft.com/library/windows/hardware/dn818561">DEBUG_STACK_FRAME_EX</a> structure. 


### -param ScopeContext [in]

A pointer to a scope context. 


### -param ScopeContextSize [in]

The size of the scope context.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn818561">DEBUG_STACK_FRAME_EX</a>



<a href="https://msdn.microsoft.com/BE2734B5-1E67-4E38-B4DF-0C353BFB1F0B">IDebugSymbols4</a>
 

 

