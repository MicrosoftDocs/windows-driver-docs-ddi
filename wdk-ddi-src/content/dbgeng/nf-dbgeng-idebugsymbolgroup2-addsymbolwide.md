---
UID: NF:dbgeng.IDebugSymbolGroup2.AddSymbolWide
title: IDebugSymbolGroup2::AddSymbolWide method
author: windows-driver-content
description: The AddSymbolWide method adds a symbol to a symbol group.
old-location: debugger\addsymbolwide.htm
old-project: debugger
ms.assetid: 1c363649-4eff-4ad1-bc31-b060e2eb15d5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: AddSymbolWide method [Windows Debugging], AddSymbolWide method [Windows Debugging], IDebugSymbolGroup2 interface, AddSymbolWide,IDebugSymbolGroup2.AddSymbolWide, IDebugSymbolGroup2, IDebugSymbolGroup2 interface [Windows Debugging], AddSymbolWide method, IDebugSymbolGroup2::AddSymbolWide, dbgeng/IDebugSymbolGroup2::AddSymbolWide, debugger.addsymbolwide
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
-	IDebugSymbolGroup2.AddSymbolWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbolGroup2::AddSymbolWide method


## -description


The <b>AddSymbolWide</b> method adds a symbol to a <a href="https://msdn.microsoft.com/94cbf33b-e975-49eb-a266-774798955a48">symbol group</a>.


## -syntax


````
HRESULT AddSymbolWide(
  [in]      PCWSTR Name,
  [in, out] PULONG Index
);
````


## -parameters




### -param Name [in]

The symbol's name.  <i>Name</i> is examined as an expression to determine the symbol's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439450">type</a>.  This expression can include pointer, array, and structure dereferencing (for example, <b>*my_pointer</b>, <b>my_array[1]</b>, or <b>my_struct.some_field</b>).


### -param Index [in, out]

The index of the entry in the symbol group.  When you are calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff537925">AddSymbol</a> or <b>AddSymbolWide</b>, <i>Index</i> should point to the index of the symbol that you want. Or, if <i>Index</i> points to DEBUG_ANY_ID, the symbol is appended to the end of the list.   

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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup2::AddSymbolWide method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

