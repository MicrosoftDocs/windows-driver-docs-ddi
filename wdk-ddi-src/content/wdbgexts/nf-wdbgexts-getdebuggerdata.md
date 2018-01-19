---
UID: NF:wdbgexts.GetDebuggerData
title: GetDebuggerData macro
author: windows-driver-content
description: The GetDebuggerData function retrieves information stored in a data block.
old-location: debugger\getdebuggerdata.htm
old-project: debugger
ms.assetid: a07afa2e-1f7d-4685-9ede-8b7805dd6583
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: GetDebuggerData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetDebuggerData
req.alt-loc: wdbgexts.h
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
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# GetDebuggerData macro



## -description
The <b>GetDebuggerData</b> function retrieves information stored in a data block.



## -syntax

````
ULONG GetDebuggerData(
   ULONG Tag,
   PVOID Buf,
   ULONG Size
);
````


## -parameters

### -param Tag 

This should be set equal to KDBG_TAG. (This value is specified in wdbgexts.h.)


### -param Buf 

Points to the debugger data block.


### -param Size 

Specifies the size of the data block, including the header.


## -remarks
