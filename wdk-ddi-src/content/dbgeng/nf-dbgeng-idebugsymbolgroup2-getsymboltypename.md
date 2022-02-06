---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolTypeName
title: IDebugSymbolGroup2::GetSymbolTypeName (dbgeng.h)
description: The GetSymbolTypeName methods return the name of the specified symbol's type.
old-location: debugger\getsymboltypename.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugSymbolGroup2::GetSymbolTypeName"]
ms.keywords: ComOther_27d4a23e-4566-4b37-a692-2b82310ae8e9.xml, GetSymbolTypeName, GetSymbolTypeName method [Windows Debugging], GetSymbolTypeName method [Windows Debugging],IDebugSymbolGroup2 interface, IDebugSymbolGroup2 interface [Windows Debugging],GetSymbolTypeName method, IDebugSymbolGroup2.GetSymbolTypeName, IDebugSymbolGroup2::GetSymbolTypeName, dbgeng/IDebugSymbolGroup2::GetSymbolTypeName, debugger.getsymboltypename
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
 - IDebugSymbolGroup2::GetSymbolTypeName
 - dbgeng/IDebugSymbolGroup2::GetSymbolTypeName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbolGroup2::GetSymbolTypeName
---

# IDebugSymbolGroup2::GetSymbolTypeName


## -description

The <b>GetSymbolTypeName</b>  methods return the name of the specified symbol's type.

## -parameters

### -param Index [in]


The index of the symbol whose type name you want. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.

### -param Buffer [out, optional]


The name of the symbol's type.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize [in]


The size, in characters, of the <i>Buffer</i> buffer. This size includes the space for the '\0' terminating character.

### -param NameSize [out, optional]


The size, in characters, of the name of the symbol's type. This size includes the space for the '\0' terminating character. If <i>NameSize</i> is <b>NULL</b>, this information is not returned.

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
The size of the buffer was smaller than the size of the name of the symbol's type. The buffer is filled with the truncated name.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

## -remarks

For more information about symbol groups, see <a href="/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-gettypename">IDebugSymbols::GetTypeName</a>

