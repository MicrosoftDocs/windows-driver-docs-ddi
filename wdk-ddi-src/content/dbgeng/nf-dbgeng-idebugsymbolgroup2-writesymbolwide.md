---
UID: NF:dbgeng.IDebugSymbolGroup2.WriteSymbolWide
title: IDebugSymbolGroup2::WriteSymbolWide
author: windows-driver-content
description: The WriteSymbolWide method sets the value of the specified symbol.
old-location: debugger\writesymbolwide.htm
old-project: debugger
ms.assetid: ed77fddf-c23c-4522-a2c4-875f07d249fb
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugSymbolGroup2 interface [Windows Debugging],WriteSymbolWide method, IDebugSymbolGroup2.WriteSymbolWide, IDebugSymbolGroup2::WriteSymbolWide, WriteSymbolWide, WriteSymbolWide method [Windows Debugging], WriteSymbolWide method [Windows Debugging],IDebugSymbolGroup2 interface, dbgeng/IDebugSymbolGroup2::WriteSymbolWide, debugger.writesymbolwide
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugSymbolGroup2.WriteSymbolWide
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2::WriteSymbolWide


## -description


The <b>WriteSymbolWide</b> method sets the value of the specified symbol.


## -parameters




### -param Index [in]

The index of the symbol whose value will be changed. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


### -param Value [in]

A C++ expression that is evaluated to give the symbol's new value.


## -returns



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
</table>
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.




## -remarks



This method can change symbols only if the symbols are stored in a register or memory location that the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> knowns and if they have not had their type changed to an extension by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553191">OutputAsType</a> method.  

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549201">GetSymbolValueText</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550846">IDebugSymbolGroup2</a>
 

 

