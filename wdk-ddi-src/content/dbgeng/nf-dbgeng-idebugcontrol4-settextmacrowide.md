---
UID: NF:dbgeng.IDebugControl4.SetTextMacroWide
title: IDebugControl4::SetTextMacroWide (dbgeng.h)
description: The SetTextMacroWide method sets the value of a fixed-name alias.
old-location: debugger\settextmacrowide.htm
tech.root: debugger
ms.assetid: 98e93636-33e3-4642-a4fb-8590a7a0e784
ms.date: 05/03/2018
keywords: ["IDebugControl4::SetTextMacroWide"]
ms.keywords: IDebugControl4 interface [Windows Debugging],SetTextMacroWide method, IDebugControl4.SetTextMacroWide, IDebugControl4::SetTextMacroWide, SetTextMacroWide, SetTextMacroWide method [Windows Debugging], SetTextMacroWide method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::SetTextMacroWide, debugger.settextmacrowide
f1_keywords:
 - "dbgeng/IDebugControl4.SetTextMacroWide"
 - "IDebugControl4.SetTextMacroWide"
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
- IDebugControl4.SetTextMacroWide
targetos: Windows
req.typenames: 
---

# IDebugControl4::SetTextMacroWide


## -description


The <b>SetTextMacroWide</b>  method sets the value of a fixed-name alias.


## -parameters




### -param Slot [in]

Specifies the number of the fixed-name alias.  <i>Slot</i> can take the values 0, 1, ..., 9, that represent the fixed-name aliases <b>$u0</b>, <b>$u1</b>, ..., <b>$u9</b>.


### -param Macro [in]

Specifies the new value of the alias specified by <i>Slot</i>.  The <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a> makes a copy of this string.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



Before executing commands or evaluating expressions, the debugger engine will replace the alias specified by <i>Slot</i> with the value of the alias (specified by <i>Macro</i>).

For an overview of aliases used by the debugger engine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-aliases">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/interacting-with-the-engine">Interacting with the Engine</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-gettextmacro">GetTextMacro</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removetextreplacements">RemoveTextReplacements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-settextreplacement">SetTextReplacement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/r--registers-">r (Registers)</a>
 

 

