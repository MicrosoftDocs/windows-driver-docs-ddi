---
UID: NF:dbgeng.IDebugSymbols3.GetModuleByIndex
title: IDebugSymbols3::GetModuleByIndex method
author: windows-driver-content
description: The GetModuleByIndex method returns the location of the module with the specified index.
old-location: debugger\getmodulebyindex.htm
old-project: debugger
ms.assetid: a33f8a78-4026-4424-af42-2ad359054556
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::GetModuleByIndex, GetModuleByIndex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSymbols.GetModuleByIndex,IDebugSymbols2.GetModuleByIndex,IDebugSymbols3.GetModuleByIndex
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugSymbols3::GetModuleByIndex method



## -description
The <b>GetModuleByIndex</b> method returns the location of the module with the specified index.



## -syntax

````
HRESULT GetModuleByIndex(
  [in]  ULONG    Index,
  [out] PULONG64 Base
);
````


## -parameters

### -param Index [in]

Specifies the index of the module whose location is requested.


### -param Base [out]

Receives the location in the target's memory address space of the module.


## -returns
This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The specified module was not loaded, and information about the module was not available.

 


## -remarks
For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.</p>