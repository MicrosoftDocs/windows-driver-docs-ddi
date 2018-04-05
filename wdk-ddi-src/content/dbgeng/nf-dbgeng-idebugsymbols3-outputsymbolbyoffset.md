---
UID: NF:dbgeng.IDebugSymbols3.OutputSymbolByOffset
title: IDebugSymbols3::OutputSymbolByOffset method
author: windows-driver-content
description: The OutputSymbolByOffset method looks up a symbol by address and prints the symbol name and other symbol information to the debugger console.
old-location: debugger\outputsymbolbyoffset.htm
old-project: debugger
ms.assetid: a9b3ac31-2001-45cc-a917-de687419b561
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], OutputSymbolByOffset method, IDebugSymbols3::OutputSymbolByOffset, IDebugSymbols_45f0a841-85cf-4be8-82bc-e962b5af2f5d.xml, OutputSymbolByOffset method [Windows Debugging], OutputSymbolByOffset method [Windows Debugging], IDebugSymbols3 interface, OutputSymbolByOffset,IDebugSymbols3.OutputSymbolByOffset, dbgeng/IDebugSymbols3::OutputSymbolByOffset, debugger.outputsymbolbyoffset
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
-	IDebugSymbols3.OutputSymbolByOffset
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::OutputSymbolByOffset method


## -description


The <b>OutputSymbolByOffset</b> method looks up a symbol by address and prints the symbol name and other symbol information to the debugger console.


## -parameters




### -param OutputControl [in]

Specifies where to send the output. For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.


### -param Flags [in]

Specifies the flags used to determine what information is printed with the symbol.

The following flags can be present:

<table>
<tr>
<th>Bit-flag</th>
<th>Effect</th>
</tr>
<tr>
<td>
DEBUG_OUTSYM_FORCE_OFFSET

</td>
<td>
Include the location of the symbol.

</td>
</tr>
<tr>
<td>
DEBUG_OUTSYM_SOURCE_LINE

</td>
<td>
Include the file name and line number of the source file where the symbol is defined.

</td>
</tr>
<tr>
<td>
DEBUG_OUTSYM_ALLOW_DISPLACEMENT

</td>
<td>
Do not require an exact match for the symbols location.

This allows the <i>Offset</i> parameter to specify any address within the symbol's memory allocation - not just the base address.

</td>
</tr>
</table>
 


### -param Offset [in]

Specifies the location in the process's virtual address space of the symbol to be printed.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No symbol was found at the specified location.

</td>
</tr>
</table>
 




## -remarks



For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547183">GetNameByOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

