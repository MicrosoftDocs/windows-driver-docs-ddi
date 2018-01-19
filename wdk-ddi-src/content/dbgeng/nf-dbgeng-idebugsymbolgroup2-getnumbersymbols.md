---
UID: NF:dbgeng.IDebugSymbolGroup2.GetNumberSymbols
title: IDebugSymbolGroup2::GetNumberSymbols method
author: windows-driver-content
description: The GetNumberSymbols method returns the number of symbols that are contained in a symbol group.
old-location: debugger\getnumbersymbols.htm
old-project: debugger
ms.assetid: 5a202530-7146-472d-9560-580871cd56ec
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbolGroup2, IDebugSymbolGroup2::GetNumberSymbols, GetNumberSymbols
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
req.alt-api: IDebugSymbolGroup.GetNumberSymbols,IDebugSymbolGroup2.GetNumberSymbols
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

# IDebugSymbolGroup2::GetNumberSymbols method



## -description
The <b>GetNumberSymbols</b> method returns the number of <a href="debugger.symbols#symbols#symbols">symbols</a> that are contained in a symbol group.



## -syntax

````
HRESULT GetNumberSymbols(
  [out] PULONG Number
);
````


## -parameters

### -param Number [out]

The number of symbols that are contained in this symbol group.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
Each symbol in a symbol group is identified by an <i>index</i>.  This index is a number between zero and the number that is returned to <i>Number</i> minus one.  Every time that a symbol is added or removed from the symbol group, the index of all of the symbols in the group might change.

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.</p>