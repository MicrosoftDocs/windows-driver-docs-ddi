---
UID: NF:dbgeng.IDebugSymbols2.GetSymbolModule
title: IDebugSymbols2::GetSymbolModule method
author: windows-driver-content
description: The GetSymbolModule method returns the base address of module which contains the specified symbol.
old-location: debugger\getsymbolmodule.htm
old-project: debugger
ms.assetid: f3774204-86c3-467b-96ba-739f19d300e3
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetSymbolModule method [Windows Debugging], dbgeng/IDebugSymbols3::GetSymbolModule, GetSymbolModule method [Windows Debugging], IDebugSymbols interface, dbgeng/IDebugSymbols::GetSymbolModule, IDebugSymbols interface [Windows Debugging], GetSymbolModule method, IDebugSymbols2 interface [Windows Debugging], GetSymbolModule method, GetSymbolModule method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols2, IDebugSymbols3::GetSymbolModule, IDebugSymbols_a680615c-bc2a-4fa3-a83a-6960ed64c1e9.xml, IDebugSymbols2::GetSymbolModule, IDebugSymbols, GetSymbolModule, IDebugSymbols3 interface [Windows Debugging], GetSymbolModule method, IDebugSymbols::GetSymbolModule, debugger.getsymbolmodule, dbgeng/IDebugSymbols2::GetSymbolModule, GetSymbolModule method [Windows Debugging], IDebugSymbols2 interface
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
-	dbgeng.h
apiname:
-	IDebugSymbols.GetSymbolModule
-	IDebugSymbols2.GetSymbolModule
-	IDebugSymbols3.GetSymbolModule
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSymbols2::GetSymbolModule method


## -description


The <b>GetSymbolModule</b> method returns the base address of module which contains the specified symbol.


## -syntax


````
HRESULT GetSymbolModule(
  [in]  PCSTR    Symbol,
  [out] PULONG64 Base
);
````


## -parameters




### -param Symbol [in]

Specifies the name of the symbol to look up.  See the Remarks section for details of the syntax of this name.


### -param Base [out]

Receives the location in the target's memory address space of the base of the module.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The symbol or module could not be found.

</td>
</tr>
</table>
 




## -remarks



The string <i>Symbol</i> must contain an exclamation point ( <b>!</b> ).  If <i>Symbol</i> is a module-qualified symbol name (for example, <b>mymodules!main</b>) or if the module name is omitted (for example, <b>!main</b>), the engine will search for this symbol and return the module in which it is found.  If <i>Symbol</i> contains just a module name (for example, <b>mymodule!</b>) the engine returns the first module with this module name.

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.



