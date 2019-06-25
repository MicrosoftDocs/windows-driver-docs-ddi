---
UID: NF:dbgeng.IDebugControl3.OutputPrompt
title: IDebugControl3::OutputPrompt (dbgeng.h)
description: The OutputPrompt method formats and sends a user prompt to the output callback objects.
old-location: debugger\outputprompt.htm
tech.root: debugger
ms.assetid: 463d6fbd-cbe4-4de1-a01a-52a5002f24b8
ms.date: 05/03/2018
ms.keywords: IDebugControl interface [Windows Debugging],OutputPrompt method, IDebugControl2 interface [Windows Debugging],OutputPrompt method, IDebugControl2::OutputPrompt, IDebugControl3 interface [Windows Debugging],OutputPrompt method, IDebugControl3.OutputPrompt, IDebugControl3::OutputPrompt, IDebugControl::OutputPrompt, IDebugControl_bb972181-80f5-4c7a-8705-919273529eee.xml, OutputPrompt, OutputPrompt method [Windows Debugging], OutputPrompt method [Windows Debugging],IDebugControl interface, OutputPrompt method [Windows Debugging],IDebugControl2 interface, OutputPrompt method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::OutputPrompt, dbgeng/IDebugControl3::OutputPrompt, dbgeng/IDebugControl::OutputPrompt, debugger.outputprompt
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Dbgeng.h
api_name:
- IDebugControl.OutputPrompt
- IDebugControl2.OutputPrompt
- IDebugControl3.OutputPrompt
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::OutputPrompt


## -description


The <b>OutputPrompt</b>  method formats and sends a user prompt to the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-callback-objects">output callback objects</a>.


## -parameters




### -param OutputControl [in]

Specifies an output control that determines which of the client's output callbacks will receive the output.  For possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.


### -param Format [in, optional]

Specifies the format string, as in <b>printf</b>.  Typically, conversion characters work exactly as they do in C. For the floating-point conversion characters, the 64-bit argument is interpreted as a 32-bit floating-point number unless the <b>l</b>  modifier is used.

The <b>%p</b> conversion character is supported, but it represents a pointer in a target's address space.  It might not have any modifiers and it uses the debugger's internal address formatting.  The following additional conversion characters are supported.

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
Address of a NULL-terminated ASCII string in the process' virtual address space.

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
 

If <i>Format</i> is <b>NULL</b>, only the standard prompt text is sent to the output callbacks.


### -param param






####### - ...

Specifies additional parameters that represent values to be inserted into the output during formatting.


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
 

This method can also return error values. See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



<b>OutputPrompt</b> and <b>OutputPromptWide</b> can be used to prompt the user for input.

The standard prompt will be sent to the output callbacks before the formatted text described by <i>Format</i>.  The contents of the standard prompt is returned by the method <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getprompttext">GetPromptText</a>.

The prompt text is sent to the output callbacks with the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-output-xxx">DEBUG_OUTPUT_PROMPT</a> output mask set.

For more information about prompting the user, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">Using Input and Output</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539248">ControlledOutput</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-output-xxx">DEBUG_OUTPUT_XXX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getprompttext">GetPromptText</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-outputpromptvalist">OutputPromptVaList</a>
 

 

