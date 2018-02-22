---
UID: NF:dbgeng.IDebugSymbols.AddSymbolOptions
title: IDebugSymbols::AddSymbolOptions method
author: windows-driver-content
description: The AddSymbolOptions method turns on some of the engine's global symbol options.
old-location: debugger\addsymboloptions.htm
old-project: Debugger
ms.assetid: 952b4a7b-2713-4d7a-b70e-4fd1867bc096
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugSymbols3 interface [Windows Debugging], AddSymbolOptions method, IDebugSymbols::AddSymbolOptions, IDebugSymbols2::AddSymbolOptions, dbgeng/IDebugSymbols3::AddSymbolOptions, AddSymbolOptions, IDebugSymbols interface [Windows Debugging], AddSymbolOptions method, IDebugSymbols3::AddSymbolOptions, AddSymbolOptions method [Windows Debugging], IDebugSymbols3 interface, AddSymbolOptions method [Windows Debugging], dbgeng/IDebugSymbols::AddSymbolOptions, AddSymbolOptions method [Windows Debugging], IDebugSymbols2 interface, AddSymbolOptions method [Windows Debugging], IDebugSymbols interface, debugger.addsymboloptions, IDebugSymbols2 interface [Windows Debugging], AddSymbolOptions method, IDebugSymbols_a7ffc5ae-fc9e-4298-a351-95871b8fd12e.xml, IDebugSymbols, dbgeng/IDebugSymbols2::AddSymbolOptions
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Dbgeng.h
apiname:
-	IDebugSymbols.AddSymbolOptions
-	IDebugSymbols2.AddSymbolOptions
-	IDebugSymbols3.AddSymbolOptions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols::AddSymbolOptions method


## -description


The <b>AddSymbolOptions</b> method turns on some of the engine's global symbol options.


## -syntax


````
HRESULT AddSymbolOptions(
  [in] PULONG Options
);
````


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



After the symbol options have been changed, for each client the engine sends out notification to that client's <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> by passing the DEBUG_CES_SYMBOL_OPTIONS flag to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550692">IDebugEventCallbacks::ChangeSymbolState</a> method.

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554535">RemoveSymbolOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556798">SetSymbolOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549139">GetSymbolOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugSymbols::AddSymbolOptions method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

