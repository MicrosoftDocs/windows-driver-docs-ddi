---
UID: NF:dbgeng.IDebugSymbolGroup2.RemoveSymbolByNameWide
title: IDebugSymbolGroup2::RemoveSymbolByNameWide method
author: windows-driver-content
description: The RemoveSymbolByNameWide method removes the specified symbol from a symbol group.
old-location: debugger\removesymbolbynamewide.htm
old-project: debugger
ms.assetid: 12261b88-681e-4623-b5af-abaae756e3e1
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugSymbolGroup2, IDebugSymbolGroup2 interface [Windows Debugging], RemoveSymbolByNameWide method, IDebugSymbolGroup2::RemoveSymbolByNameWide, RemoveSymbolByNameWide method [Windows Debugging], RemoveSymbolByNameWide method [Windows Debugging], IDebugSymbolGroup2 interface, RemoveSymbolByNameWide,IDebugSymbolGroup2.RemoveSymbolByNameWide, dbgeng/IDebugSymbolGroup2::RemoveSymbolByNameWide, debugger.removesymbolbynamewide
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
-	IDebugSymbolGroup2.RemoveSymbolByNameWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbolGroup2::RemoveSymbolByNameWide method


## -description


The  <b>RemoveSymbolByNameWide</b> method removes the specified symbol from a symbol group.


## -parameters




### -param Name [in]

The name of the symbol to remove from the symbol group.


## -returns



<b>RemoveSymbolByNameWide</b> might return one of the following values:

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550846">IDebugSymbolGroup2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554510">RemoveSymbolByIndex</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup2::RemoveSymbolByNameWide method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
