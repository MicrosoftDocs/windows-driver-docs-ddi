---
UID: NC:wdbgexts.PWINDBG_OUTPUT_ROUTINE
title: PWINDBG_OUTPUT_ROUTINE
author: windows-driver-content
description: The callback function implements the functionality to print a formatted string to the Debugger Command window.
old-location: debugger\dprintf.htm
old-project: debugger
ms.assetid: 33bcf4d4-1a79-4950-858e-10543faa9432
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.dprintf, dprintf, dprintf callback function [Windows Debugging], dprintf, PWINDBG_OUTPUT_ROUTINE, PWINDBG_OUTPUT_ROUTINE, wdbgexts/dprintf, WdbgExts_Ref_89454805-6140-4023-ba28-2d7130c73cf5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wdbgexts.h
apiname:
-	dprintf
product: Windows
targetos: Windows
req.typenames: VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
req.product: Windows 10 or later.
---

# PWINDBG_OUTPUT_ROUTINE callback


## -description


The callback function implements the functionality to print a formatted string to the Debugger Command window. 

The wdbgexts.h header declares a macro, <b>dprintf</b> that  prints the formatted string. It works like the C-language routine <b>printf</b>. 


## -prototype


````
PWINDBG_OUTPUT_ROUTINE dprintf;

VOID dprintf(
  _In_ PCSTR format,
  _In_ ...   [arguments]
)
{ ... }
````


## -parameters




### -param lpFormat


### -param ...








#### - [arguments] [in]

Specifies arguments for the format string, as in <b>printf</b>. The number of arguments specified should match the number of conversion characters in <i>FormatString</i>. Each argument is an expression that will be evaluated by the default expression evaluator (MASM or C++). For details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552280">Numerical Expression Syntax</a>. 


#### - format [in]

Specifies the format string, as in <b>printf</b>.  In general, conversion characters work exactly as in C. For the floating-point conversion characters the 64-bit argument is interpreted as a 32-bit floating-point number unless the <b>l</b>  modifier is used.

The <b>%p</b> conversion character is supported, but it represents a pointer in the target's virtual address space.  It may not have any modifiers and it uses the debugger's internal address formatting.  The following additional conversion characters are supported:

<table>
<tr>
<th>Character</th>
<th>Argument Type</th>
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
Pointer in the target's virtual address space

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
DWORD_PTR (32 or 64 bits, depending on the <u>host's</u> architecture) 

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
The specified value.  If this is greater than 0xFFFFFFFF it is printed as a 64-bit address, otherwise it is printed as a 32-bit address.

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
Address of a NULL-terminated ASCII string in the target's virtual address space

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
Address of a NULL-terminated Unicode string in the target's virtual address space

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
Address of an ANSI_STRING structure in the target's virtual address space

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
Address of a UNICODE_STRING structure in the target's virtual address space

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
Address of a debugger symbol in the target's virtual address space

</td>
<td>
String containing the name of the specified symbol (and displacement, if any). 

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
Address of a debugger symbol in the target's virtual address space

</td>
<td>
String containing the name of the specified symbol (and displacement, if any), as well as any available source line information. 

</td>
</tr>
</table>
 


## -returns



This callback function does not return a value.




## -remarks



When generating very large output strings, it is possible the limits of the debugger engine or operating system may be reached.  For example, some versions of the debugger engine have a 16K character limit for a single piece of output.  If you find that very large output is getting truncated, you may need to split your output into multiple requests.



