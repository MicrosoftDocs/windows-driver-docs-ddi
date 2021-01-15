---
UID: NF:dbgeng.IDebugControl2.SetRadix
title: IDebugControl2::SetRadix (dbgeng.h)
description: The SetRadix method sets the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.
old-location: debugger\setradix.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl2::SetRadix"]
ms.keywords: IDebugControl interface [Windows Debugging],SetRadix method, IDebugControl2 interface [Windows Debugging],SetRadix method, IDebugControl2.SetRadix, IDebugControl2::SetRadix, IDebugControl3 interface [Windows Debugging],SetRadix method, IDebugControl3::SetRadix, IDebugControl::SetRadix, IDebugControl_f0462fa8-da93-414b-b4b1-246a50572bb2.xml, SetRadix, SetRadix method [Windows Debugging], SetRadix method [Windows Debugging],IDebugControl interface, SetRadix method [Windows Debugging],IDebugControl2 interface, SetRadix method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetRadix, dbgeng/IDebugControl3::SetRadix, dbgeng/IDebugControl::SetRadix, debugger.setradix
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
 - IDebugControl2::SetRadix
 - dbgeng/IDebugControl2::SetRadix
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl2::SetRadix
---

# IDebugControl2::SetRadix


## -description

The <b>SetRadix</b> method sets the default radix (number base) used by the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a> when it evaluates and displays MASM expressions, and when it displays symbol information.

## -parameters

### -param Radix 

[in]
Specifies the new default radix.  The following table contains the possible values for the radix.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
8

</td>
<td>
Octal

</td>
</tr>
<tr>
<td>
10

</td>
<td>
Decimal

</td>
</tr>
<tr>
<td>
16

</td>
<td>
Hexadecimal

</td>
</tr>
</table>

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

When the radix is changed, the engine notifies the event callbacks by passing the DEBUG_CES_RADIX flag to the <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> callback method.

For more information about the default radix, see <a href="/windows-hardware/drivers/debugger/using-input-and-output">Using Input and Output</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getradix">GetRadix</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/debugger/n--set-number-base-">n (Set Number Base)</a>

