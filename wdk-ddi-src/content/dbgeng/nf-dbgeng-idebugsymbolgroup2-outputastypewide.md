---
UID: NF:dbgeng.IDebugSymbolGroup2.OutputAsTypeWide
title: IDebugSymbolGroup2::OutputAsTypeWide method
author: windows-driver-content
description: The OutputAsTypeWide method changes the type of a symbol in a symbol group. The symbol's entry is updated to represent the new type.
old-location: debugger\outputastypewide.htm
old-project: debugger
ms.assetid: f43b702d-37a7-484d-8a18-fa190e9189b2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugSymbolGroup2, IDebugSymbolGroup2 interface [Windows Debugging], OutputAsTypeWide method, IDebugSymbolGroup2::OutputAsTypeWide, OutputAsTypeWide method [Windows Debugging], OutputAsTypeWide method [Windows Debugging], IDebugSymbolGroup2 interface, OutputAsTypeWide,IDebugSymbolGroup2.OutputAsTypeWide, dbgeng/IDebugSymbolGroup2::OutputAsTypeWide, debugger.outputastypewide
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
-	IDebugSymbolGroup2.OutputAsTypeWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbolGroup2::OutputAsTypeWide method


## -description


The <b>OutputAsTypeWide</b> method changes the type of a symbol in a symbol group.  The symbol's entry is updated to represent the new type. 


## -syntax


````
HRESULT OutputAsTypeWide(
  [in] ULONG  Index,
  [in] PCWSTR Type
);
````


## -parameters




### -param Index [in]

The index of the entry in this symbol group.  The <i>index</i> of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


### -param Type [in]

The name of the type of the symbol that you want.  If the name begins with an exclamation mark (<b>!</b>), the name is treated as an extension.  For more information about how to use an extension as a type, see the Remarks section.


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



Because the children of the new entry type might differ from the children of the old entry type, the <b>OutputAsTypeWide</b> method removes all of the children of the entry from the symbol group.  You can add the children back by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543271">ExpandSymbol</a> method.

If <i>Type</i> is an extension, the address of the symbol is passed to the extension.  Every line of output from the extension becomes a child symbol of the specified symbol.  These child symbols are text and you cannot manipulate them in any way.  For example, if the name of a variable is <b>@$teb</b>, you can change its type to <b>!teb</b>.

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543271">ExpandSymbol</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>



 

 


