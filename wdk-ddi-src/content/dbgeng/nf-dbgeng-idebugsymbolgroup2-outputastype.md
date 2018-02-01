---
UID: NF:dbgeng.IDebugSymbolGroup2.OutputAsType
title: IDebugSymbolGroup2::OutputAsType method
author: windows-driver-content
description: The OutputAsType method changes the type of a symbol in a symbol group. The symbol's entry is updated to represent the new type.
old-location: debugger\outputastype.htm
old-project: debugger
ms.assetid: ab8c19c8-73c0-4c70-9a5d-9cf9d182157d
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSymbolGroup2::OutputAsType, IDebugSymbolGroup2, dbgeng/IDebugSymbolGroup2::OutputAsType, IDebugSymbolGroup::OutputAsType, OutputAsType method [Windows Debugging], dbgeng/IDebugSymbolGroup::OutputAsType, OutputAsType, OutputAsType method [Windows Debugging], IDebugSymbolGroup interface, ComOther_6805cc12-0d46-4114-a40d-54c7e32b3c7c.xml, OutputAsType method [Windows Debugging], IDebugSymbolGroup2 interface, IDebugSymbolGroup2 interface [Windows Debugging], OutputAsType method, IDebugSymbolGroup interface [Windows Debugging], OutputAsType method, debugger.outputastype
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
-	IDebugSymbolGroup.OutputAsType
-	IDebugSymbolGroup2.OutputAsType
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbolGroup2::OutputAsType method


## -description


The <b>OutputAsType</b>  method changes the type of a symbol in a symbol group.  The symbol's entry is updated to represent the new type. 


## -syntax


````
HRESULT OutputAsType(
  [in] ULONG Index,
  [in] PCSTR Type
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


Because the children of the new entry type might differ from the children of the old entry type, the <b>OutputAsType</b> method removes all of the children of the entry from the symbol group.  You can add the children back by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543271">ExpandSymbol</a> method.

If <i>Type</i> is an extension, the address of the symbol is passed to the extension.  Every line of output from the extension becomes a child symbol of the specified symbol.  These child symbols are text and you cannot manipulate them in any way.  For example, if the name of a variable is <b>@$teb</b>, you can change its type to <b>!teb</b>.

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543271">ExpandSymbol</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup::OutputAsType method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

