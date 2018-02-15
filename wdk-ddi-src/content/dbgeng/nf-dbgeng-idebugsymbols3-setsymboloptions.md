---
UID: NF:dbgeng.IDebugSymbols3.SetSymbolOptions
title: IDebugSymbols3::SetSymbolOptions method
author: windows-driver-content
description: The SetSymbolOptions method changes the engine's global symbol options.
old-location: debugger\setsymboloptions.htm
old-project: debugger
ms.assetid: 06cfae40-eb32-4f9b-b7ad-266cb12f4a32
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSymbols2 interface [Windows Debugging], SetSymbolOptions method, SetSymbolOptions method [Windows Debugging], IDebugSymbols2 interface, IDebugSymbols2::SetSymbolOptions, SetSymbolOptions method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging], SetSymbolOptions method, IDebugSymbols3::SetSymbolOptions, dbgeng/IDebugSymbols2::SetSymbolOptions, IDebugSymbols_56cfcd8d-304b-4433-beab-2fc3e58a54a4.xml, IDebugSymbols2, IDebugSymbols3, IDebugSymbols::SetSymbolOptions, debugger.setsymboloptions, dbgeng/IDebugSymbols::SetSymbolOptions, IDebugSymbols3 interface [Windows Debugging], SetSymbolOptions method, dbgeng/IDebugSymbols3::SetSymbolOptions, IDebugSymbols, SetSymbolOptions, SetSymbolOptions method [Windows Debugging], IDebugSymbols interface, SetSymbolOptions method [Windows Debugging]
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
-	dbgeng.h
apiname:
-	IDebugSymbols.SetSymbolOptions
-	IDebugSymbols2.SetSymbolOptions
-	IDebugSymbols3.SetSymbolOptions
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSymbols3::SetSymbolOptions method


## -description


The <b>SetSymbolOptions</b> method changes the engine's global symbol options.


## -syntax


````
HRESULT SetSymbolOptions(
  [in] ULONG Options
);
````


## -parameters




### -param Options [in]

Specifies the new symbol options.  <i>Options</i> is a bit-set; it will replace the existing symbol options.  For a description of the bit flags, see <a href="https://msdn.microsoft.com/4a501ea3-431c-4c11-8826-154eb8799a64">Setting Symbol Options</a>.


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



This method will set the engine's global symbol options to those specified in <i>Options</i>.  Unlike <a href="https://msdn.microsoft.com/library/windows/hardware/ff537930">AddSymbolOptions</a>, any symbol options not in the bit-set <i>Options</i> will be removed.

After the symbol options have been changed, for each client the engine sends out notification to that client's <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> by passing the DEBUG_CES_SYMBOL_OPTIONS flag to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550692">IDebugEventCallbacks::ChangeSymbolState</a> method.

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549139">GetSymbolOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554535">RemoveSymbolOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537930">AddSymbolOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::SetSymbolOptions method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

