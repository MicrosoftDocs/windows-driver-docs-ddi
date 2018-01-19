---
UID: NF:dbgeng.IDebugSymbolGroup2.RemoveSymbolByNameWide
title: IDebugSymbolGroup2::RemoveSymbolByNameWide method
author: windows-driver-content
description: The RemoveSymbolByNameWide method removes the specified symbol from a symbol group.
old-location: debugger\removesymbolbynamewide.htm
old-project: debugger
ms.assetid: 12261b88-681e-4623-b5af-abaae756e3e1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbolGroup2, IDebugSymbolGroup2::RemoveSymbolByNameWide, RemoveSymbolByNameWide
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
req.alt-api: IDebugSymbolGroup2.RemoveSymbolByNameWide
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

# IDebugSymbolGroup2::RemoveSymbolByNameWide method



## -description
The  <b>RemoveSymbolByNameWide</b> method removes the specified symbol from a symbol group.



## -syntax

````
HRESULT RemoveSymbolByNameWide(
  [in] PCWSTR Name
);
````


## -parameters

### -param Name [in]

The name of the symbol to remove from the symbol group.


## -returns
<b>RemoveSymbolByNameWide</b> might return one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
When a symbol is removed, the indexes of the symbols that remain in the symbol group might change.

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537925">AddSymbol</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549121">GetSymbolName</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554510">RemoveSymbolByIndex</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup2::RemoveSymbolByNameWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

