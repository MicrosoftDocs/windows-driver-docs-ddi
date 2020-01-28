---
UID: NF:dbgeng.IDebugSymbols3.AppendSymbolPathWide
title: IDebugSymbols3::AppendSymbolPathWide (dbgeng.h)
description: The AppendSymbolPathWide method appends directories to the symbol path.
old-location: debugger\appendsymbolpathwide.htm
tech.root: debugger
ms.assetid: 184f40ff-be43-482c-8620-382f11f95548
ms.date: 05/03/2018
ms.keywords: AppendSymbolPathWide, AppendSymbolPathWide method [Windows Debugging], AppendSymbolPathWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],AppendSymbolPathWide method, IDebugSymbols3.AppendSymbolPathWide, IDebugSymbols3::AppendSymbolPathWide, dbgeng/IDebugSymbols3::AppendSymbolPathWide, debugger.appendsymbolpathwide
f1_keywords:
 - "dbgeng/IDebugSymbols3.AppendSymbolPathWide"
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
- Dbgeng.h
api_name:
- IDebugSymbols3.AppendSymbolPathWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::AppendSymbolPathWide


## -description


The <b>AppendSymbolPathWide</b>  method appends directories to the symbol path.


## -parameters




### -param Addition [in]

Specifies the directories to append to the symbol path.  This is a string that contains symbol path elements separated by semicolons (;).  Each symbol path element can specify either a directory or a symbol server.


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
</table>
 

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



For more information about manipulating the symbol path, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-symbols">Using Symbols</a>.  For an overview of the symbol path and its syntax, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbol-path">Symbol Path</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolpath">GetSymbolPath</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-setsymbolpath">SetSymbolPath</a>
 

 

