---
UID: NF:ntifs.RtlGetCompressionWorkSpaceSize
title: RtlGetCompressionWorkSpaceSize function
author: windows-driver-content
description: The RtlGetCompressionWorkSpaceSize function is used to determine the correct size of the WorkSpace buffer for the RtlCompressBuffer and RtlDecompressFragment functions.
old-location: ifsk\rtlgetcompressionworkspacesize.htm
old-project: ifsk
ms.assetid: f0e856f8-9c01-4219-b521-ab4a5c9bc35c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlGetCompressionWorkSpaceSize, RtlGetCompressionWorkSpaceSize function [Installable File System Drivers], ifsk.rtlgetcompressionworkspacesize, ntifs/RtlGetCompressionWorkSpaceSize, rtlref_26332738-6278-49f9-b948-87bcb7e68c83.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlGetCompressionWorkSpaceSize
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlGetCompressionWorkSpaceSize function


## -description


The <b>RtlGetCompressionWorkSpaceSize</b> function is used to determine the correct size of the <i>WorkSpace</i> buffer for the <a href="..\ntifs\nf-ntifs-rtlcompressbuffer.md">RtlCompressBuffer</a> and <a href="..\ntifs\nf-ntifs-rtldecompressfragment.md">RtlDecompressFragment</a> functions.


## -syntax


````
NTSTATUS RtlGetCompressionWorkSpaceSize(
  _In_  USHORT CompressionFormatAndEngine,
  _Out_ PULONG CompressBufferWorkSpaceSize,
  _Out_ PULONG CompressFragmentWorkSpaceSize
);
````


## -parameters




### -param CompressionFormatAndEngine [in]

Bitmask specifying the compression format and engine type. This parameter must be set to one of the following bitwise OR combinations:

<ul>
<li>
COMPRESSION_FORMAT_LZNT1 | COMPRESSION_ENGINE_STANDARD

</li>
<li>
COMPRESSION_FORMAT_LZNT1 | COMPRESSION_ENGINE_MAXIMUM

</li>
</ul>
The meanings of these, and other related values, are as follows:

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
<tr>
<td>
COMPRESSION_ENGINE_STANDARD

</td>
<td>
Data is compressed using an algorithm which provides a balance between data compression and performance. This value cannot be used with COMPRESSION_ENGINE_MAXIMUM.

</td>
</tr>
<tr>
<td>
COMPRESSION_ENGINE_MAXIMUM

</td>
<td>
Data is compressed using an algorithm which provides maximum data compression but with relatively slower performance. This value cannot be used with COMPRESSION_ENGINE_STANDARD.

</td>
</tr>
<tr>
<td>
COMPRESSION_ENGINE_HIBER

</td>
<td>
Not supported by this function.

</td>
</tr>
</table>
 


### -param CompressBufferWorkSpaceSize [out]

A pointer to a caller-allocated buffer receiving the size, in bytes, required to compress a buffer. This value is used to determine the correct size of <a href="..\ntifs\nf-ntifs-rtlcompressbuffer.md">RtlCompressBuffer</a>'s <i>WorkSpace</i> buffer.


### -param CompressFragmentWorkSpaceSize [out]

A pointer to a caller-allocated buffer receiving the size, in bytes, required to decompress a compressed buffer to a fragment. This value is used to determine the correct size of <a href="..\ntifs\nf-ntifs-rtldecompressfragment.md">RtlDecompressFragment</a>'s <i>WorkSpace</i> buffer. Note that the <b>RtlCompressFragment</b> function does not currently exist.


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
<li>COMPRESSION_FORMAT_LZNT1 </li>
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



The <a href="..\ntifs\nf-ntifs-rtlcompressbuffer.md">RtlCompressBuffer</a> and <a href="..\ntifs\nf-ntifs-rtldecompressfragment.md">RtlDecompressFragment</a>functions require an appropriately sized work space buffer to compress and decompress successfully. To determine the correct work space buffer size, in bytes, call the <b>RtlGetCompressionWorkSpaceSize</b> function. 

As an example, the <i>WorkSpace</i> parameter of the <a href="..\ntifs\nf-ntifs-rtlcompressbuffer.md">RtlCompressBuffer</a> function must point to an adequately sized work space buffer. The <i>CompressBufferWorkSpaceSize</i> parameter of the <b>RtlGetCompressionWorkSpaceSize</b> provides this size.

To compress an uncompressed buffer, use the <a href="..\ntifs\nf-ntifs-rtlcompressbuffer.md">RtlCompressBuffer</a> function.

To decompress a compressed buffer, use the <a href="..\ntifs\nf-ntifs-rtldecompressbuffer.md">RtlDecompressBuffer</a> function.

To decompress only a portion of a compressed buffer (that is, a "fragment" of the buffer), use the <a href="..\ntifs\nf-ntifs-rtldecompressfragment.md">RtlDecompressFragment</a> function.




## -see-also

<a href="..\ntifs\nf-ntifs-rtlcompressbuffer.md">RtlCompressBuffer</a>



<a href="..\ntifs\nf-ntifs-rtldecompressbuffer.md">RtlDecompressBuffer</a>



<a href="..\ntifs\nf-ntifs-rtldecompressfragment.md">RtlDecompressFragment</a>



<a href="..\ntifs\ns-ntifs-_file_compression_information.md">FILE_COMPRESSION_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlGetCompressionWorkSpaceSize function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

