---
UID: NF:ntifs.RtlDecompressFragment
title: RtlDecompressFragment function
author: windows-driver-content
description: The RtlDecompressFragment function is used to decompress part of a compressed buffer (that is, a buffer &#0034;fragment&#0034;).
old-location: ifsk\rtldecompressfragment.htm
old-project: ifsk
ms.assetid: 80450bfb-ae3a-46cd-8cf2-905df5adf70d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.rtldecompressfragment, RtlDecompressFragment function [Installable File System Drivers], ntifs/RtlDecompressFragment, RtlDecompressFragment, rtlref_40a25add-c5bc-40f5-bb79-d5dcd6c11d69.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of all Windows operating systems.
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
-	RtlDecompressFragment
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlDecompressFragment function


## -description


The <b>RtlDecompressFragment</b> function is used to decompress part of a compressed buffer (that is, a buffer "fragment").


## -syntax


````
NTSTATUS RtlDecompressFragment(
  _In_  USHORT CompressionFormat,
  _Out_ PUCHAR UncompressedFragment,
  _In_  ULONG  UncompressedFragmentSize,
  _In_  PUCHAR CompressedBuffer,
  _In_  ULONG  CompressedBufferSize,
  _In_  ULONG  FragmentOffset,
  _Out_ PULONG FinalUncompressedSize,
  _In_  PVOID  WorkSpace
);
````


## -parameters




### -param CompressionFormat [in]

Bitmask specifying the compression format of the compressed buffer. This parameter must be set to COMPRESSION_FORMAT_LZNT1. The meaning of this and other related compression format values are as follows:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
COMPRESSION_FORMAT_NONE

</td>
<td>
Not supported by this function.

</td>
</tr>
<tr>
<td>
COMPRESSION_FORMAT_DEFAULT

</td>
<td>
Not supported by this function.

</td>
</tr>
<tr>
<td>
COMPRESSION_FORMAT_LZNT1

</td>
<td>
Specifies that compression should be performed. This value is required.

</td>
</tr>
</table> 


### -param UncompressedFragment [out]

Pointer to a caller-allocated buffer (allocated from paged or non-paged pool) receiving the decompressed data from <i>CompressedBuffer</i>. This parameter is required and cannot be <b>NULL</b>.


### -param UncompressedFragmentSize [in]

The size, in bytes, of the <i>UncompressedFragment</i> buffer.


### -param CompressedBuffer [in]

A pointer to the buffer containing the data to decompress. This parameter is required and cannot be <b>NULL</b>.


### -param CompressedBufferSize [in]

The size, in bytes, of the <i>CompressedBuffer</i> buffer.


### -param FragmentOffset [in]

The zero-based offset, in bytes, where the uncompressed fragment is being extract from. This offset value is the position within the original uncompressed buffer.


### -param FinalUncompressedSize [out]

A pointer to a caller-allocated variable which receives the size, in bytes, of the decompressed data stored in <i>UncompressedFragment</i>. This parameter is required and cannot be <b>NULL</b>.


### -param WorkSpace [in]

A pointer to a caller-allocated work space buffer used by the <b>RtlDecompressFragment</b> function during decompression. Use the <a href="..\ntifs\nf-ntifs-rtlgetcompressionworkspacesize.md">RtlGetCompressionWorkSpaceSize</a> function to determine the correct work space buffer size.


## -returns


<b>RtlDecompressFragment</b>returns an appropriate error status, such as one of the following:
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
The <i>CompressedBuffer</i> buffer was successfully decompressed into <i>UncompressedFragment</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid compression format was specified via the <i>CompressionFormat</i> parameter. If <i>CompressionFormat</i> is either COMPRESSION_FORMAT_NONE or COMPRESSION_FORMAT_DEFAULT (but not both), this value is returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUPPORTED_COMPRESSION</b></dt>
</dl>
</td>
<td width="60%">
An invalid compression format was specified via the <i>CompressionFormat</i> parameter. If <i>CompressionFormat</i> is not one of the following, STATUS_UNSUPPORTED_COMPRESSION is returned:

<ul>
<li>COMPRESSION_FORMAT_LZNT1</li>
<li>COMPRESSION_FORMAT_NONE (in this case, STATUS_INVALID_PARAMETER is returned).</li>
<li>COMPRESSION_FORMAT_DEFAULT (in this case, STATUS_INVALID_PARAMETER is returned). </li>
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
<i>UncompressedFragment</i> is not large enough to contain the uncompressed data.

</td>
</tr>
</table> 



## -remarks


Relative to the <a href="..\ntifs\nf-ntifs-rtldecompressbuffer.md">RtlDecompressBuffer</a> function, <b>RtlDecompressFragment</b> is used for decompressing a portion of the data from a compressed buffer (as opposed to the entire buffer). 

To determine the correct buffer size for the <i>WorkSpace</i> parameter, use the <a href="..\ntifs\nf-ntifs-rtlgetcompressionworkspacesize.md">RtlGetCompressionWorkSpaceSize</a> function (that is, the value returned by the <b>RtlGetCompressionWorkSpaceSize</b> parameter).

To compress an uncompressed buffer, use the <a href="..\ntifs\nf-ntifs-rtlcompressbuffer.md">RtlCompressBuffer</a> function.

To decompress an entire compressed buffer, use the <a href="..\ntifs\nf-ntifs-rtldecompressbuffer.md">RtlDecompressBuffer</a> function.



## -see-also

<a href="..\ntifs\nf-ntifs-rtldecompressfragmentex.md">RtlDecompressFragmentEx</a>

<a href="..\ntifs\nf-ntifs-rtldecompressbufferex.md">RtlDecompressBufferEx</a>

<a href="..\ntifs\nf-ntifs-rtldecompressbuffer.md">RtlDecompressBuffer</a>

<a href="..\ntifs\ns-ntifs-_file_compression_information.md">FILE_COMPRESSION_INFORMATION</a>

<a href="..\ntifs\nf-ntifs-rtlcompressbuffer.md">RtlCompressBuffer</a>

<a href="..\ntifs\nf-ntifs-rtldecompressbufferex2.md">RtlDecompressBufferEx2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlDecompressFragment function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

