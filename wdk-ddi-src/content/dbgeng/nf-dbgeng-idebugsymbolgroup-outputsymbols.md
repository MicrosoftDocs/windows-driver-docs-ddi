---
UID: NF:dbgeng.IDebugSymbolGroup.OutputSymbols
title: IDebugSymbolGroup::OutputSymbols method
author: windows-driver-content
description: The OutputSymbols method prints the specified symbols to the debugger console.
old-location: debugger\outputsymbols.htm
old-project: debugger
ms.assetid: 1fe99cc4-35d9-432a-aed9-074d40438976
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: ComOther_47d8529f-4fdf-4a79-ae80-61e483c897f2.xml, IDebugSymbolGroup, IDebugSymbolGroup interface [Windows Debugging], OutputSymbols method, IDebugSymbolGroup2 interface [Windows Debugging], OutputSymbols method, IDebugSymbolGroup2::OutputSymbols, IDebugSymbolGroup::OutputSymbols, OutputSymbols method [Windows Debugging], OutputSymbols method [Windows Debugging], IDebugSymbolGroup interface, OutputSymbols method [Windows Debugging], IDebugSymbolGroup2 interface, OutputSymbols,IDebugSymbolGroup.OutputSymbols, dbgeng/IDebugSymbolGroup2::OutputSymbols, dbgeng/IDebugSymbolGroup::OutputSymbols, debugger.outputsymbols
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
-	IDebugSymbolGroup.OutputSymbols
-	IDebugSymbolGroup2.OutputSymbols
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbolGroup::OutputSymbols method


## -description


The <b>OutputSymbols</b> method prints the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">symbols</a> to the debugger console.


## -parameters




### -param OutputControl [in]

The output control to use when printing the symbols' information.  For more information about possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.  For more information about output, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.


### -param Flags [in]

The flags that determine what information is printed for each symbol.  By default, the output includes the symbol's name, offset, value, and type.  The format for the output is as follows:

<code>Name**NAME**Offset**OFF**Value**VALUE**Type**TYPE**</code>

You can use the following bit flags to suppress the output of one of these pieces of information together with the corresponding marker.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_OUTPUT_SYMBOLS_NO_NAMES

</td>
<td>
Suppress output of the symbol's name.

</td>
</tr>
<tr>
<td>
DEBUG_OUTPUT_SYMBOLS_NO_OFFSETS

</td>
<td>
Suppress output of the symbol's offset.

</td>
</tr>
<tr>
<td>
DEBUG_OUTPUT_SYMBOLS_NO_VALUES

</td>
<td>
Suppress output of the symbol's value.

</td>
</tr>
<tr>
<td>
DEBUG_OUTPUT_SYMBOLS_NO_TYPES

</td>
<td>
Suppress output of the symbol's type.

</td>
</tr>
</table>
 


### -param Start [in]

The index of the first symbol in the symbol group to print.  The index of a symbol is an identification number. This number ranges from zero through the number of symbols in the symbol group minus one.


### -param Count [in]

The number of symbols to print.


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
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.




## -remarks



For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550838">IDebugSymbolGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550846">IDebugSymbolGroup2</a>
 

 

