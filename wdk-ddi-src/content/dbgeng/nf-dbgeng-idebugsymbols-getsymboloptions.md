---
UID: NF:dbgeng.IDebugSymbols.GetSymbolOptions
title: IDebugSymbols::GetSymbolOptions method
author: windows-driver-content
description: The GetSymbolOptions method returns the engine's global symbol options.
old-location: debugger\getsymboloptions.htm
old-project: debugger
ms.assetid: a9da40fa-59b7-4d2b-978f-1785a51eeaed
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, D, G, GetSymbolOptions method [Windows Debugging], GetSymbolOptions method [Windows Debugging], IDebugSymbols interface, GetSymbolOptions method [Windows Debugging], IDebugSymbols2 interface, GetSymbolOptions method [Windows Debugging], IDebugSymbols3 interface, GetSymbolOptions,IDebugSymbols.GetSymbolOptions, I, IDebugSymbols, IDebugSymbols interface [Windows Debugging], GetSymbolOptions method, IDebugSymbols2 interface [Windows Debugging], GetSymbolOptions method, IDebugSymbols2::GetSymbolOptions, IDebugSymbols3 interface [Windows Debugging], GetSymbolOptions method, IDebugSymbols3::GetSymbolOptions, IDebugSymbols::GetSymbolOptions, IDebugSymbols_70c05823-d1a1-4769-8584-e191255c4deb.xml, O, S, b, dbgeng/IDebugSymbols2::GetSymbolOptions, dbgeng/IDebugSymbols3::GetSymbolOptions, dbgeng/IDebugSymbols::GetSymbolOptions, debugger.getsymboloptions, e, g, i, l, m, n, o, p, s, t, u, y"
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
-	IDebugSymbols.GetSymbolOptions
-	IDebugSymbols2.GetSymbolOptions
-	IDebugSymbols3.GetSymbolOptions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols::GetSymbolOptions method


## -description


The <b>GetSymbolOptions</b> method returns the engine's global symbol options.


## -syntax


````
HRESULT GetSymbolOptions(
  [out] PULONG Options
);
````


## -parameters




### -param Options [out]

Receives the symbol options bit-set.  For a description of the bit flags, see <a href="https://msdn.microsoft.com/4a501ea3-431c-4c11-8826-154eb8799a64">Setting Symbol Options</a>.


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

<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554535">RemoveSymbolOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556798">SetSymbolOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537930">AddSymbolOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetSymbolOptions method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

