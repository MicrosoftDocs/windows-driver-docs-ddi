---
UID: NN:dbgeng.IDebugSymbolGroup2
title: IDebugSymbolGroup2
author: windows-driver-content
description: IDebugSymbolGroup2 interface
old-location: debugger\idebugsymbolgroup2.htm
old-project: debugger
ms.assetid: d702fe69-966c-4b9a-aa0e-b8376288cb79
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IDebugSymbolGroup2, IDebugSymbolGroup2 interface [Windows Debugging], IDebugSymbolGroup2 interface [Windows Debugging], described, dbgeng/IDebugSymbolGroup2, debugger.idebugsymbolgroup2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
-	IDebugSymbolGroup2
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbolGroup2 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSymbolGroup2</b> interface inherits from <a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>. <b>IDebugSymbolGroup2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugSymbolGroup2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537934">AddSymbolWide</a>
</td>
<td align="left" width="63%">
Adds a symbol to a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548484">GetSymbolEntryInformation</a>
</td>
<td align="left" width="63%">
Returns information about a symbol in a symbol group.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549129">GetSymbolNameWide</a>
</td>
<td align="left" width="63%">
Returns the name of a symbol in a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549135">GetSymbolOffset</a>
</td>
<td align="left" width="63%">
Retrieves the location in the process's virtual address space of a symbol in a symbol group, if the symbol has an absolute address.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549165">GetSymbolRegister</a>
</td>
<td align="left" width="63%">
Returns the register that contains the value or a pointer to the value of a symbol in a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549169">GetSymbolSize</a>
</td>
<td align="left" width="63%">
Returns the size of a symbol's value.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549188">GetSymbolTypeName</a>
</td>
<td align="left" width="63%">
Returns the name of the specified symbol's type.
(ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549192">GetSymbolTypeNameWide</a>
</td>
<td align="left" width="63%">
Returns the name of the specified symbol's type.
(Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549201">GetSymbolValueText</a>
</td>
<td align="left" width="63%">
Returns a string that represents the value of a symbol.
(ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549208">GetSymbolValueTextWide</a>
</td>
<td align="left" width="63%">
Returns a string that represents the value of a symbol.
(Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553198">OutputAsTypeWide</a>
</td>
<td align="left" width="63%">
Changes the type of a symbol in a symbol group. The symbol's entry is updated to represent the new type.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554526">RemoveSymbolByNameWide</a>
</td>
<td align="left" width="63%">
Removes the specified symbol from a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561460">WriteSymbolWide</a>
</td>
<td align="left" width="63%">
Sets the value of the specified symbol.

</td>
</tr>
</table> 


## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup2 interface%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

