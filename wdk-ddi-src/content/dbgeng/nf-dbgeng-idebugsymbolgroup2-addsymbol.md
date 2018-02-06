---
UID: NF:dbgeng.IDebugSymbolGroup2.AddSymbol
title: IDebugSymbolGroup2::AddSymbol method
author: windows-driver-content
description: The AddSymbol method adds a symbol to a symbol group.
old-location: debugger\addsymbol.htm
old-project: debugger
ms.assetid: b77de459-b5ac-4752-89eb-f24fdde36134
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: ComOther_936851e7-6a8b-4b42-b339-9c8aa096d684.xml, IDebugSymbolGroup2 interface [Windows Debugging], AddSymbol method, IDebugSymbolGroup2, AddSymbol, IDebugSymbolGroup interface [Windows Debugging], AddSymbol method, AddSymbol method [Windows Debugging], IDebugSymbolGroup2 interface, dbgeng/IDebugSymbolGroup2::AddSymbol, AddSymbol method [Windows Debugging], debugger.addsymbol, IDebugSymbolGroup2::AddSymbol, IDebugSymbolGroup::AddSymbol, AddSymbol method [Windows Debugging], IDebugSymbolGroup interface, dbgeng/IDebugSymbolGroup::AddSymbol
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
-	Dbgeng.h
apiname:
-	IDebugSymbolGroup.AddSymbol
-	IDebugSymbolGroup2.AddSymbol
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSymbolGroup2::AddSymbol method


## -description


The <b>AddSymbol</b>  method adds a symbol to a <a href="https://msdn.microsoft.com/94cbf33b-e975-49eb-a266-774798955a48">symbol group</a>.


## -syntax


````
HRESULT AddSymbol(
  [in]      PCSTR  Name,
  [in, out] PULONG Index
);
````


## -parameters




### -param Name [in]

The symbol's name.  <i>Name</i> is examined as an expression to determine the symbol's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439450">type</a>.  This expression can include pointer, array, and structure dereferencing (for example, <b>*my_pointer</b>, <b>my_array[1]</b>, or <b>my_struct.some_field</b>).


### -param Index [in, out]

The index of the entry in the symbol group.  When you are calling <b>AddSymbol</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff537934">AddSymbolWide</a>, <i>Index</i> should point to the index of the symbol that you want. Or, if <i>Index</i> points to DEBUG_ANY_ID, the symbol is appended to the end of the list.   

When this method returns, <i>Index</i> points to the actual index of the symbol.  The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


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


The symbol name in <i>Name</i> is evaluated by the <a href="https://msdn.microsoft.com/e5d3ac7f-fd79-48bb-b927-9ad72570dcbe">C++ expression evaluator</a> and can contain any C++ expression (for example, <b>x+y</b>).

If the index that you want is less than the size of the symbol group, the new symbol is added at the desired index.  If the desired index is larger than the size of the symbol group, the new symbol is added to the end of the list (as in the case of DEBUG_ANY_ID).

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554510">RemoveSymbolByIndex</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554518">RemoveSymbolByName</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup::AddSymbol method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

