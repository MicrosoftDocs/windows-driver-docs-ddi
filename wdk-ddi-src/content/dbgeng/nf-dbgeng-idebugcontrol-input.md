---
UID: NF:dbgeng.IDebugControl.Input
title: IDebugControl::Input (dbgeng.h)
description: The Input method requests an input string from the debugger engine.
old-location: debugger\input.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugControl::Input"]
ms.keywords: IDebugControl interface [Windows Debugging],Input method, IDebugControl.Input, IDebugControl::Input, IDebugControl_10615761-d032-439f-955b-220def3835a9.xml, Input, Input method [Windows Debugging], Input method [Windows Debugging],IDebugControl interface, dbgeng/IDebugControl::Input, debugger.input
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
 - IDebugControl::Input
 - dbgeng/IDebugControl::Input
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugControl::Input
---

# IDebugControl::Input


## -description

The <b>Input</b>  method requests an input string from the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a>.

## -parameters

### -param Buffer [out]


Receives the input string from the engine.

### -param BufferSize [in]


Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies. This size includes the space for the '\0' terminating character.

### -param InputSize [out, optional]


Receives the number of characters returned in <i>Buffer</i>. This size includes the space for the '\0' terminating character. If <i>InputSize</i> is <b>NULL</b>, this information is not returned.

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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the buffer was not big enough to hold the whole input string and it was truncated.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

For an overview of input in the debugger engine, see <a href="/windows-hardware/drivers/debugger/input-and-output">Input and Output</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-inputwide">InputWide</a>

