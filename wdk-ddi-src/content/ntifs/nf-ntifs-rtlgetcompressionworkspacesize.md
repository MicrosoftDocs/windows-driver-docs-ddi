---
UID: NF:ntifs.RtlGetCompressionWorkSpaceSize
title: RtlGetCompressionWorkSpaceSize function (ntifs.h)
description: The RtlGetCompressionWorkSpaceSize function is used to determine the correct size of the WorkSpace buffer for the RtlCompressBuffer and RtlDecompressFragment functions.
old-location: ifsk\rtlgetcompressionworkspacesize.htm
tech.root: ifsk
ms.assetid: f0e856f8-9c01-4219-b521-ab4a5c9bc35c
ms.date: 04/16/2018
keywords: ["RtlGetCompressionWorkSpaceSize function"]
ms.keywords: RtlGetCompressionWorkSpaceSize, RtlGetCompressionWorkSpaceSize function [Installable File System Drivers], ifsk.rtlgetcompressionworkspacesize, ntifs/RtlGetCompressionWorkSpaceSize, rtlref_26332738-6278-49f9-b948-87bcb7e68c83.xml
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and all later versions of Windows operating systems.
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
 - RtlGetCompressionWorkSpaceSize
 - ntifs/RtlGetCompressionWorkSpaceSize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlGetCompressionWorkSpaceSize
---

# RtlGetCompressionWorkSpaceSize function


## -description

The <b>RtlGetCompressionWorkSpaceSize</b> function is used to determine the correct size of the <i>WorkSpace</i> buffer for the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcompressbuffer">RtlCompressBuffer</a> and <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldecompressfragment">RtlDecompressFragment</a> functions.

## -parameters

### -param CompressionFormatAndEngine 

[in]
Bitmask specifying the compression format and engine type. This parameter must be set to a valid bitwise OR combination of one format type and one engine type. For example, COMPRESSION_FORMAT_LZNT1 | COMPRESSION_ENGINE_STANDARD.

The meanings of these, and other related values, are as follows:

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
The function will perform LZ compression.

</td>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_FORMAT_XPRESS"></a><a id="compression_format_xpress"></a><dl>
<dt><b>COMPRESSION_FORMAT_XPRESS</b></dt>
</dl>
</td>
<td width="60%">
The function will perform Xpress compression.

</td>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_FORMAT_XPRESS_HUFF"></a><a id="compression_format_xpress_huff"></a><dl>
<dt><b>COMPRESSION_FORMAT_XPRESS_HUFF</b></dt>
</dl>
</td>
<td width="60%">
The function will perform Xpress Huffman compression.

</td>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_ENGINE_STANDARD"></a><a id="compression_engine_standard"></a><dl>
<dt><b>COMPRESSION_ENGINE_STANDARD</b></dt>
</dl>
</td>
<td width="60%">
The <i>UncompressedBuffer</i> buffer is compressed using an algorithm that provides a balance between data compression and performance. This value cannot be used with COMPRESSION_ENGINE_MAXIMUM.

</td>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_ENGINE_MAXIMUM"></a><a id="compression_engine_maximum"></a><dl>
<dt><b>COMPRESSION_ENGINE_MAXIMUM</b></dt>
</dl>
</td>
<td width="60%">
The <i>UncompressedBuffer</i> buffer is compressed using an algorithm that provides maximum data compression but with relatively slower performance. This value cannot be used with COMPRESSION_ENGINE_STANDARD.

</td>
</tr>
<tr>
<td width="40%"><a id="COMPRESSION_ENGINE_HIBER"></a><a id="compression_engine_hiber"></a><dl>
<dt><b>COMPRESSION_ENGINE_HIBER</b></dt>
</dl>
</td>
<td width="60%">
Not supported by this function.

</td>
</tr>
</table>

### -param CompressBufferWorkSpaceSize 

[out]
A pointer to a caller-allocated buffer receiving the size, in bytes, required to compress a buffer. This value is used to determine the correct size of <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcompressbuffer">RtlCompressBuffer</a>'s <i>WorkSpace</i> buffer.

### -param CompressFragmentWorkSpaceSize 

[out]
A pointer to a caller-allocated buffer receiving the size, in bytes, required to decompress a compressed buffer to a fragment. This value is used to determine the correct size of <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldecompressfragment">RtlDecompressFragment</a>'s <i>WorkSpace</i> buffer. Note that the <b>RtlCompressFragment</b> function does not currently exist.

## -returns

<b>RtlGetCompressionWorkSpaceSize</b>returns an appropriate error status, such as one of the following:

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
The required buffer sizes, in bytes, were successfully returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid compression format was specified via the <i>CompressionFormatAndEngine</i> parameter. If <i>CompressionFormatAndEngine</i> is either COMPRESSION_FORMAT_NONE or COMPRESSION_FORMAT_DEFAULT (but not both), this value is returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUPPORTED_COMPRESSION</b></dt>
</dl>
</td>
<td width="60%">
An invalid compression format was specified via the <i>CompressionFormatAndEngine</i> parameter. If <i>CompressionFormatAndEngine</i> is not one of the following, STATUS_UNSUPPORTED_COMPRESSION is returned:



<ul>
<li>COMPRESSION_FORMAT_LZNT1</li>
<li>COMPRESSION_FORMAT_XPRESS</li>
<li>COMPRESSION_FORMAT_XPRESS_HUFF</li>
<li>COMPRESSION_FORMAT_NONE (in this case, STATUS_INVALID_PARAMETER is returned) 
</li>
<li>COMPRESSION_FORMAT_DEFAULT (in this case, STATUS_INVALID_PARAMETER is returned) </li>
</ul>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
An invalid compression engine was specified via the <i>CompressionFormatAndEngine</i> parameter. If <i>CompressionFormatAndEngine</i> is not COMPRESSION_ENGINE_STANDARD or COMPRESSION_ENGINE_MAXIMUM (but not both), this value is returned.

</td>
</tr>
</table>

## -remarks

The <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcompressbuffer">RtlCompressBuffer</a> and <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldecompressfragment">RtlDecompressFragment</a>functions require an appropriately sized work space buffer to compress and decompress successfully. To determine the correct work space buffer size, in bytes, call the <b>RtlGetCompressionWorkSpaceSize</b> function. 

As an example, the <i>WorkSpace</i> parameter of the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcompressbuffer">RtlCompressBuffer</a> function must point to an adequately sized work space buffer. The <i>CompressBufferWorkSpaceSize</i> parameter of the <b>RtlGetCompressionWorkSpaceSize</b> provides this size.

To compress an uncompressed buffer, use the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcompressbuffer">RtlCompressBuffer</a> function.

To decompress a compressed buffer, use the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldecompressbuffer">RtlDecompressBuffer</a> function.

To decompress only a portion of a compressed buffer (that is, a "fragment" of the buffer), use the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldecompressfragment">RtlDecompressFragment</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_compression_information">FILE_COMPRESSION_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcompressbuffer">RtlCompressBuffer</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldecompressbuffer">RtlDecompressBuffer</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldecompressfragment">RtlDecompressFragment</a>