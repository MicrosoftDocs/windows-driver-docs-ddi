---
UID: NF:dbgeng.IDebugControl2.GetRadix
title: IDebugControl2::GetRadix (dbgeng.h)
description: The GetRadix method returns the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.
old-location: debugger\getradix.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl2::GetRadix"]
ms.keywords: GetRadix, GetRadix method [Windows Debugging], GetRadix method [Windows Debugging],IDebugControl interface, GetRadix method [Windows Debugging],IDebugControl2 interface, GetRadix method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetRadix method, IDebugControl2 interface [Windows Debugging],GetRadix method, IDebugControl2.GetRadix, IDebugControl2::GetRadix, IDebugControl3 interface [Windows Debugging],GetRadix method, IDebugControl3::GetRadix, IDebugControl::GetRadix, IDebugControl_3f4cb732-868a-4944-bcd9-dd1f221824df.xml, dbgeng/IDebugControl2::GetRadix, dbgeng/IDebugControl3::GetRadix, dbgeng/IDebugControl::GetRadix, debugger.getradix
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
 - IDebugControl2::GetRadix
 - dbgeng/IDebugControl2::GetRadix
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl2::GetRadix
---

# IDebugControl2::GetRadix


## -description

The <b>GetRadix</b> method returns the default radix (number base) used by the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a> when it evaluates and displays MASM expressions, and when it displays symbol information.

## -parameters

### -param Radix 

[out]
Receives the default radix.

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

For more information about the default radix, see <a href="/windows-hardware/drivers/debugger/using-input-and-output">Using Input and Output</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setradix">SetRadix</a>



<a href="/windows-hardware/drivers/debugger/n--set-number-base-">n (Set Number Base)</a>

