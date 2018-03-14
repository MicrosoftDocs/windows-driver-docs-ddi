---
UID: NF:dbgeng.IDebugDataSpaces4.ReadUnicodeStringVirtualWide
title: IDebugDataSpaces4::ReadUnicodeStringVirtualWide method
author: windows-driver-content
description: The ReadUnicodeStringVirtualWide method reads a null-terminated, Unicode string from the target.
old-location: debugger\readunicodestringvirtualwide.htm
old-project: debugger
ms.assetid: 7c360f9a-83f6-4bc8-abb4-08d1b0c4fdc9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4 interface [Windows Debugging], ReadUnicodeStringVirtualWide method, IDebugDataSpaces4::ReadUnicodeStringVirtualWide, IDebugDataSpaces_c722fa7f-bbd2-4e0c-bd83-c59d2442ae26.xml, ReadUnicodeStringVirtualWide method [Windows Debugging], ReadUnicodeStringVirtualWide method [Windows Debugging], IDebugDataSpaces4 interface, ReadUnicodeStringVirtualWide,IDebugDataSpaces4.ReadUnicodeStringVirtualWide, dbgeng/IDebugDataSpaces4::ReadUnicodeStringVirtualWide, debugger.readunicodestringvirtualwide
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
-	IDebugDataSpaces4.ReadUnicodeStringVirtualWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces4::ReadUnicodeStringVirtualWide method


## -description


The <b>ReadUnicodeStringVirtualWide</b> method reads a null-terminated, Unicode string from the target.


## -syntax


````
HRESULT ReadUnicodeStringVirtualWide(
  [in]            ULONG64 Offset,
  [in]            ULONG   MaxBytes,
  [out, optional] PWSTR   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  StringBytes
);
````


## -parameters




### -param Offset [in]

Specifies the location of the string in the process's virtual address space.


### -param MaxBytes [in]

Specifies the maximum number of bytes to read from the target.


### -param Buffer [out, optional]

Receives the string from the target.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

<div class="alert"><b>Note</b>    The remainder of the buffer, following the returned string, might be overwritten by this method.</div>
<div> </div>

### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param StringBytes [out, optional]

Receives the size, in bytes, of the string.  If <i>StringBytes</i> is <b>NULL</b>, this information is not returned.


## -returns



This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<td width="60%"></td>
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
 

The method was successful.




## -remarks



The engine will read up to <i>MaxBytes</i> from the target, looking for a null-terminator.  If the string has more than <i>BufferSize</i> characters, the string will be truncated to fit in <i>Buffer</i>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554304">ReadMultiByteStringVirtualWide</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554351">ReadUnicodeStringVirtual</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>



 

 


