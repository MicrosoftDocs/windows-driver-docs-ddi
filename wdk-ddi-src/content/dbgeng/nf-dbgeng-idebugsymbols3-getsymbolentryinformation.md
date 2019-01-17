---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryInformation
title: IDebugSymbols3::GetSymbolEntryInformation
description: The GetSymbolEntryInformation method returns the symbol entry information for a symbol.
old-location: debugger\getsymbolentryinformation.htm
tech.root: debugger
ms.assetid: 02fe418f-1793-4585-9891-1274a4ddba74
ms.date: 05/03/2018
ms.keywords: GetSymbolEntryInformation, GetSymbolEntryInformation method [Windows Debugging], GetSymbolEntryInformation method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSymbolEntryInformation method, IDebugSymbols3.GetSymbolEntryInformation, IDebugSymbols3::GetSymbolEntryInformation, IDebugSymbols_a1ac4d9f-172c-4697-937d-a59c88bb8778.xml, dbgeng/IDebugSymbols3::GetSymbolEntryInformation, debugger.getsymbolentryinformation
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugSymbols3.GetSymbolEntryInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSymbolEntryInformation


## -description


The <b>GetSymbolEntryInformation</b> method returns the symbol entry information for a symbol.


## -parameters




### -param Id [in]

Specifies the module and symbol ID of the desired symbol.  For details on this structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541511">DEBUG_MODULE_AND_ID</a>.


### -param Info [out]

Receives the symbol entry information for the symbol.  For details on this structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541662">DEBUG_SYMBOL_ENTRY</a>.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



For details on the symbol entry information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/ee8ea970-04ee-4bf5-9e81-7d5baf0eac0d">IdebugSymbolGroup2::GetSymbolEntryInformation</a>
 

 

