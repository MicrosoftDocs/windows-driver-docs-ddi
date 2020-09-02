---
UID: NF:dbgeng.IDebugControl4.GetTextMacroWide
title: IDebugControl4::GetTextMacroWide (dbgeng.h)
description: The GetTextMacroWide method returns the value of a fixed-name alias.
old-location: debugger\gettextmacrowide.htm
tech.root: debugger
ms.assetid: 5b125041-969e-49bb-96d5-b40cc7285315
ms.date: 05/03/2018
keywords: ["IDebugControl4::GetTextMacroWide"]
ms.keywords: GetTextMacroWide, GetTextMacroWide method [Windows Debugging], GetTextMacroWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetTextMacroWide method, IDebugControl4.GetTextMacroWide, IDebugControl4::GetTextMacroWide, dbgeng/IDebugControl4::GetTextMacroWide, debugger.gettextmacrowide
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
 - IDebugControl4::GetTextMacroWide
 - dbgeng/IDebugControl4::GetTextMacroWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl4.GetTextMacroWide
---

# IDebugControl4::GetTextMacroWide


## -description

The <b>GetTextMacroWide</b> method returns the value of a fixed-name alias.

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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-settextmacro">SetTextMacro</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/r--registers-">r (Registers)</a>

