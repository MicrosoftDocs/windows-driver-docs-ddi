---
UID: NF:dbgeng.IDebugSymbols4.SetScopeEx
title: IDebugSymbols4::SetScopeEx method
author: windows-driver-content
description: Sets the scope as an extended frame structure.
old-location: debugger\idebugsymbols4_setscopeex.htm
old-project: debugger
ms.assetid: 22844EBB-9BE7-47C0-BE1F-075473430F11
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: SetScopeEx method [Windows Debugging], IDebugSymbols4 interface, SetScopeEx method [Windows Debugging], IDebugSymbols4, IDebugSymbols4::SetScopeEx, dbgeng/IDebugSymbols4::SetScopeEx, debugger.idebugsymbols4_setscopeex, IDebugSymbols4 interface [Windows Debugging], SetScopeEx method, SetScopeEx
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Dbgeng.h
apiname:
-	IDebugSymbols4.SetScopeEx
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSymbols4::SetScopeEx method


## -description


Sets the scope as an extended frame structure. 


## -syntax


````
HRESULT SetScopeEx(
  [in]           ULONG64                                   InstructionOffset,
  [in, optional] PDEBUG_STACK_FRAME_EX                     ScopeFrame,
  [in]           _reads_bytes_opt_(ScopeContextSize) PVOID ScopeContext,
  [in]           ULONG                                     ScopeContextSize
);
````


## -parameters




### -param InstructionOffset [in]

The offset of the instruction for the scope. 


### -param ScopeFrame [in, optional]

The scope frame to set as a <a href="..\dbgeng\ns-dbgeng-_debug_stack_frame_ex.md">DEBUG_STACK_FRAME_EX</a> structure. 


### -param ScopeContext [in]

A pointer to a scope context. 


### -param ScopeContextSize [in]

The size of the scope context.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols4.md">IDebugSymbols4</a>



<a href="..\dbgeng\ns-dbgeng-_debug_stack_frame_ex.md">DEBUG_STACK_FRAME_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols4::SetScopeEx method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

