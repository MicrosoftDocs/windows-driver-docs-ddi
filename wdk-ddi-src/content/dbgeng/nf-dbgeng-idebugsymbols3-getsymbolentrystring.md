---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryString
title: IDebugSymbols3::GetSymbolEntryString
author: windows-driver-content
description: The GetSymbolEntryString method returns string information for the specified symbol.
old-location: debugger\getsymbolentrystring.htm
old-project: debugger
ms.assetid: 3ec46b53-f3a8-4fd6-bf94-261ff8accad7
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetSymbolEntryString, GetSymbolEntryString method [Windows Debugging], GetSymbolEntryString method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSymbolEntryString method, IDebugSymbols3.GetSymbolEntryString, IDebugSymbols3::GetSymbolEntryString, IDebugSymbols_cf31d6c1-ffc6-4112-af04-dc023635bb5a.xml, dbgeng/IDebugSymbols3::GetSymbolEntryString, debugger.getsymbolentrystring
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IDebugSymbols3.GetSymbolEntryString
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSymbolEntryString


## -description


The <b>GetSymbolEntryString</b>  method returns string information for the specified symbol.


## -parameters




### -param Id [in]

Specifies the symbols whose memory regions are being requested.  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff541511">DEBUG_MODULE_AND_ID</a> structure contains the module containing the symbol and the symbol ID of the symbol within the module.


### -param Which [in]

Specifies the index of the desired string.  Often this is zero, as most symbols contain just one string (their name).  But some symbols may contain more than one string -- for example, annotation symbols.


### -param Buffer [out, optional]

Receives the name of the symbol.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size in characters of the buffer <i>Buffer</i>.


### -param StringSize [out, optional]

Receives the size in characters of the symbol's name.  If <i>StringSize</i> is <b>NULL</b>, this information is not returned.


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



For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548458">GetSymbolEntriesByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548476">GetSymbolEntriesByOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

