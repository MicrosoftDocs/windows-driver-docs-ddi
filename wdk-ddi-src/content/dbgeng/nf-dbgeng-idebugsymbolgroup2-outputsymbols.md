---
UID: NF:dbgeng.IDebugSymbolGroup2.OutputSymbols
title: IDebugSymbolGroup2::OutputSymbols (dbgeng.h)
description: The OutputSymbols method prints the specified symbols to the debugger console.
old-location: debugger\outputsymbols.htm
tech.root: debugger
ms.assetid: 1fe99cc4-35d9-432a-aed9-074d40438976
ms.date: 05/03/2018
keywords: ["IDebugSymbolGroup2::OutputSymbols"]
ms.keywords: ComOther_47d8529f-4fdf-4a79-ae80-61e483c897f2.xml, IDebugSymbolGroup interface [Windows Debugging],OutputSymbols method, IDebugSymbolGroup2 interface [Windows Debugging],OutputSymbols method, IDebugSymbolGroup2.OutputSymbols, IDebugSymbolGroup2::OutputSymbols, IDebugSymbolGroup::OutputSymbols, OutputSymbols, OutputSymbols method [Windows Debugging], OutputSymbols method [Windows Debugging],IDebugSymbolGroup interface, OutputSymbols method [Windows Debugging],IDebugSymbolGroup2 interface, dbgeng/IDebugSymbolGroup2::OutputSymbols, dbgeng/IDebugSymbolGroup::OutputSymbols, debugger.outputsymbols
f1_keywords:
 - "dbgeng/IDebugSymbolGroup.OutputSymbols"
 - "IDebugSymbolGroup.OutputSymbols"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugSymbolGroup.OutputSymbols
- IDebugSymbolGroup2.OutputSymbols
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2::OutputSymbols


## -description


The <b>OutputSymbols</b> method prints the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">symbols</a> to the debugger console.


## -parameters




### -param OutputControl 
[in]
The output control to use when printing the symbols' information.  For more information about possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.  For more information about output, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/input-and-output">Input and Output</a>.


### -param Flags 
[in]
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
 


### -param Start 
[in]
The index of the first symbol in the symbol group to print.  The index of a symbol is an identification number. This number ranges from zero through the number of symbols in the symbol group minus one.


### -param Count 
[in]
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
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



For more information about symbol groups, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>
 

 

