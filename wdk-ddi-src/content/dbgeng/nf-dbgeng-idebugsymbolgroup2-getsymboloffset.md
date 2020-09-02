---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolOffset
title: IDebugSymbolGroup2::GetSymbolOffset (dbgeng.h)
description: The GetSymbolOffset method retrieves the location in the process's virtual address space of a symbol in a symbol group, if the symbol has an absolute address.
old-location: debugger\getsymboloffset.htm
tech.root: debugger
ms.assetid: da3ddebc-109e-43fb-a0e9-fd89d90dbbc7
ms.date: 05/03/2018
keywords: ["IDebugSymbolGroup2::GetSymbolOffset"]
ms.keywords: ComOther_11a91301-541c-4bc3-aa1e-614db8170e03.xml, GetSymbolOffset, GetSymbolOffset method [Windows Debugging], GetSymbolOffset method [Windows Debugging],IDebugSymbolGroup2 interface, IDebugSymbolGroup2 interface [Windows Debugging],GetSymbolOffset method, IDebugSymbolGroup2.GetSymbolOffset, IDebugSymbolGroup2::GetSymbolOffset, dbgeng/IDebugSymbolGroup2::GetSymbolOffset, debugger.getsymboloffset
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
 - IDebugSymbolGroup2::GetSymbolOffset
 - dbgeng/IDebugSymbolGroup2::GetSymbolOffset
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbolGroup2.GetSymbolOffset
---

# IDebugSymbolGroup2::GetSymbolOffset


## -description

The <b>GetSymbolOffset</b> method retrieves the location in the process's virtual address space of a symbol in a symbol group, if the symbol has an absolute address.

## -parameters

### -param Index 

[in]
The index of the symbol whose address you want.  The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.

### -param Offset 

[out]
The location in the process's virtual address space of the symbol.

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
The symbol does not have an absolute address.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

## -remarks

For more information about symbol groups, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>

