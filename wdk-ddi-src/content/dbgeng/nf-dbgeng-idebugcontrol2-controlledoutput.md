---
UID: NF:dbgeng.IDebugControl2.ControlledOutput
title: IDebugControl2::ControlledOutput method
author: windows-driver-content
description: The ControlledOutput method formats a string and sends the result to output callbacks that were registered with some of the engine's clients.
old-location: debugger\controlledoutput.htm
old-project: Debugger
ms.assetid: d1a4aba3-9567-4d8e-980c-f6a85f54870e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.controlledoutput, IDebugControl2::ControlledOutput, IDebugControl, IDebugControl_b35fb81f-3425-4a39-8c80-b6e8a161ba71.xml, ControlledOutput method [Windows Debugging], IDebugControl3 interface, IDebugControl interface [Windows Debugging], ControlledOutput method, IDebugControl3 interface [Windows Debugging], ControlledOutput method, ControlledOutput method [Windows Debugging], IDebugControl2 interface, IDebugControl2 interface [Windows Debugging], ControlledOutput method, IDebugControl2, ControlledOutput method [Windows Debugging], dbgeng/IDebugControl2::ControlledOutput, dbgeng/IDebugControl3::ControlledOutput, IDebugControl3::ControlledOutput, ControlledOutput method [Windows Debugging], IDebugControl interface, ControlledOutput, dbgeng/IDebugControl::ControlledOutput, IDebugControl::ControlledOutput
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
-	IDebugControl.ControlledOutput
-	IDebugControl2.ControlledOutput
-	IDebugControl3.ControlledOutput
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::ControlledOutput method


## -description


The <b>ControlledOutput</b>  method formats a string and sends the result to <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">output callbacks</a> that were registered with some of the engine's clients.


## -syntax


````
HRESULT ControlledOutput(
  [in] ULONG OutputControl,
  [in] ULONG Mask,
  [in] PCSTR Format,
             ...
);
````


## -parameters




### -param OutputControl [in]

Specifies an output control that determines which of the clients' output callbacks will receive the output.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.  For more information about output, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.


### -param Mask [in]

Specifies the output-type bit field.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> for possible values.


### -param Format [in]

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
 

The %Y format specifier can be used to support the Debugger Markup Language (DML). For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt613235">Customizing Debugger Output Using DML</a>.

The following table summarizes the use of the %Y format specifier.

<table>
<tr>
<td>Character</td>
<td>Argument type</td>
<td>Argument</td>
<td>Text printed</td>
</tr>
<tr>
<td>
<b>%Y{t}</b>

</td>
<td>
String

</td>
<td>Text</td>
<td>	  Quoted string.  Will convert text to DML if the output format (first arg) is DML.</td>
</tr>
<tr>
<td>
<b>%Y{T}</b>

</td>
<td>
String

</td>
<td>Text</td>
<td>Quoted string.  Will always convert text to DML regardless of the output format.</td>
</tr>
<tr>
<td>
<b>%Y{s}</b>

</td>
<td>
 String

</td>
<td>Text</td>
<td>  Unquoted string. Will convert text to DML if the output format (first arg) is DML.</td>
</tr>
<tr>
<td>
<b>%Y{S}</b>

</td>
<td>
String

</td>
<td>Text</td>
<td>	  Unquoted string. Will always convert text to DML regardless of the output format.</td>
</tr>
<tr>
<td>
<b>%Y{as}</b>

</td>
<td>
ULONG64

