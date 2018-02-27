---
UID: NF:dbgeng.IDebugSymbols2.StartSymbolMatch
title: IDebugSymbols2::StartSymbolMatch method
author: windows-driver-content
description: The StartSymbolMatch method initializes a search for symbols whose names match a given pattern.
old-location: debugger\startsymbolmatch.htm
old-project: debugger
ms.assetid: 465b13a7-59e0-47f8-9e33-82043a23f146
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IDebugSymbols interface [Windows Debugging], StartSymbolMatch method, IDebugSymbols2, IDebugSymbols2 interface [Windows Debugging], StartSymbolMatch method, IDebugSymbols2::StartSymbolMatch, IDebugSymbols3 interface [Windows Debugging], StartSymbolMatch method, IDebugSymbols3::StartSymbolMatch, IDebugSymbols::StartSymbolMatch, IDebugSymbols_4b000f13-0dc1-4a2c-8de3-3bf5384172c3.xml, StartSymbolMatch method [Windows Debugging], StartSymbolMatch method [Windows Debugging], IDebugSymbols interface, StartSymbolMatch method [Windows Debugging], IDebugSymbols2 interface, StartSymbolMatch method [Windows Debugging], IDebugSymbols3 interface, StartSymbolMatch,IDebugSymbols2.StartSymbolMatch, dbgeng/IDebugSymbols2::StartSymbolMatch, dbgeng/IDebugSymbols3::StartSymbolMatch, dbgeng/IDebugSymbols::StartSymbolMatch, debugger.startsymbolmatch
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
-	IDebugSymbols.StartSymbolMatch
-	IDebugSymbols2.StartSymbolMatch
-	IDebugSymbols3.StartSymbolMatch
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols2::StartSymbolMatch method


## -description


The <b>StartSymbolMatch</b> method initializes a search for symbols whose names match a given pattern.


## -syntax


````
HRESULT StartSymbolMatch(
  [in]  PCSTR    Pattern,
  [out] PULONG64 Handle
);
````


## -parameters




### -param Pattern [in]

Specifies the pattern for which to search.  The search will return all symbols whose names match this pattern.  For details of the syntax of the pattern, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558843">Symbol Syntax and Symbol Matching</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff558819">String Wildcard Syntax</a>.


### -param Handle [out]

Receives the handle identifying the search.  This handle can be passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547856">GetNextSymbolMatch</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543008">EndSymbolMatch</a>.


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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The specified module was not found.

</td>
</tr>
</table>
 




## -remarks



This method initializes a symbol search.  The results of the search can be obtained by repeated calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547856">GetNextSymbolMatch</a>.  When all the desired results have been found, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff543008">EndSymbolMatch</a> to release resources the engine holds for the search.

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543008">EndSymbolMatch</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547856">GetNextSymbolMatch</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::StartSymbolMatch method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

