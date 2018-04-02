---
UID: NF:dbgeng.IDebugSymbolGroup.RemoveSymbolByIndex
title: IDebugSymbolGroup::RemoveSymbolByIndex method
author: windows-driver-content
description: The RemoveSymbolByIndex method removes the specified symbol from a symbol group.
old-location: debugger\removesymbolbyindex.htm
old-project: debugger
ms.assetid: 1903d454-02d1-4528-9b8f-3c2eab8c6a6a
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: ComOther_d532b37e-11c9-4cff-a619-0b9dffef0af1.xml, IDebugSymbolGroup, IDebugSymbolGroup interface [Windows Debugging], RemoveSymbolByIndex method, IDebugSymbolGroup2 interface [Windows Debugging], RemoveSymbolByIndex method, IDebugSymbolGroup2::RemoveSymbolByIndex, IDebugSymbolGroup::RemoveSymbolByIndex, RemoveSymbolByIndex method [Windows Debugging], RemoveSymbolByIndex method [Windows Debugging], IDebugSymbolGroup interface, RemoveSymbolByIndex method [Windows Debugging], IDebugSymbolGroup2 interface, RemoveSymbolByIndex,IDebugSymbolGroup.RemoveSymbolByIndex, dbgeng/IDebugSymbolGroup2::RemoveSymbolByIndex, dbgeng/IDebugSymbolGroup::RemoveSymbolByIndex, debugger.removesymbolbyindex
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
-	IDebugSymbolGroup.RemoveSymbolByIndex
-	IDebugSymbolGroup2.RemoveSymbolByIndex
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbolGroup::RemoveSymbolByIndex method


## -description


The <b>RemoveSymbolByIndex</b> method removes the specified symbol from a symbol group.


## -parameters




### -param Index [in]

The index of the symbol to remove. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


## -returns



<b>RemoveSymbolByIndex</b> might return one of the following values:

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



When a symbol is removed, the indexes of the symbols that remain in the symbol group might change.  

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537925">AddSymbol</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550838">IDebugSymbolGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550846">IDebugSymbolGroup2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554518">RemoveSymbolByName</a>
 

 

