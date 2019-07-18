---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolSize
title: IDebugSymbolGroup2::GetSymbolSize (dbgeng.h)
description: The GetSymbolSize method returns the size of a symbol's value.
old-location: debugger\getsymbolsize.htm
tech.root: debugger
ms.assetid: f35bbbeb-585b-47b0-ae36-bd37fe9e1bbc
ms.date: 05/03/2018
ms.keywords: ComOther_a6e69468-38f9-449d-9bd7-0ef52585f2aa.xml, GetSymbolSize, GetSymbolSize method [Windows Debugging], GetSymbolSize method [Windows Debugging],IDebugSymbolGroup2 interface, IDebugSymbolGroup2 interface [Windows Debugging],GetSymbolSize method, IDebugSymbolGroup2.GetSymbolSize, IDebugSymbolGroup2::GetSymbolSize, dbgeng/IDebugSymbolGroup2::GetSymbolSize, debugger.getsymbolsize
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugSymbolGroup2.GetSymbolSize"
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
- IDebugSymbolGroup2.GetSymbolSize
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2::GetSymbolSize


## -description


The <b>GetSymbolSize</b> method returns the size of a symbol's value.


## -parameters




### -param Index [in]

The index of the symbol to remove. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


### -param Size [out]

The size, in bytes, of the symbol's value. This information might not be available. If this information is not available, <i>Size</i> is set to zero.  For some symbols (for example, a function's code), the data might be split over multiple regions. In this situation, <i>Size</i> is not meaningful.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The symbol does not have type data associated with it.

</td>
</tr>
</table>
 

This method can also return other error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



For more information about symbol groups, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-gettypesize">IDebugSymbols::GetTypeSize</a>
 

 

