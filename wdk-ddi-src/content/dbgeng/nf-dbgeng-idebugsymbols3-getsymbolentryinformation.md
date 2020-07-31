---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryInformation
title: IDebugSymbols3::GetSymbolEntryInformation (dbgeng.h)
description: The GetSymbolEntryInformation method returns the symbol entry information for a symbol.
old-location: debugger\getsymbolentryinformation.htm
tech.root: debugger
ms.assetid: 02fe418f-1793-4585-9891-1274a4ddba74
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetSymbolEntryInformation"]
ms.keywords: GetSymbolEntryInformation, GetSymbolEntryInformation method [Windows Debugging], GetSymbolEntryInformation method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSymbolEntryInformation method, IDebugSymbols3.GetSymbolEntryInformation, IDebugSymbols3::GetSymbolEntryInformation, IDebugSymbols_a1ac4d9f-172c-4697-937d-a59c88bb8778.xml, dbgeng/IDebugSymbols3::GetSymbolEntryInformation, debugger.getsymbolentryinformation
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetSymbolEntryInformation"
 - "IDebugSymbols3.GetSymbolEntryInformation"
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
- IDebugSymbols3.GetSymbolEntryInformation
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSymbolEntryInformation


## -description


The <b>GetSymbolEntryInformation</b> method returns the symbol entry information for a symbol.


## -parameters




### -param Id [in]

Specifies the module and symbol ID of the desired symbol.  For details on this structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_module_and_id">DEBUG_MODULE_AND_ID</a>.


### -param Info [out]

Receives the symbol entry information for the symbol.  For details on this structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_entry">DEBUG_SYMBOL_ENTRY</a>.


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



For details on the symbol entry information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymbolentryinformation">IdebugSymbolGroup2::GetSymbolEntryInformation</a>
 

 

