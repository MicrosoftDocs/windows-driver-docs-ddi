---
UID: NF:dbgeng.IDebugSymbols4.GetScopeEx
title: IDebugSymbols4::GetScopeEx (dbgeng.h)
description: Gets the scope as an extended frame structure.
old-location: debugger\idebugsymbols4_getscopeex.htm
tech.root: debugger
ms.assetid: B91EF786-51F7-406E-BCC2-C917E6881886
ms.date: 05/03/2018
keywords: ["IDebugSymbols4::GetScopeEx"]
ms.keywords: GetScopeEx, GetScopeEx method [Windows Debugging], GetScopeEx method [Windows Debugging],IDebugSymbols4 interface, IDebugSymbols4 interface [Windows Debugging],GetScopeEx method, IDebugSymbols4.GetScopeEx, IDebugSymbols4::GetScopeEx, dbgeng/IDebugSymbols4::GetScopeEx, debugger.idebugsymbols4_getscopeex
f1_keywords:
 - "dbgeng/IDebugSymbols4.GetScopeEx"
 - "IDebugSymbols4.GetScopeEx"
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
- IDebugSymbols4.GetScopeEx
targetos: Windows
req.typenames: 
---

# IDebugSymbols4::GetScopeEx


## -description


Gets the scope as an extended frame structure. 


## -parameters




### -param InstructionOffset 
[out, optional]
The offset of the instruction for the scope. 


### -param ScopeFrame 
[out, optional]
The scope frame returned as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_stack_frame_ex">DEBUG_STACK_FRAME_EX</a> structure. 


### -param ScopeContext 
[out]
A pointer to the scope context returned. 


### -param ScopeContextSize 
[in]
The size of the scope context.


## -returns



If this method succeeds, it returns **S_OK**. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_stack_frame_ex">DEBUG_STACK_FRAME_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols4">IDebugSymbols4</a>
 

 

