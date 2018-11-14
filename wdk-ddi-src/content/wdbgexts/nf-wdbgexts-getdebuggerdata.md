---
UID: NF:wdbgexts.GetDebuggerData
title: GetDebuggerData macro
author: windows-driver-content
description: The GetDebuggerData function retrieves information stored in a data block.
old-location: debugger\getdebuggerdata.htm
tech.root: debugger
ms.assetid: a07afa2e-1f7d-4685-9ede-8b7805dd6583
ms.date: 11/13/2018
ms.keywords: GetDebuggerData, GetDebuggerData function [Windows Debugging], WdbgExts_Ref_a9b54b49-d8ac-4bee-a837-3986a250403a.xml, debugger.getdebuggerdata, wdbgexts/GetDebuggerData
ms.topic: macro
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
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
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	GetDebuggerData
product:
- Windows
targetos: Windows
req.typenames: 
---

# GetDebuggerData macro


## -description


The <b>GetDebuggerData</b> function retrieves information stored in a data block.


## -parameters




### -param TAG

<p>This should be set equal to KDBG_TAG. (This value is specified in wdbgexts.h.)</p>


### -param BUF

<p>Points to the debugger data block.</p>


### -param SIZE

<p>Specifies the size of the data block, including the header.</p>

## -returns

If the data block is found, the return value is TRUE; otherwise, it is FALSE.





