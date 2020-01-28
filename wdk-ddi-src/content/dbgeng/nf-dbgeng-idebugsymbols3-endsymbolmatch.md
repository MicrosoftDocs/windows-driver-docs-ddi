---
UID: NF:dbgeng.IDebugSymbols3.EndSymbolMatch
title: IDebugSymbols3::EndSymbolMatch (dbgeng.h)
description: The EndSymbolMatch method releases the resources used by a symbol search.
old-location: debugger\endsymbolmatch.htm
tech.root: debugger
ms.assetid: 02cc9db2-173a-4d5d-a465-098391336100
ms.date: 05/03/2018
ms.keywords: EndSymbolMatch, EndSymbolMatch method [Windows Debugging], EndSymbolMatch method [Windows Debugging],IDebugSymbols interface, EndSymbolMatch method [Windows Debugging],IDebugSymbols2 interface, EndSymbolMatch method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],EndSymbolMatch method, IDebugSymbols2 interface [Windows Debugging],EndSymbolMatch method, IDebugSymbols2::EndSymbolMatch, IDebugSymbols3 interface [Windows Debugging],EndSymbolMatch method, IDebugSymbols3.EndSymbolMatch, IDebugSymbols3::EndSymbolMatch, IDebugSymbols::EndSymbolMatch, IDebugSymbols_1661cc8a-ad5c-4cd3-83fe-f829bd07e453.xml, dbgeng/IDebugSymbols2::EndSymbolMatch, dbgeng/IDebugSymbols3::EndSymbolMatch, dbgeng/IDebugSymbols::EndSymbolMatch, debugger.endsymbolmatch
f1_keywords:
 - "dbgeng/IDebugSymbols.EndSymbolMatch"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugSymbols.EndSymbolMatch
- IDebugSymbols2.EndSymbolMatch
- IDebugSymbols3.EndSymbolMatch
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::EndSymbolMatch


## -description


The <b>EndSymbolMatch</b> method releases the resources used by a symbol search.


## -parameters




### -param Handle [in]

Specifies the handle returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-startsymbolmatch">StartSymbolMatch</a> when the search was initialized.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
 




## -remarks



This method releases the resources held by the engine during a symbol search.  After these resources are released, the handle becomes invalid, so it must not be passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getnextsymbolmatch">GetNextSymbolMatch</a> after it has been passed to this method.

For more information about symbols, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">Symbols</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getnextsymbolmatch">GetNextSymbolMatch</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-startsymbolmatch">StartSymbolMatch</a>
 

 

