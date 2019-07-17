---
UID: NF:dbgeng.IDebugSymbols2.AppendSymbolPath
title: IDebugSymbols2::AppendSymbolPath (dbgeng.h)
description: The AppendSymbolPath method appends directories to the symbol path.
old-location: debugger\appendsymbolpath.htm
tech.root: debugger
ms.assetid: 99a0ded5-2a73-40c9-99f4-82d31395aa62
ms.date: 05/03/2018
ms.keywords: AppendSymbolPath, AppendSymbolPath method [Windows Debugging], AppendSymbolPath method [Windows Debugging],IDebugSymbols interface, AppendSymbolPath method [Windows Debugging],IDebugSymbols2 interface, AppendSymbolPath method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],AppendSymbolPath method, IDebugSymbols2 interface [Windows Debugging],AppendSymbolPath method, IDebugSymbols2.AppendSymbolPath, IDebugSymbols2::AppendSymbolPath, IDebugSymbols3 interface [Windows Debugging],AppendSymbolPath method, IDebugSymbols3::AppendSymbolPath, IDebugSymbols::AppendSymbolPath, IDebugSymbols_cc73a8f6-3cf1-40a1-8cb5-712eeca0b883.xml, dbgeng/IDebugSymbols2::AppendSymbolPath, dbgeng/IDebugSymbols3::AppendSymbolPath, dbgeng/IDebugSymbols::AppendSymbolPath, debugger.appendsymbolpath
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugSymbols.AppendSymbolPath"
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
- IDebugSymbols.AppendSymbolPath
- IDebugSymbols2.AppendSymbolPath
- IDebugSymbols3.AppendSymbolPath
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols2::AppendSymbolPath


## -description


The <b>AppendSymbolPath</b>  method appends directories to the symbol path.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolpath">GetSymbolPath</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setsymbolpath">SetSymbolPath</a>
 

 

