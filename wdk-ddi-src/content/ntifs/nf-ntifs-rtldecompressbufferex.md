---
UID: NF:ntifs.RtlDecompressBufferEx
title: RtlDecompressBufferEx function (ntifs.h)
description: The RtlDecompressBufferEx function decompresses an entire compressed buffer.
old-location: ifsk\rtldecompressbufferex.htm
tech.root: ifsk
ms.assetid: 5AB55689-66F4-41BD-97B6-1E01899AFE23
ms.date: 04/16/2018
keywords: ["RtlDecompressBufferEx function"]
ms.keywords: COMPRESSION_FORMAT_DEFAULT, COMPRESSION_FORMAT_LZNT1, COMPRESSION_FORMAT_NONE, COMPRESSION_FORMAT_XPRESS, COMPRESSION_FORMAT_XPRESS_HUFF, RtlDecompressBufferEx, RtlDecompressBufferEx function [Installable File System Drivers], ifsk.rtldecompressbufferex, ntifs/RtlDecompressBufferEx
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting in Windows 8.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlDecompressBufferEx
 - ntifs/RtlDecompressBufferEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlDecompressBufferEx
---

# RtlDecompressBufferEx function


## -description

The <b>RtlDecompressBufferEx</b> function decompresses an entire compressed buffer.

## -parameters

### -param CompressionFormat 

[in]
A bitmask that specifies the compression format of the compressed buffer. This parameter must be set to COMPRESSION_FORMAT_LZNT1. The meaning of this and other related compression format values are as follows.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_FORMAT_NONE"></a><a id="compression_format_none"></a><dl>
<dt><b>COMPRESSION_FORMAT_NONE</b></dt>
</dl>
</td>
<td width="60%">
Not supported by this function.

</td>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_FORMAT_DEFAULT"></a><a id="compression_format_default"></a><dl>
<dt><b>COMPRESSION_FORMAT_DEFAULT</b></dt>
</dl>
</td>
<td width="60%">
Not supported by this function.

</td>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_FORMAT_LZNT1"></a><a id="compression_format_lznt1"></a><dl>
<dt><b>COMPRESSION_FORMAT_LZNT1</b></dt>
</dl>
</td>
<td width="60%">
The function will perform LZ decompression.

</td>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_FORMAT_XPRESS"></a><a id="compression_format_xpress"></a><dl>
<dt><b>COMPRESSION_FORMAT_XPRESS</b></dt>
</dl>
</td>
<td width="60%">
The function will perform Xpress decompression.

</td>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_FORMAT_XPRESS_HUFF"></a><a id="compression_format_xpress_huff"></a><dl>
<dt><b>COMPRESSION_FORMAT_XPRESS_HUFF</b></dt>
</dl>
</td>
<td width="60%">
The function will perform Xpress Huffman decompression.

</td>
</tr>
</table>

### -param UncompressedBuffer 

[out]
A pointer to a caller-allocated buffer (allocated from paged or non-paged pool) that receives the decompressed data from <i>CompressedBuffer</i>. This parameter is required and cannot be <b>NULL</b>.

### -param UncompressedBufferSize 

[in]
The size, in bytes, of the <i>UncompressedBuffer</i>buffer.

### -param CompressedBuffer 

[in]
A pointer to the buffer that contains the data to decompress. This parameter is required and cannot be <b>NULL</b>.

### -param CompressedBufferSize 

[in]
The size, in bytes, of the <i>CompressedBuffer</i> buffer.

### -param FinalUncompressedSize 

[out]
A pointer to a caller-allocated variable that receives the size, in bytes, of the decompressed data stored in <i>UncompressedBuffer</i>. This parameter is required and cannot be <b>NULL</b>.

### -param WorkSpace 

[in]
A pointer to a caller-allocated work space buffer used by the <b>RtlDecompressBufferEx</b> function during decompression. Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlgetcompressionworkspacesize">RtlGetCompressionWorkSpaceSize</a> function to determine the correct work space buffer size.

## -returns

<b>RtlDecompressBufferEx</b> returns an appropriate error status value, such as one of the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The <i>CompressedBuffer</i> buffer was successfully decompressed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid compression format was specified through the <i>CompressionFormat</i> parameter. If <i>CompressionFormat</i> is either COMPRESSION_FORMAT_NONE or COMPRESSION_FORMAT_DEFAULT (but not both), this value is returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUPPORTED_COMPRESSION</b></dt>
</dl>
</td>
<td width="60%">
An invalid compression format was specified through the <i>CompressionFormat</i> parameter. If <i>CompressionFormat</i> is not one of the following, STATUS_UNSUPPORTED_COMPRESSION is returned:

<ul>
<li>
 COMPRESSION_FORMAT_LZNT1

</li>
<li>
 COMPRESSION_FORMAT_XPRESS

</li>
<li>
 COMPRESSION_FORMAT_XPRESS_HUFF

</li>
<li>
 COMPRESSION_FORMAT_NONE (in this case, STATUS_INVALID_PARAMETER is returned).

</li>
<li>
 COMPRESSION_FORMAT_DEFAULT (in this case, STATUS_INVALID_PARAMETER is returned).

</li>
</ul>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BAD_COMPRESSION_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
<i>UncompressedBuffer</i> is not large enough to contain the uncompressed data.

</td>
</tr>
</table>

## -remarks

The <b>RtlDecompressBufferEx</b> function takes as input an entire compressed buffer and produces its decompressed equivalent provided that the uncompressed data fits within the specified destination buffer.

To decompress only a portion of a compressed buffer (that is, a "fragment" of the buffer), use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldecompressfragment">RtlDecompressFragment</a> function.

To compress an uncompressed buffer, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcompressbuffer">RtlCompressBuffer</a> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_compression_information">FILE_COMPRESSION_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcompressbuffer">RtlCompressBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldecompressbuffer">RtlDecompressBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldecompressbufferex2">RtlDecompressBufferEx2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldecompressfragment">RtlDecompressFragment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldecompressfragmentex">RtlDecompressFragmentEx</a>

