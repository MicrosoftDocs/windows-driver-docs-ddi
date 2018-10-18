---
UID: NF:ntifs.RtlDecompressFragment
title: RtlDecompressFragment function
author: windows-driver-content
description: The RtlDecompressFragment function is used to decompress part of a compressed buffer (that is, a buffer &#0034;fragment&#0034;).
old-location: ifsk\rtldecompressfragment.htm
tech.root: ifsk
ms.assetid: 80450bfb-ae3a-46cd-8cf2-905df5adf70d
ms.date: 4/16/2018
ms.keywords: RtlDecompressFragment, RtlDecompressFragment function [Installable File System Drivers], ifsk.rtldecompressfragment, ntifs/RtlDecompressFragment, rtlref_40a25add-c5bc-40f5-bb79-d5dcd6c11d69.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlDecompressFragment
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlDecompressFragment function


## -description


The <b>RtlDecompressFragment</b> function is used to decompress part of a compressed buffer (that is, a buffer "fragment").


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

A pointer to a caller-allocated work space buffer used by the <b>RtlDecompressFragment</b> function during decompression. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552291">RtlGetCompressionWorkSpaceSize</a> function to determine the correct work space buffer size.


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



Relative to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552191">RtlDecompressBuffer</a> function, <b>RtlDecompressFragment</b> is used for decompressing a portion of the data from a compressed buffer (as opposed to the entire buffer). 

To determine the correct buffer size for the <i>WorkSpace</i> parameter, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552291">RtlGetCompressionWorkSpaceSize</a> function (that is, the value returned by the <b>RtlGetCompressionWorkSpaceSize</b> parameter).

To compress an uncompressed buffer, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552127">RtlCompressBuffer</a> function.

To decompress an entire compressed buffer, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552191">RtlDecompressBuffer</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540239">FILE_COMPRESSION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552127">RtlCompressBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552191">RtlDecompressBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439511">RtlDecompressBufferEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt426737">RtlDecompressBufferEx2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt426738">RtlDecompressFragmentEx</a>
 

 

