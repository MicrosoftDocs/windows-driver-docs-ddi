---
UID: NF:dbgeng.IDebugSymbolGroup2.RemoveSymbolByName
title: IDebugSymbolGroup2::RemoveSymbolByName method
author: windows-driver-content
description: The RemoveSymbolByName method removes the specified symbol from a symbol group.
old-location: debugger\removesymbolbyname.htm
old-project: debugger
ms.assetid: 2b03f010-cc3c-48a1-b86c-df470a832c94
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSymbolGroup2::RemoveSymbolByName, dbgeng/IDebugSymbolGroup2::RemoveSymbolByName, IDebugSymbolGroup2, RemoveSymbolByName method [Windows Debugging], IDebugSymbolGroup2 interface, RemoveSymbolByName method [Windows Debugging], IDebugSymbolGroup interface, dbgeng/IDebugSymbolGroup::RemoveSymbolByName, ComOther_894176f1-bf26-4780-b287-a97993dd6e79.xml, debugger.removesymbolbyname, IDebugSymbolGroup2 interface [Windows Debugging], RemoveSymbolByName method, RemoveSymbolByName method [Windows Debugging], IDebugSymbolGroup interface [Windows Debugging], RemoveSymbolByName method, RemoveSymbolByName, IDebugSymbolGroup::RemoveSymbolByName
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
-	IDebugSymbolGroup.RemoveSymbolByName
-	IDebugSymbolGroup2.RemoveSymbolByName
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugSymbolGroup2::RemoveSymbolByName method


## -description


The <b>RemoveSymbolByName</b>  method removes the specified symbol from a symbol group.


## -syntax


````
HRESULT RemoveSymbolByName(
  [in] PCSTR Name
);
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549121">GetSymbolName</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554510">RemoveSymbolByIndex</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537925">AddSymbol</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup::RemoveSymbolByName method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

