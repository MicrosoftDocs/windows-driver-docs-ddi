---
UID: NF:dbgeng.IDebugControl3.OutputPrompt
title: IDebugControl3::OutputPrompt method
author: windows-driver-content
description: The OutputPrompt method formats and sends a user prompt to the output callback objects.
old-location: debugger\outputprompt.htm
old-project: Debugger
ms.assetid: 463d6fbd-cbe4-4de1-a01a-52a5002f24b8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugControl3, OutputPrompt method [Windows Debugging], IDebugControl2, IDebugControl2::OutputPrompt, IDebugControl interface [Windows Debugging], OutputPrompt method, IDebugControl, debugger.outputprompt, dbgeng/IDebugControl::OutputPrompt, IDebugControl3 interface [Windows Debugging], OutputPrompt method, IDebugControl_bb972181-80f5-4c7a-8705-919273529eee.xml, OutputPrompt method [Windows Debugging], IDebugControl interface, OutputPrompt, OutputPrompt method [Windows Debugging], IDebugControl2 interface, dbgeng/IDebugControl3::OutputPrompt, IDebugControl2 interface [Windows Debugging], OutputPrompt method, dbgeng/IDebugControl2::OutputPrompt, OutputPrompt method [Windows Debugging], IDebugControl3 interface, IDebugControl3::OutputPrompt, IDebugControl::OutputPrompt
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Dbgeng.h
apiname:
-	IDebugControl.OutputPrompt
-	IDebugControl2.OutputPrompt
-	IDebugControl3.OutputPrompt
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::OutputPrompt method


## -description


The <b>OutputPrompt</b>  method formats and sends a user prompt to the <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">output callback objects</a>.


## -syntax


````
HRESULT OutputPrompt(
  [in]           ULONG OutputControl,
  [in, optional] PCSTR Format,
                       ...
);
````


## -parameters




### -param OutputControl [in]

Specifies an output control that determines which of the client's output callbacks will receive the output.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.


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
 

This method can also return error values. See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



<b>OutputPrompt</b> and <b>OutputPromptWide</b> can be used to prompt the user for input.

The standard prompt will be sent to the output callbacks before the formatted text described by <i>Format</i>.  The contents of the standard prompt is returned by the method <a href="https://msdn.microsoft.com/library/windows/hardware/ff548180">GetPromptText</a>.

The prompt text is sent to the output callbacks with the <a href="https://msdn.microsoft.com/0c500a2e-0817-45de-8607-4cd4a29d5813">DEBUG_OUTPUT_PROMPT</a> output mask set.

For more information about prompting the user, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539248">ControlledOutput</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553231">OutputPromptVaList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539248">ControlledOutput</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548180">GetPromptText</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl::OutputPrompt method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

