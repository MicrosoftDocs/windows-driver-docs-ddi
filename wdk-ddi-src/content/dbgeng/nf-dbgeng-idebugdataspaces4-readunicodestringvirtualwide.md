---
UID: NF:dbgeng.IDebugDataSpaces4.ReadUnicodeStringVirtualWide
title: IDebugDataSpaces4::ReadUnicodeStringVirtualWide (dbgeng.h)
description: The ReadUnicodeStringVirtualWide method reads a null-terminated, Unicode string from the target.
old-location: debugger\readunicodestringvirtualwide.htm
tech.root: debugger
ms.assetid: 7c360f9a-83f6-4bc8-abb4-08d1b0c4fdc9
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces4::ReadUnicodeStringVirtualWide"]
ms.keywords: IDebugDataSpaces4 interface [Windows Debugging],ReadUnicodeStringVirtualWide method, IDebugDataSpaces4.ReadUnicodeStringVirtualWide, IDebugDataSpaces4::ReadUnicodeStringVirtualWide, IDebugDataSpaces_c722fa7f-bbd2-4e0c-bd83-c59d2442ae26.xml, ReadUnicodeStringVirtualWide, ReadUnicodeStringVirtualWide method [Windows Debugging], ReadUnicodeStringVirtualWide method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces4::ReadUnicodeStringVirtualWide, debugger.readunicodestringvirtualwide
f1_keywords:
 - "dbgeng/IDebugDataSpaces4.ReadUnicodeStringVirtualWide"
 - "IDebugDataSpaces4.ReadUnicodeStringVirtualWide"
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
- dbgeng.h
api_name:
- IDebugDataSpaces4.ReadUnicodeStringVirtualWide
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces4::ReadUnicodeStringVirtualWide


## -description


The <b>ReadUnicodeStringVirtualWide</b> method reads a null-terminated, Unicode string from the target.


## -parameters




### -param Offset 
[in]
Specifies the location of the string in the process's virtual address space.


### -param MaxBytes 
[in]
Specifies the maximum number of bytes to read from the target.


### -param Buffer 
[out, optional]
Receives the string from the target.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

<div class="alert"><b>Note</b>    The remainder of the buffer, following the returned string, might be overwritten by this method.</div>
<div> </div>

### -param BufferSize 
[in]
Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param StringBytes 
[out, optional]
Receives the size, in bytes, of the string.  If <i>StringBytes</i> is <b>NULL</b>, this information is not returned.


## -returns



This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readmultibytestringvirtualwide">ReadMultiByteStringVirtualWide</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readunicodestringvirtual">ReadUnicodeStringVirtual</a>
 

 

