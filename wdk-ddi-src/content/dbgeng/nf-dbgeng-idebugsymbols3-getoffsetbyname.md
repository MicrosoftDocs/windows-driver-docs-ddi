---
UID: NF:dbgeng.IDebugSymbols3.GetOffsetByName
title: IDebugSymbols3::GetOffsetByName method
author: windows-driver-content
description: The GetOffsetByName method returns the location of a symbol identified by name.
old-location: debugger\getoffsetbyname.htm
old-project: debugger
ms.assetid: b6915215-3654-446b-b30d-b891f439a379
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetOffsetByName method [Windows Debugging], GetOffsetByName method [Windows Debugging], IDebugSymbols interface, GetOffsetByName method [Windows Debugging], IDebugSymbols2 interface, GetOffsetByName method [Windows Debugging], IDebugSymbols3 interface, GetOffsetByName,IDebugSymbols3.GetOffsetByName, IDebugSymbols interface [Windows Debugging], GetOffsetByName method, IDebugSymbols2 interface [Windows Debugging], GetOffsetByName method, IDebugSymbols2::GetOffsetByName, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetOffsetByName method, IDebugSymbols3::GetOffsetByName, IDebugSymbols::GetOffsetByName, IDebugSymbols_ef72e546-d27f-4cdf-9eeb-53151680c2d1.xml, dbgeng/IDebugSymbols2::GetOffsetByName, dbgeng/IDebugSymbols3::GetOffsetByName, dbgeng/IDebugSymbols::GetOffsetByName, debugger.getoffsetbyname
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugSymbols.GetOffsetByName
-	IDebugSymbols2.GetOffsetByName
-	IDebugSymbols3.GetOffsetByName
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetOffsetByName method


## -description


The <b>GetOffsetByName</b>  method returns the location of a symbol identified by name.


## -syntax


````
HRESULT GetOffsetByName(
  [in]  PCSTR    Symbol,
  [out] PULONG64 Offset
);
````


## -parameters




### -param Symbol [in]

Specifies the name of the symbol to locate.  The name may be qualified by a module name (for example, <b>mymodule!main</b>).


### -param Offset [out]

Receives the location in the target's memory address space of the base of the symbol's memory allocation.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, the name <i>Symbol</i> was not unique and multiple symbols with that name were found.  One of these symbols was arbitrarily chosen and returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
No symbol could be found with the specified name.

</td>
</tr>
</table>
 




## -remarks



If the name <i>Symbol</i> is not unique and <b>GetOffsetByName</b> finds multiple symbols with that name, then the ambiguity will be resolved arbitrarily.  In this case the value S_FALSE will be returned.  <a href="https://msdn.microsoft.com/library/windows/hardware/ff558815">StartSymbolMatch</a> can be used to initiate a search to determine which is the desired result.

<b>GetNameByOffset</b> does not support pattern matching (e.g. wildcards).  To find a symbol using pattern matching use <b>StartSymbolMatch</b>.

If the module name for the symbol is known, it is best to qualify the symbol name with the module name.  Otherwise the engine will search the symbols for all modules until it finds a match; this can take a long time if it has to load the symbol files for a lot of modules.  If the symbol name is qualified with a module name, the engine only searches the symbols for that module.  

For more information about symbols and symbol names, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547183">GetNameByOffset</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetOffsetByName method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

