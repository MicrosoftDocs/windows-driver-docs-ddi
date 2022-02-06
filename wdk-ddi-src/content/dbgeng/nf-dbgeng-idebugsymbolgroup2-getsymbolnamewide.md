---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolNameWide
title: IDebugSymbolGroup2::GetSymbolNameWide (dbgeng.h)
description: The GetSymbolNameWide method returns the name of a symbol in a symbol group.
old-location: debugger\getsymbolnamewide.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugSymbolGroup2::GetSymbolNameWide"]
ms.keywords: GetSymbolNameWide, GetSymbolNameWide method [Windows Debugging], GetSymbolNameWide method [Windows Debugging],IDebugSymbolGroup2 interface, IDebugSymbolGroup2 interface [Windows Debugging],GetSymbolNameWide method, IDebugSymbolGroup2.GetSymbolNameWide, IDebugSymbolGroup2::GetSymbolNameWide, dbgeng/IDebugSymbolGroup2::GetSymbolNameWide, debugger.getsymbolnamewide
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
 - IDebugSymbolGroup2::GetSymbolNameWide
 - dbgeng/IDebugSymbolGroup2::GetSymbolNameWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbolGroup2::GetSymbolNameWide
---

# IDebugSymbolGroup2::GetSymbolNameWide


## -description

The <b>GetSymbolNameWide</b> method returns the name of a symbol in a symbol group.

## -parameters

### -param Index [in]


The index of the symbol whose name you want.  The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.

### -param Buffer [out, optional]


The symbol name.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize [in]


The size of the buffer that <i>Buffer </i>points to. This size includes the space for the '\0' terminating character.

### -param NameSize [out, optional]


The size of the symbol name. This size includes the space for the '\0' terminating character. If <i>NameSize</i> is <b>NULL</b>, this information is not returned.

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
The method was successful. However, the name of the symbol did not fit in the buffer referred to by the <i>Buffer</i> parameter, so a truncated name was returned.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

## -remarks

For more information about symbol groups, see <a href="/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>

