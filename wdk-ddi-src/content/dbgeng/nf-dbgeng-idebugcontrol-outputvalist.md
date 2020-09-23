---
UID: NF:dbgeng.IDebugControl.OutputVaList
title: IDebugControl::OutputVaList (dbgeng.h)
description: The OutputVaList method formats a string and sends the result to the output callbacks that are registered with the engine's clients.
old-location: debugger\outputvalist.htm
tech.root: debugger
ms.assetid: 6b2c0c43-26a3-4e66-aa9f-45b431ce6516
ms.date: 05/03/2018
keywords: ["IDebugControl::OutputVaList"]
ms.keywords: IDebugControl interface [Windows Debugging],OutputVaList method, IDebugControl.OutputVaList, IDebugControl2 interface [Windows Debugging],OutputVaList method, IDebugControl2::OutputVaList, IDebugControl3 interface [Windows Debugging],OutputVaList method, IDebugControl3::OutputVaList, IDebugControl::OutputVaList, IDebugControl_4c0f8057-9e61-4a89-a2e8-be15bd49e5fc.xml, OutputVaList, OutputVaList method [Windows Debugging], OutputVaList method [Windows Debugging],IDebugControl interface, OutputVaList method [Windows Debugging],IDebugControl2 interface, OutputVaList method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::OutputVaList, dbgeng/IDebugControl3::OutputVaList, dbgeng/IDebugControl::OutputVaList, debugger.outputvalist
req.header: dbgeng.h
req.include-header: Dbgeng.h, Stdarg.h
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
 - IDebugControl::OutputVaList
 - dbgeng/IDebugControl::OutputVaList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.OutputVaList
 - IDebugControl2.OutputVaList
 - IDebugControl3.OutputVaList
---

# IDebugControl::OutputVaList


## -description

The <b>OutputVaList</b>  method formats a string and sends the result to the <a href="/windows-hardware/drivers/debugger/using-input-and-output">output callbacks</a> that are registered with the engine's clients.

## -parameters

### -param Mask 

[in]
Specifies the output-type bit field.  See <a href="/windows-hardware/drivers/debugger/debug-output-xxx">DEBUG_OUTPUT_XXX</a> for possible values.

### -param Format 

[in]
Specifies the format string, as in <b>printf</b>.  Typically, conversion characters work exactly as they do in C. For the floating-point conversion characters, the 64-bit argument is interpreted as a 32-bit floating-point number unless the <b>l</b>  modifier is used.

The <b>%p</b> conversion character is supported, but it represents a pointer in a target's address space.  It might not have any modifiers, and it uses the debugger's internal address formatting.  The following additional conversion characters are supported.

<table>
<tr>
<th>Character</th>
<th>Argument type</th>
<th>Argument</th>
<th>Text printed</th>
</tr>
<tr>
<td>
<b>%p</b>

</td>
<td>
ULONG64

</td>
<td>
Pointer in an address space.

</td>
<td>
The value of the pointer. 

</td>
</tr>
<tr>
<td>
<b>%N</b>

</td>
<td>
DWORD_PTR (32 or 64 bits, depending on the host's architecture) 

</td>
<td>
Pointer in the host's virtual address space.

</td>
<td>
The value of the pointer.  (This is equivalent to the standard C <b>%p</b> character.) 

</td>
</tr>
<tr>
<td>
<b>%I</b>

</td>
<td>
ULONG64

</td>
<td>
Any 64-bit value.

</td>
<td>
The specified value.  If this is greater than 0xFFFFFFFF, it is printed as a 64-bit value; otherwise, it is printed as a 32-bit value.

</td>
</tr>
<tr>
<td>
<b>%ma</b>

</td>
<td>
ULONG64 

</td>
<td>
Address of a NULL-terminated ASCII string in the process's virtual address space.

</td>
<td>
The specified string.

</td>
</tr>
<tr>
<td>
<b>%mu</b>

</td>
<td>
ULONG64 

</td>
<td>
Address of a NULL-terminated Unicode string in the process's virtual address space.

</td>
<td>
The specified string.

</td>
</tr>
<tr>
<td>
<b>%msa</b>

</td>
<td>
ULONG64 

</td>
<td>
Address of an ANSI_STRING structure in the process's virtual address space.

</td>
<td>
The specified string.

</td>
</tr>
<tr>
<td>
<b>%msu</b>

</td>
<td>
ULONG64 

</td>
<td>
Address of a UNICODE_STRING structure in the process's virtual address space.

</td>
<td>
The specified string.

</td>
</tr>
<tr>
<td>
<b>%y</b>

</td>
<td>
ULONG64 

</td>
<td>
Address in the process's virtual address space of an item with symbol information.

</td>
<td>
String that contains the name of the specified symbol (and displacement, if any). 

</td>
</tr>
<tr>
<td>
<b>%ly</b>

</td>
<td>
ULONG64 

</td>
<td>
Address in the process's virtual address space of an item with symbol information.

</td>
<td>
String that contains the name of the specified symbol (and displacement, if any), as well as any available source line information. 

</td>
</tr>
</table>

### -param Args 

[in]
Specifies additional parameters that represent values to be inserted into the output during formatting.  <i>Args</i> must be initialized using <b>va_start</b>.  This method does not call <b>va_end</b>.

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

When generating very large output strings, it is possible to reach the limits of the debugger engine or of the operating system.  For example, some versions of the debugger engine have a 16K character limit for a single output.  If you find that very large output is getting truncated, you might need to split your output into multiple requests.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-controlledoutputvalist">ControlledOutputVaList</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/previous-versions/ff553183(v=vs.85)">Output</a>



<a href="/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_output_routine">dprintf</a>