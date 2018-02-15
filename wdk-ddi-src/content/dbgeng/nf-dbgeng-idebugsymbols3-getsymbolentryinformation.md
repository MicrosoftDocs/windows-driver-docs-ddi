---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryInformation
title: IDebugSymbols3::GetSymbolEntryInformation method
author: windows-driver-content
description: The GetSymbolEntryInformation method returns the symbol entry information for a symbol.
old-location: debugger\getsymbolentryinformation.htm
old-project: debugger
ms.assetid: 02fe418f-1793-4585-9891-1274a4ddba74
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.getsymbolentryinformation, IDebugSymbols_a1ac4d9f-172c-4697-937d-a59c88bb8778.xml, GetSymbolEntryInformation method [Windows Debugging], GetSymbolEntryInformation method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging], GetSymbolEntryInformation method, IDebugSymbols3::GetSymbolEntryInformation, GetSymbolEntryInformation, IDebugSymbols3, dbgeng/IDebugSymbols3::GetSymbolEntryInformation
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSymbols3.GetSymbolEntryInformation
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSymbols3::GetSymbolEntryInformation method


## -description


The <b>GetSymbolEntryInformation</b> method returns the symbol entry information for a symbol.


## -syntax


````
HRESULT GetSymbolEntryInformation(
  [in]  PDEBUG_MODULE_AND_ID Id,
  [out] PDEBUG_SYMBOL_ENTRY  Info
);
````


## -parameters




### -param Id [in]

Specifies the module and symbol ID of the desired symbol.  For details on this structure, see <a href="..\dbgeng\ns-dbgeng-_debug_module_and_id.md">DEBUG_MODULE_AND_ID</a>.


### -param Info [out]

Receives the symbol entry information for the symbol.  For details on this structure, see <a href="..\dbgeng\ns-dbgeng-_debug_symbol_entry.md">DEBUG_SYMBOL_ENTRY</a>.


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

<a href="https://msdn.microsoft.com/ee8ea970-04ee-4bf5-9e81-7d5baf0eac0d">IdebugSymbolGroup2::GetSymbolEntryInformation</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSymbolEntryInformation method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

