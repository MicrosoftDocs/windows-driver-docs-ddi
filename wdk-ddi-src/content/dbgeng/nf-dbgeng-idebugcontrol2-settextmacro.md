---
UID: NF:dbgeng.IDebugControl2.SetTextMacro
title: IDebugControl2::SetTextMacro (dbgeng.h)
description: The SetTextMacro method sets the value of a fixed-name alias.
old-location: debugger\settextmacro.htm
tech.root: debugger
ms.assetid: 8319ab12-bb23-4de4-b3dc-afd3cd13d03e
ms.date: 05/03/2018
keywords: ["IDebugControl2::SetTextMacro"]
ms.keywords: IDebugControl interface [Windows Debugging],SetTextMacro method, IDebugControl2 interface [Windows Debugging],SetTextMacro method, IDebugControl2.SetTextMacro, IDebugControl2::SetTextMacro, IDebugControl3 interface [Windows Debugging],SetTextMacro method, IDebugControl3::SetTextMacro, IDebugControl::SetTextMacro, IDebugControl_5eac09ea-004d-4231-b865-d191790880fc.xml, SetTextMacro, SetTextMacro method [Windows Debugging], SetTextMacro method [Windows Debugging],IDebugControl interface, SetTextMacro method [Windows Debugging],IDebugControl2 interface, SetTextMacro method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetTextMacro, dbgeng/IDebugControl3::SetTextMacro, dbgeng/IDebugControl::SetTextMacro, debugger.settextmacro
f1_keywords:
 - "dbgeng/IDebugControl.SetTextMacro"
 - "IDebugControl.SetTextMacro"
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
- IDebugControl.SetTextMacro
- IDebugControl2.SetTextMacro
- IDebugControl3.SetTextMacro
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::SetTextMacro


## -description


The <b>SetTextMacro</b>  method sets the value of a fixed-name alias.


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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removetextreplacements">RemoveTextReplacements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-settextreplacement">SetTextReplacement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/r--registers-">r (Registers)</a>
 

 

