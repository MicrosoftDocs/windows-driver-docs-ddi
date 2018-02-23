---
UID: NF:dbgeng.IDebugSymbols3.GetNextSymbolMatch
title: IDebugSymbols3::GetNextSymbolMatch method
author: windows-driver-content
description: The GetNextSymbolMatch method returns the next symbol found in a symbol search.
old-location: debugger\getnextsymbolmatch.htm
old-project: debugger
ms.assetid: 0de394a0-9ae8-4ac9-970b-8575bb7dcc99
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: GetNextSymbolMatch method [Windows Debugging], IDebugSymbols interface [Windows Debugging], GetNextSymbolMatch method, dbgeng/IDebugSymbols3::GetNextSymbolMatch, GetNextSymbolMatch method [Windows Debugging], IDebugSymbols2 interface, IDebugSymbols::GetNextSymbolMatch, IDebugSymbols2 interface [Windows Debugging], GetNextSymbolMatch method, dbgeng/IDebugSymbols2::GetNextSymbolMatch, GetNextSymbolMatch method [Windows Debugging], IDebugSymbols interface, dbgeng/IDebugSymbols::GetNextSymbolMatch, IDebugSymbols2::GetNextSymbolMatch, IDebugSymbols3::GetNextSymbolMatch, IDebugSymbols, IDebugSymbols3 interface [Windows Debugging], GetNextSymbolMatch method, IDebugSymbols_9918b348-5b29-4b38-849e-3a36414b773d.xml, GetNextSymbolMatch method [Windows Debugging], IDebugSymbols3 interface, GetNextSymbolMatch, IDebugSymbols3, debugger.getnextsymbolmatch, IDebugSymbols2
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
-	IDebugSymbols.GetNextSymbolMatch
-	IDebugSymbols2.GetNextSymbolMatch
-	IDebugSymbols3.GetNextSymbolMatch
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetNextSymbolMatch method


## -description


The <b>GetNextSymbolMatch</b>  method returns the next symbol found in a symbol search.


## -syntax


````
HRESULT GetNextSymbolMatch(
  [in]            ULONG64  Handle,
  [out, optional] PSTR     Buffer,
  [in]            ULONG    BufferSize,
  [out, optional] PULONG   MatchSize,
  [out, optional] PULONG64 Offset
);
````


## -parameters




### -param Handle [in]

Specifies the handle returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff558815">StartSymbolMatch</a> when the search was initialized.


### -param Buffer [out, optional]

Receives the name of the symbol.  If <i>Buffer</i> is <b>NULL</b>, the same symbol will be returned again next time one of these methods are called (with the same handle); this can be used to determine the size of the name of the symbol.


### -param BufferSize [in]

Specifies the size in characters of the buffer.


### -param MatchSize [out, optional]

Receives the size in characters of the name of the symbol.  If <i>MatchSize</i> is <b>NULL</b>, this information is not returned.


### -param Offset [out, optional]

Receives the location in the target's virtual address space of the symbol.  If <i>Offset</i> is <b>NULL</b>, this information is not returned.


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
The size of the buffer was too small for the name of the symbol, or <i>Buffer</i> was <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No more symbols were found matching the pattern.

</td>
</tr>
</table>
 




## -remarks



The search must first be initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff558815">StartSymbolMatch</a>.  Once all the desired symbols have been found, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543008">EndSymbolMatch</a> can be used to release the resources the engine holds for the search.

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543008">EndSymbolMatch</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558815">StartSymbolMatch</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetNextSymbolMatch method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

