---
UID: NF:dbgeng.IDebugRegisters2.GetIndexByNameWide
title: IDebugRegisters2::GetIndexByNameWide method
author: windows-driver-content
description: The GetIndexByNameWide method returns the index of the named register.
old-location: debugger\getindexbynamewide.htm
old-project: debugger
ms.assetid: eb6a50b4-275f-42c9-8121-17677971ebb2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugRegisters2, IDebugRegisters2::GetIndexByNameWide, GetIndexByNameWide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugRegisters2.GetIndexByNameWide
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

# IDebugRegisters2::GetIndexByNameWide method



## -description
The <b>GetIndexByNameWide</b> method returns the index of the named register.



## -syntax

````
HRESULT GetIndexByNameWide(
  [in]  PCWSTR Name,
  [out] PULONG Index
);
````


## -parameters

### -param Name [in]

Specifies the name of the register whose index is requested.


### -param Index [out]

Receives the index of the register.


## -returns
This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>The register was not found.

 


## -remarks
For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.</p>