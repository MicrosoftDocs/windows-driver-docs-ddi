---
UID: NF:dbgeng.IDebugControl2.GetTextMacro
title: IDebugControl2::GetTextMacro (dbgeng.h)
description: The GetTextMacro method returns the value of a fixed-name alias.
old-location: debugger\gettextmacro.htm
tech.root: debugger
ms.assetid: 980bcf7b-8e4a-4516-ab71-af60a1d8e99c
ms.date: 05/03/2018
keywords: ["IDebugControl2::GetTextMacro"]
ms.keywords: GetTextMacro, GetTextMacro method [Windows Debugging], GetTextMacro method [Windows Debugging],IDebugControl interface, GetTextMacro method [Windows Debugging],IDebugControl2 interface, GetTextMacro method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetTextMacro method, IDebugControl2 interface [Windows Debugging],GetTextMacro method, IDebugControl2.GetTextMacro, IDebugControl2::GetTextMacro, IDebugControl3 interface [Windows Debugging],GetTextMacro method, IDebugControl3::GetTextMacro, IDebugControl::GetTextMacro, IDebugControl_b6408c67-fb45-4a11-94b4-24099f406a8a.xml, dbgeng/IDebugControl2::GetTextMacro, dbgeng/IDebugControl3::GetTextMacro, dbgeng/IDebugControl::GetTextMacro, debugger.gettextmacro
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugControl2::GetTextMacro
 - dbgeng/IDebugControl2::GetTextMacro
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.GetTextMacro
 - IDebugControl2.GetTextMacro
 - IDebugControl3.GetTextMacro
---

# IDebugControl2::GetTextMacro


## -description

The <b>GetTextMacro</b> method returns the value of a fixed-name alias.

## -parameters

### -param Slot 

[in]
Specifies the number of the fixed-name alias.  <i>Slot</i> can take the values 0, 1, ..., 9, that represent the fixed-name aliases <b>$u0</b>, <b>$u1</b>, ..., <b>$u9</b>.

### -param Buffer 

[out, optional]
Receives the value of the alias specified by <i>Slot</i>.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize 

[in]
Specifies the size, in characters, of the <i>Buffer</i> buffer.

### -param MacroSize 

[out, optional]
Receives the size, in characters, of the value of the alias.

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

Before executing commands or evaluating expressions, the debugger engine will replace the alias specified by <i>Slot</i> with the value of the alias (returned to the <i>Buffer</i> buffer).

For an overview of aliases used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-aliases">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/interacting-with-the-engine">Interacting with the Engine</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getnumbertextreplacements">GetNumberTextReplacements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-gettextreplacement">GetTextReplacement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-settextmacro">SetTextMacro</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/r--registers-">r (Registers)</a>