</td>
<td>Debugger formatted pointer</td>
<td>Adds either an empty string or 9 characters of spacing for padding the high 32-bit portion of debugger formatted pointer fields. The extra space outputs 9 spaces which includes the upper 8 zeros plus the ` character.</td>
</tr>
<tr>
<td>
<b>%Y{ps}</b>

</td>
<td>
ULONG64

</td>
<td>Debugger formatted pointer</td>
<td>	Adds either an empty string or 8 characters of spacing for padding the high 32-bit portion of debugger formatted pointer fields. </td>
</tr>
<tr>
<td>
<b>%Y{l}</b>

</td>
<td>
ULONG64

</td>
<td>Debugger formatted pointer</td>
<td>	Address as source line information.</td>
</tr>
</table>
 

This code snippet illustrates the use of the  %Y format specifier.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT CALLBACK testout(_In_ PDEBUG_CLIENT pClient, _In_ PCWSTR /*pwszArgs*/)
{
    HRESULT hr = S_OK;

    ComPtr&lt;IDebugControl4&gt; spControl;
    IfFailedReturn(pClient-&gt;QueryInterface(IID_PPV_ARGS(&amp;spControl)));

    spControl-&gt;ControlledOutputWide(DEBUG_OUTCTL_DML, DEBUG_OUTPUT_NORMAL, L"DML/NORMAL Y{t}: %Y{t}\n", L"Hello &lt;World&gt;");
    spControl-&gt;ControlledOutputWide(DEBUG_OUTCTL_DML, DEBUG_OUTPUT_NORMAL, L"DML/NORMAL Y{T}: %Y{T}\n", L"Hello &lt;World&gt;");
    spControl-&gt;ControlledOutputWide(DEBUG_OUTCTL_DML, DEBUG_OUTPUT_NORMAL, L"DML/NORMAL Y{s}: %Y{s}\n", L"Hello &lt;World&gt;");
    spControl-&gt;ControlledOutputWide(DEBUG_OUTCTL_DML, DEBUG_OUTPUT_NORMAL, L"DML/NORMAL Y{S}: %Y{S}\n", L"Hello &lt;World&gt;");

    spControl-&gt;ControlledOutputWide(0, DEBUG_OUTPUT_NORMAL, L"TEXT/NORMAL Y{t}: %Y{t}\n", L"Hello &lt;World&gt;");
    spControl-&gt;ControlledOutputWide(0, DEBUG_OUTPUT_NORMAL, L"TEXT/NORMAL Y{T}: %Y{T}\n", L"Hello &lt;World&gt;");
    spControl-&gt;ControlledOutputWide(0, DEBUG_OUTPUT_NORMAL, L"TEXT/NORMAL Y{s}: %Y{s}\n", L"Hello &lt;World&gt;");
    spControl-&gt;ControlledOutputWide(0, DEBUG_OUTPUT_NORMAL, L"TEXT/NORMAL Y{S}: %Y{S}\n", L"Hello &lt;World&gt;");

    spControl-&gt;ControlledOutputWide(DEBUG_OUTCTL_DML, DEBUG_OUTPUT_NORMAL, L"DML/NORMAL Y{a}: %Y{a}\n", (ULONG64)0x00007ffa7da163c0);
    spControl-&gt;ControlledOutputWide(DEBUG_OUTCTL_DML, DEBUG_OUTPUT_NORMAL, L"DML/NORMAL Y{as} 64bit   : '%Y{as}'\n", (ULONG64)0x00007ffa7da163c0);
    spControl-&gt;ControlledOutputWide(DEBUG_OUTCTL_DML, DEBUG_OUTPUT_NORMAL, L"DML/NORMAL Y{as} 32value : '%Y{as}'\n", (ULONG64)0x1);

    spControl-&gt;ControlledOutputWide(DEBUG_OUTCTL_DML, DEBUG_OUTPUT_NORMAL, L"DML/NORMAL Y{ps} 64bit   : '%Y{ps}'\n", (ULONG64)0x00007ffa7da163c0);
    spControl-&gt;ControlledOutputWide(DEBUG_OUTCTL_DML, DEBUG_OUTPUT_NORMAL, L"DML/NORMAL Y{ps} 32value : '%Y{ps}'\n", (ULONG64)0x1);

    spControl-&gt;ControlledOutputWide(DEBUG_OUTCTL_DML, DEBUG_OUTPUT_NORMAL, L"DML/NORMAL Y{l}: %Y{l}\n", (ULONG64)0x00007ffa7da163c0);

    return hr;

}
</pre>
</td>
</tr>
</table></span></div>
This sample code would generate the following output.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>0:004&gt; !testout
DML/NORMAL Y{t}: "Hello &lt;World&gt;"
DML/NORMAL Y{T}: "Hello &lt;World&gt;"
DML/NORMAL Y{s}: Hello &lt;World&gt;
DML/NORMAL Y{S}: Hello &lt;World&gt;
TEXT/NORMAL Y{t}: "Hello &lt;World&gt;"
TEXT/NORMAL Y{T}: &amp;quot;Hello &amp;lt;World&amp;gt;&amp;quot;
TEXT/NORMAL Y{s}: Hello &lt;World&gt;
TEXT/NORMAL Y{S}: Hello &amp;lt;World&amp;gt;
DML/NORMAL Y{a}: 00007ffa`7da163c0
DML/NORMAL Y{as} 64bit   : '         '
DML/NORMAL Y{as} 32value : '         '
DML/NORMAL Y{ps} 64bit   : '        '
DML/NORMAL Y{ps} 32value : '        '
DML/NORMAL Y{l}: [d:\th\minkernel\kernelbase\debug.c @ 443]
</pre>
</td>
</tr>
</table></span></div>



### -param param






####### - ...

Specifies additional parameters that represent values to be inserted into the output during formatting.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539252">ControlledOutputVaList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553183">Output</a>



<a href="..\wdbgexts\nc-wdbgexts-pwindbg_output_routine.md">dprintf</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl::ControlledOutput method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

