---
UID: NF:dbgeng.IDebugDataSpaces4.ReadUnicodeStringVirtual
title: IDebugDataSpaces4::ReadUnicodeStringVirtual method
author: windows-driver-content
description: The ReadUnicodeStringVirtual method reads a null-terminated, Unicode string from the target and converts it to a multibyte string.
old-location: debugger\readunicodestringvirtual.htm
old-project: debugger
ms.assetid: 956ad15d-2c90-473a-b9be-8c5023628841
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4 interface [Windows Debugging], ReadUnicodeStringVirtual method, IDebugDataSpaces4::ReadUnicodeStringVirtual, IDebugDataSpaces_423e591f-3840-4c6c-94e0-67b06a435652.xml, ReadUnicodeStringVirtual method [Windows Debugging], ReadUnicodeStringVirtual method [Windows Debugging], IDebugDataSpaces4 interface, ReadUnicodeStringVirtual,IDebugDataSpaces4.ReadUnicodeStringVirtual, dbgeng/IDebugDataSpaces4::ReadUnicodeStringVirtual, debugger.readunicodestringvirtual
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Winnls.h
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
-	IDebugDataSpaces4.ReadUnicodeStringVirtual
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces4::ReadUnicodeStringVirtual method


## -description


The <b>ReadUnicodeStringVirtual</b> method reads a null-terminated, Unicode string from the target and converts it to a multibyte string.


## -parameters




### -param Offset [in]

Specifies the location in the process's virtual address space of the string.


### -param MaxBytes [in]

Specifies the maximum number of bytes to read from the target.


### -param CodePage [in]

Specifies the code page to use to convert the multibyte string read from the target into a Unicode string.  For example, CP_ACP is the ANSI code page.


### -param Buffer [out, optional]

Receives the string from the target.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param StringBytes [out, optional]

Receives the size, in bytes, of the string in the target.  If <i>StringBytes</i> is <b>NULL</b>, this information is not returned.


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
The method was successful.  However <i>Buffer</i> was not large enough to hold the string and the string was truncated to fit in <i>Buffer</i>.  The truncated string is null-terminated if <i>Buffer</i> has space for at least one character.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
A null-terminator was not found after reading <i>MaxBytes</i> from the target.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



The engine will read up to <i>MaxBytes</i> from the target, looking for a null-terminator.  If the string has more than <i>BufferSize</i> characters, the string will be truncated to fit in <i>Buffer</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550546">IDebugDataSpaces4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554300">ReadMultiByteStringVirtual</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554357">ReadUnicodeStringVirtualWide</a>
 

 

