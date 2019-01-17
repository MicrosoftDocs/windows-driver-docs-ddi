---
UID: NF:dbgeng.IDebugSymbols2.AddSymbolOptions
title: IDebugSymbols2::AddSymbolOptions
description: The AddSymbolOptions method turns on some of the engine's global symbol options.
old-location: debugger\addsymboloptions.htm
tech.root: debugger
ms.assetid: 952b4a7b-2713-4d7a-b70e-4fd1867bc096
ms.date: 05/03/2018
ms.keywords: AddSymbolOptions, AddSymbolOptions method [Windows Debugging], AddSymbolOptions method [Windows Debugging],IDebugSymbols interface, AddSymbolOptions method [Windows Debugging],IDebugSymbols2 interface, AddSymbolOptions method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],AddSymbolOptions method, IDebugSymbols2 interface [Windows Debugging],AddSymbolOptions method, IDebugSymbols2.AddSymbolOptions, IDebugSymbols2::AddSymbolOptions, IDebugSymbols3 interface [Windows Debugging],AddSymbolOptions method, IDebugSymbols3::AddSymbolOptions, IDebugSymbols::AddSymbolOptions, IDebugSymbols_a7ffc5ae-fc9e-4298-a351-95871b8fd12e.xml, dbgeng/IDebugSymbols2::AddSymbolOptions, dbgeng/IDebugSymbols3::AddSymbolOptions, dbgeng/IDebugSymbols::AddSymbolOptions, debugger.addsymboloptions
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
-	Dbgeng.h
api_name:
-	IDebugSymbols.AddSymbolOptions
-	IDebugSymbols2.AddSymbolOptions
-	IDebugSymbols3.AddSymbolOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols2::AddSymbolOptions


## -description


The <b>AddSymbolOptions</b> method turns on some of the engine's global symbol options.


## -parameters




### -param Options [in]

Specifies the symbol options to turns on.  <i>Options</i> is a bit-set that will be ORed with the existing symbol options.  For a description of the bit flags, see <a href="https://msdn.microsoft.com/4a501ea3-431c-4c11-8826-154eb8799a64">Setting Symbol Options</a>.


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



After the symbol options have been changed, for each client the engine sends out notification to that client's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550550">IDebugEventCallbacks</a> by passing the DEBUG_CES_SYMBOL_OPTIONS flag to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550692">IDebugEventCallbacks::ChangeSymbolState</a> method.

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549139">GetSymbolOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554535">RemoveSymbolOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556798">SetSymbolOptions</a>
 

 

