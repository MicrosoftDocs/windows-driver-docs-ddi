---
UID: NF:dbgeng.IDebugSymbols3.CreateSymbolGroup2
title: IDebugSymbols3::CreateSymbolGroup2
author: windows-driver-content
description: The CreateSymbolGroup2 method creates a new symbol group.
old-location: debugger\createsymbolgroup2.htm
tech.root: debugger
ms.assetid: 42ddf77a-14c8-4d6a-98a2-b0c67836990d
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: CreateSymbolGroup2, CreateSymbolGroup2 method [Windows Debugging], CreateSymbolGroup2 method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],CreateSymbolGroup2 method, IDebugSymbols3.CreateSymbolGroup2, IDebugSymbols3::CreateSymbolGroup2, dbgeng/IDebugSymbols3::CreateSymbolGroup2, debugger.createsymbolgroup2
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
-	Dbgeng.h
api_name:
-	IDebugSymbols3.CreateSymbolGroup2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::CreateSymbolGroup2


## -description


The <b>CreateSymbolGroup2</b>  method creates a new symbol group.


## -parameters




### -param Group [out]

Receives an interface pointer for the new <a href="https://msdn.microsoft.com/library/windows/hardware/ff550838">IDebugSymbolGroup</a> object.


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
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



The newly created symbol group is empty; it does not contain any <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">symbols</a>.  Symbols may be added to the symbol group using <a href="https://msdn.microsoft.com/b77de459-b5ac-4752-89eb-f24fdde36134">IDebugSymbolGroup::AddSymbol</a>.

References to the returned object are managed like other COM objects, using the <b>IUnknown::AddRef</b> and <b>IUnknown::Release</b> methods.  In particular, the <b>IUnknown::Release</b> method must be called when the returned object is no longer needed.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff560088">Using Client Objects</a> for more information about using COM interfaces in the Debugger Engine API.

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550838">IDebugSymbolGroup</a>



<a href="https://msdn.microsoft.com/b77de459-b5ac-4752-89eb-f24fdde36134">IDebugSymbolGroup::AddSymbol</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

