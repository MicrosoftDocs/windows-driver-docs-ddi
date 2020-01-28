---
UID: NF:dbgeng.IDebugSymbols2.GetSymbolTypeId
title: IDebugSymbols2::GetSymbolTypeId (dbgeng.h)
description: The GetSymbolTypeId method returns the type ID and module of the specified symbol.
old-location: debugger\getsymboltypeid.htm
tech.root: debugger
ms.assetid: 0c77ad1a-218d-4857-a07c-f5d542d070d7
ms.date: 05/03/2018
ms.keywords: GetSymbolTypeId, GetSymbolTypeId method [Windows Debugging], GetSymbolTypeId method [Windows Debugging],IDebugSymbols interface, GetSymbolTypeId method [Windows Debugging],IDebugSymbols2 interface, GetSymbolTypeId method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetSymbolTypeId method, IDebugSymbols2 interface [Windows Debugging],GetSymbolTypeId method, IDebugSymbols2.GetSymbolTypeId, IDebugSymbols2::GetSymbolTypeId, IDebugSymbols3 interface [Windows Debugging],GetSymbolTypeId method, IDebugSymbols3::GetSymbolTypeId, IDebugSymbols::GetSymbolTypeId, IDebugSymbols_c62a5150-7e20-4217-8fb8-667cbd93042a.xml, dbgeng/IDebugSymbols2::GetSymbolTypeId, dbgeng/IDebugSymbols3::GetSymbolTypeId, dbgeng/IDebugSymbols::GetSymbolTypeId, debugger.getsymboltypeid
f1_keywords:
 - "dbgeng/IDebugSymbols.GetSymbolTypeId"
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
- IDebugSymbols.GetSymbolTypeId
- IDebugSymbols2.GetSymbolTypeId
- IDebugSymbols3.GetSymbolTypeId
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols2::GetSymbolTypeId


## -description


The <b>GetSymbolTypeId</b>  method returns the type ID and module of the specified symbol.


## -parameters




### -param Symbol [in]

Specifies the expression whose type ID is requested.  See the Remarks section for details on the syntax of this expression.


### -param TypeId [out]

Receives the type ID.


### -param Module [out, optional]

Receives the base address of the module containing the symbol.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">Modules</a>.  If <i>Module</i> is <b>NULL</b>, this information is not returned.


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
The method was successful

</td>
</tr>
</table>
 




## -remarks



The Sy<i></i>mbol expression may contain structure fields, pointer dereferencing, and array dereferencing -- for example <b>my_struct.some_field[0]</b>.

For more information about symbols, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">Symbols</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsymboltypeid">GetSymbolTypeId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-gettypeid">GetTypeId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

