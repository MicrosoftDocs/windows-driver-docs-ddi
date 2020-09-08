---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolValueText
title: IDebugSymbolGroup2::GetSymbolValueText (dbgeng.h)
description: The GetSymbolValueText method returns a string that represents the value of a symbol.
old-location: debugger\getsymbolvaluetext.htm
tech.root: debugger
ms.assetid: 587b8769-86b6-48bd-b238-84aeb5611668
ms.date: 05/03/2018
keywords: ["IDebugSymbolGroup2::GetSymbolValueText"]
ms.keywords: ComOther_2a064ea0-63f4-441f-a79c-e6fc1e9688c7.xml, GetSymbolValueText, GetSymbolValueText method [Windows Debugging], GetSymbolValueText method [Windows Debugging],IDebugSymbolGroup2 interface, IDebugSymbolGroup2 interface [Windows Debugging],GetSymbolValueText method, IDebugSymbolGroup2.GetSymbolValueText, IDebugSymbolGroup2::GetSymbolValueText, dbgeng/IDebugSymbolGroup2::GetSymbolValueText, debugger.getsymbolvaluetext
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugSymbolGroup2::GetSymbolValueText
 - dbgeng/IDebugSymbolGroup2::GetSymbolValueText
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbolGroup2.GetSymbolValueText
---

# IDebugSymbolGroup2::GetSymbolValueText


## -description

The <b>GetSymbolValueText</b>  method returns a string that represents the value of a symbol.

## -parameters

### -param Index 

[in]
The index of the symbol whose value you want.  The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.

### -param Buffer 

[out, optional]
The value of the symbol as a string.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize 

[in]
The size, in characters, of the <i>Buffer </i>buffer.

### -param NameSize 

[out, optional]
The size, in characters, of the value of the symbol.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.

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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, the value of the symbol would not fit in the buffer referred to by the <i>Buffer</i> parameter, so a truncated value was returned.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

## -remarks

If you added the symbol to the symbol group by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-addsymbol">AddSymbol</a> method, the string that is returned to <i>Buffer</i> is the name of the symbol that is passed to <b>AddSymbol</b>.

For more information about symbol groups, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-writesymbol">WriteSymbol</a>

