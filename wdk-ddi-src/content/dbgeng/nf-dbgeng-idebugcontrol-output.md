---
UID: NF:dbgeng.IDebugControl.Output
title: IDebugControl::Output
author: windows-driver-content
description: The Output method formats a string and send the result to output callbacks that have been registered with the engine's clients.
old-location: debugger\output.htm
tech.root: debugger
ms.assetid: 2c748325-3718-4fcc-98a3-3318d361ba6e
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: IDebugControl interface [Windows Debugging],Output method, IDebugControl.Output, IDebugControl2 interface [Windows Debugging],Output method, IDebugControl2::Output, IDebugControl3 interface [Windows Debugging],Output method, IDebugControl3::Output, IDebugControl::Output, IDebugControl_4b29317b-e521-4deb-84dc-fc4bb7d6ca90.xml, Output, Output method [Windows Debugging], Output method [Windows Debugging],IDebugControl interface, Output method [Windows Debugging],IDebugControl2 interface, Output method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::Output, dbgeng/IDebugControl3::Output, dbgeng/IDebugControl::Output, debugger.output
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl.Output
-	IDebugControl2.Output
-	IDebugControl3.Output
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::Output


## -description


The <b>Output</b>  method formats a string and send the result to output callbacks that have been registered with the engine's clients.


## -parameters




### -param Mask [in]

Specifies the output-type bit field.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> for possible values.


### -param Format [in]

Specifies the format string, as in <b>printf</b>.  In general, conversion characters work exactly as in C. For the floating-point conversion characters the 64-bit argument is interpreted as a 32-bit floating-point number unless the <b>l</b>  modifier is used.

The <b>%p</b> conversion character is supported, but it represents a pointer in a target's address space.  It cannot have any modifiers and it uses the debugger's internal address formatting.  The following additional conversion characters are supported.

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
Pointer in an address space

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
Pointer in the host's virtual address space

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
Any 64-bit value

</td>
<td>
The specified value.  If this is greater than 0xFFFFFFFF, it is printed as a 64-bit value. Otherwise, it is printed as a 32-bit value.

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
Address of a NULL-terminated ASCII string in the process's virtual address space

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
Address of a NULL-terminated Unicode string in the process's virtual address space

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
Address of an ANSI_STRING structure in the process's virtual address space

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
Address of a UNICODE_STRING structure in the process's virtual address space

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
Address in the process's virtual address space of an item with symbol information

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
Address in the process's virtual address space of an item with symbol information

</td>
<td>
String that contains the name of the specified symbol (and displacement, if any), as well as any available source line information. 

</td>
</tr>
</table>
 


### -param param






####### - ...

Specifies additional parameters that contain values to be inserted into the output during formatting.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564716">.printf</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539248">ControlledOutput</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553280">OutputVaList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542750">dprintf</a>
 

 

