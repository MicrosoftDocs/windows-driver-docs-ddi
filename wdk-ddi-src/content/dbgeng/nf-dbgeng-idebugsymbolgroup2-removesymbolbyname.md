---
UID: NF:dbgeng.IDebugSymbolGroup2.RemoveSymbolByName
title: IDebugSymbolGroup2::RemoveSymbolByName
author: windows-driver-content
description: The RemoveSymbolByName method removes the specified symbol from a symbol group.
old-location: debugger\removesymbolbyname.htm
tech.root: debugger
ms.assetid: 2b03f010-cc3c-48a1-b86c-df470a832c94
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: ComOther_894176f1-bf26-4780-b287-a97993dd6e79.xml, IDebugSymbolGroup interface [Windows Debugging],RemoveSymbolByName method, IDebugSymbolGroup2 interface [Windows Debugging],RemoveSymbolByName method, IDebugSymbolGroup2.RemoveSymbolByName, IDebugSymbolGroup2::RemoveSymbolByName, IDebugSymbolGroup::RemoveSymbolByName, RemoveSymbolByName, RemoveSymbolByName method [Windows Debugging], RemoveSymbolByName method [Windows Debugging],IDebugSymbolGroup interface, RemoveSymbolByName method [Windows Debugging],IDebugSymbolGroup2 interface, dbgeng/IDebugSymbolGroup2::RemoveSymbolByName, dbgeng/IDebugSymbolGroup::RemoveSymbolByName, debugger.removesymbolbyname
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
-	IDebugSymbolGroup.RemoveSymbolByName
-	IDebugSymbolGroup2.RemoveSymbolByName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2::RemoveSymbolByName


## -description


The <b>RemoveSymbolByName</b>  method removes the specified symbol from a symbol group.


## -parameters




### -param Name [in]

The name of the symbol to remove from the symbol group.


## -returns



<b>RemoveSymbolByName</b> might return one of the following values:

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549121">GetSymbolName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550838">IDebugSymbolGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550846">IDebugSymbolGroup2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554510">RemoveSymbolByIndex</a>
 

 

