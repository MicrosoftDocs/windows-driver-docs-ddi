---
UID: NF:dbgeng.IDebugSymbols3.RemoveSymbolOptions
title: IDebugSymbols3::RemoveSymbolOptions method
author: windows-driver-content
description: The RemoveSymbolOptions method turns off some of the engine's global symbol options.
old-location: debugger\removesymboloptions.htm
old-project: debugger
ms.assetid: a4e1f579-8056-4e2b-9b90-735c3414abbd
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugSymbols interface [Windows Debugging], RemoveSymbolOptions method, IDebugSymbols2 interface [Windows Debugging], RemoveSymbolOptions method, IDebugSymbols2::RemoveSymbolOptions, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], RemoveSymbolOptions method, IDebugSymbols3::RemoveSymbolOptions, IDebugSymbols::RemoveSymbolOptions, IDebugSymbols_a6b53bc6-23e5-4dae-b3b8-09330e91caba.xml, RemoveSymbolOptions method [Windows Debugging], RemoveSymbolOptions method [Windows Debugging], IDebugSymbols interface, RemoveSymbolOptions method [Windows Debugging], IDebugSymbols2 interface, RemoveSymbolOptions method [Windows Debugging], IDebugSymbols3 interface, RemoveSymbolOptions,IDebugSymbols3.RemoveSymbolOptions, dbgeng/IDebugSymbols2::RemoveSymbolOptions, dbgeng/IDebugSymbols3::RemoveSymbolOptions, dbgeng/IDebugSymbols::RemoveSymbolOptions, debugger.removesymboloptions
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Dbghelp.h
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
-	IDebugSymbols.RemoveSymbolOptions
-	IDebugSymbols2.RemoveSymbolOptions
-	IDebugSymbols3.RemoveSymbolOptions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::RemoveSymbolOptions method


## -description


The <b>RemoveSymbolOptions</b> method turns off some of the engine's global symbol options.


## -syntax


````
HRESULT RemoveSymbolOptions(
  [in] ULONG Options
);
````


## -parameters




### -param Options [in]

Specifies the symbol options to turn off.  <i>Options</i> is a bit-set; the new value of the symbol options will equal the old value AND NOT the value of <i>Options</i>.  For a description of the bit flags, see <a href="https://msdn.microsoft.com/4a501ea3-431c-4c11-8826-154eb8799a64">Setting Symbol Options</a>.


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
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



After the symbol options have been changed, for each client the engine sends out notification to that client's <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> by it passing the DEBUG_CES_SYMBOL_OPTIONS flag to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550692">IDebugEventCallbacks::ChangeSymbolState</a> method.

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556798">SetSymbolOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537930">AddSymbolOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549139">GetSymbolOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



 

 


