---
UID: NF:dbgeng.IDebugDataSpaces4.ReadMultiByteStringVirtualWide
title: IDebugDataSpaces4::ReadMultiByteStringVirtualWide (dbgeng.h)
description: The ReadMultiByteStringVirtualWide method reads a null-terminated, multibyte string from the target and converts it to Unicode.
old-location: debugger\readmultibytestringvirtualwide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces4::ReadMultiByteStringVirtualWide"]
ms.keywords: IDebugDataSpaces4 interface [Windows Debugging],ReadMultiByteStringVirtualWide method, IDebugDataSpaces4.ReadMultiByteStringVirtualWide, IDebugDataSpaces4::ReadMultiByteStringVirtualWide, IDebugDataSpaces_c5a99b4a-a468-459e-acc1-f3a4f224f645.xml, ReadMultiByteStringVirtualWide, ReadMultiByteStringVirtualWide method [Windows Debugging], ReadMultiByteStringVirtualWide method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces4::ReadMultiByteStringVirtualWide, debugger.readmultibytestringvirtualwide
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugDataSpaces4::ReadMultiByteStringVirtualWide
 - dbgeng/IDebugDataSpaces4::ReadMultiByteStringVirtualWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugDataSpaces4.ReadMultiByteStringVirtualWide
---

# IDebugDataSpaces4::ReadMultiByteStringVirtualWide


## -description

The <b>ReadMultiByteStringVirtualWide</b> method reads a null-terminated, multibyte string from the target and converts it to Unicode.

## -parameters

### -param Offset 

[in]
Specifies the location of the string in the process's virtual address space.

### -param MaxBytes 

[in]
Specifies the maximum number of bytes to read from the target.

### -param CodePage 

[in]
Specifies the code page to use to convert the multibyte string read from the target into a Unicode string.  For example, CP_ACP is the ANSI code page.

### -param Buffer 

[out, optional]
Receives the string from the target.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize 

[in]
Specifies the size, in characters, of the <i>Buffer</i> buffer.

### -param StringBytes 

[out, optional]
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
The method was not successful. 

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
 

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

The engine will read up to <i>MaxBytes</i> from the target, looking for a null-terminator.  If the string has more than <i>BufferSize</i> characters, the string will be truncated to fit in <i>Buffer</i>.

Note that even if S_OK is returned, the buffer may not have been large enough to store the string. In this case the string is truncated to fit in <i>Buffer</i>.  The truncated string is null-terminated if <i>Buffer</i> has space for at least one character. After the call returns, check to see if *StringBytes is bigger than BufferSize.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readmultibytestringvirtual">ReadMultiByteStringVirtual</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readunicodestringvirtualwide">ReadUnicodeStringVirtualWide</a>
