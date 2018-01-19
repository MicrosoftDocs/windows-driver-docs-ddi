---
UID: NF:dbgeng.IDebugRegisters2.GetNumberRegisters
title: IDebugRegisters2::GetNumberRegisters method
author: windows-driver-content
description: The GetNumberRegisters method returns the number of registers on the target computer.
old-location: debugger\getnumberregisters.htm
old-project: debugger
ms.assetid: 51c521fc-e89c-49c9-8110-de31af3bed83
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugRegisters2, IDebugRegisters2::GetNumberRegisters, GetNumberRegisters
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
req.alt-api: IDebugRegisters.GetNumberRegisters,IDebugRegisters2.GetNumberRegisters
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

# IDebugRegisters2::GetNumberRegisters method



## -description
The <b>GetNumberRegisters</b> method returns the number of <a href="debugger.x86_architecture#registers#registers">registers</a> on the target computer.



## -syntax

````
HRESULT GetNumberRegisters(
  [out] PULONG Number
);
````


## -parameters

### -param Number [out]

Receives the number of registers on the target's computer.


## -returns
This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.</p>