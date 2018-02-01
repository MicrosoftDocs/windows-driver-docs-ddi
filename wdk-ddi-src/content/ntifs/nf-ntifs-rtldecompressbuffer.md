---
UID: NF:ntifs.RtlDecompressBuffer
title: RtlDecompressBuffer function
author: windows-driver-content
description: The RtlDecompressBuffer function decompresses an entire compressed buffer.
old-location: ifsk\rtldecompressbuffer.htm
old-project: ifsk
ms.assetid: 4f82d094-e6be-4367-9146-1fa3f200ffa0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: COMPRESSION_FORMAT_XPRESS, COMPRESSION_FORMAT_NONE, COMPRESSION_FORMAT_DEFAULT, rtlref_d19521fb-b086-4ee4-ae65-6354a89aeff9.xml, ifsk.rtldecompressbuffer, RtlDecompressBuffer function [Installable File System Drivers], RtlDecompressBuffer, COMPRESSION_FORMAT_LZNT1, ntifs/RtlDecompressBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting in Windows XP.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlDecompressBuffer
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlDecompressBuffer function


## -description


The <b>RtlDecompressBuffer</b> function decompresses an entire compressed buffer.


## -syntax


````
NTSTATUS RtlDecompressBuffer(
  _In_  USHORT CompressionFormat,
  _Out_ PUCHAR UncompressedBuffer,
  _In_  ULONG  UncompressedBufferSize,
  _In_  PUCHAR CompressedBuffer,
  _In_  ULONG  CompressedBufferSize,
  _Out_ PULONG FinalUncompressedSize
);
````


## -parameters




### -param CompressionFormat [in]

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
</table> 


### -param UncompressedBuffer [out]

A pointer to a caller-allocated buffer (allocated from paged or non-paged pool) that receives the decompressed data from <i>CompressedBuffer</i>. This parameter is required and cannot be <b>NULL</b>.


### -param UncompressedBufferSize [in]

The size, in bytes, of the <i>UncompressedBuffer</i>  buffer.


### -param CompressedBuffer [in]

A pointer to the buffer that contains the data to decompress. This parameter is required and cannot be <b>NULL</b>.


### -param CompressedBufferSize [in]

The size, in bytes, of the <i>CompressedBuffer</i>  buffer.


### -param FinalUncompressedSize [out]

A pointer to a caller-allocated variable that receives the size, in bytes, of the decompressed data stored in <i>UncompressedBuffer</i>. This parameter is required and cannot be <b>NULL</b>.


## -returns


<b>RtlDecompressBuffer</b> returns an appropriate error status value, such as one of the following.
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


The <b>RtlDecompressBuffer</b> function takes as input an entire compressed buffer and produces its decompressed equivalent provided that the uncompressed data fits within the specified destination buffer.

To decompress only a portion of a compressed buffer (that is, a "fragment" of the buffer), use the <a href="..\ntifs\nf-ntifs-rtldecompressfragment.md">RtlDecompressFragment</a> function.

To compress an uncompressed buffer, use the <a href="..\ntifs\nf-ntifs-rtlcompressbuffer.md">RtlCompressBuffer</a> function.



## -see-also

<a href="..\ntifs\nf-ntifs-rtldecompressfragmentex.md">RtlDecompressFragmentEx</a>

<a href="..\ntifs\nf-ntifs-rtldecompressbufferex.md">RtlDecompressBufferEx</a>

<a href="..\ntifs\nf-ntifs-rtlcompressbuffer.md">RtlCompressBuffer</a>

<a href="..\ntifs\nf-ntifs-rtldecompressbufferex2.md">RtlDecompressBufferEx2</a>

<a href="..\ntifs\ns-ntifs-_file_compression_information.md">FILE_COMPRESSION_INFORMATION</a>

<a href="..\ntifs\nf-ntifs-rtldecompressfragment.md">RtlDecompressFragment</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlDecompressBuffer function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

