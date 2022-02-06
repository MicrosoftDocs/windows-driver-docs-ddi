---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryStringWide
title: IDebugSymbols3::GetSymbolEntryStringWide (dbgeng.h)
description: The GetSymbolEntryStringWide method returns string information for the specified symbol.
old-location: debugger\getsymbolentrystringwide.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugSymbols3::GetSymbolEntryStringWide"]
ms.keywords: GetSymbolEntryStringWide, GetSymbolEntryStringWide method [Windows Debugging], GetSymbolEntryStringWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSymbolEntryStringWide method, IDebugSymbols3.GetSymbolEntryStringWide, IDebugSymbols3::GetSymbolEntryStringWide, dbgeng/IDebugSymbols3::GetSymbolEntryStringWide, debugger.getsymbolentrystringwide
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
 - IDebugSymbols3::GetSymbolEntryStringWide
 - dbgeng/IDebugSymbols3::GetSymbolEntryStringWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3::GetSymbolEntryStringWide
---

# IDebugSymbols3::GetSymbolEntryStringWide


## -description

The <b>GetSymbolEntryStringWide</b>  method returns string information for the specified symbol.

## -parameters

### -param Id [in]


Specifies the symbols whose memory regions are being requested.  The <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_module_and_id">DEBUG_MODULE_AND_ID</a> structure contains the module containing the symbol and the symbol ID of the symbol within the module.

### -param Which [in]


Specifies the index of the desired string.  Often this is zero, as most symbols contain just one string (their name).  But some symbols may contain more than one string -- for example, annotation symbols.

### -param Buffer [out, optional]


Receives the name of the symbol.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize [in]


Specifies the size in characters of the buffer <i>Buffer</i>. This size includes the space for the '\0' terminating character.

### -param StringSize [out, optional]


Receives the size in characters of the symbol's name. This size includes the space for the '\0' terminating character. If <i>StringSize</i> is <b>NULL</b>, this information is not returned.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

For more information about symbols, see <a href="/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolentriesbyname">GetSymbolEntriesByName</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolentriesbyoffset">GetSymbolEntriesByOffset</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>

