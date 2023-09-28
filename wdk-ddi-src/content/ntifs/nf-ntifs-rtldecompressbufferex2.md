---
UID: NF:ntifs.RtlDecompressBufferEx2
title: RtlDecompressBufferEx2 function (ntifs.h)
description: Learn more about the RtlDecompressBufferEx2 function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["RtlDecompressBufferEx2 function"]
ms.keywords: COMPRESSION_FORMAT_DEFAULT, COMPRESSION_FORMAT_LZNT1, COMPRESSION_FORMAT_NONE, COMPRESSION_FORMAT_XPRESS, COMPRESSION_FORMAT_XPRESS_HUFF, RtlDecompressBufferEx2, RtlDecompressBufferEx2 function [Installable File System Drivers], ifsk.rtldecompressbufferex2, ntifs/RtlDecompressBufferEx2
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
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
 - RtlDecompressBufferEx2
 - ntifs/RtlDecompressBufferEx2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlDecompressBufferEx2
---

# RtlDecompressBufferEx2 function

## -description

The **RtlDecompressBufferEx2** function decompresses an entire compressed buffer, using multiple processors where possible. Multiple processor support is only implemented for kernel mode callers.

## -parameters

### -param CompressionFormat [in]

A bitmask that specifies the compression format of the compressed buffer. This parameter must be set to COMPRESSION_FORMAT_LZNT1. The meaning of this and other related compression format values are as follows.

| Value | Meaning |
| ----- | ------- |
| COMPRESSION_FORMAT_NONE        | Not supported by this function. |
| COMPRESSION_FORMAT_DEFAULT     | Not supported by this function. |
| COMPRESSION_FORMAT_LZNT1       | The function will perform LZ compression. |
| COMPRESSION_FORMAT_XPRESS      | The function will perform Xpress compression. |
| COMPRESSION_FORMAT_XPRESS_HUFF | The function will perform Xpress Huffman decompression. |

### -param UncompressedBuffer [out]

A pointer to a caller-allocated buffer (allocated from a  paged or non-paged pool) that receives the decompressed data from **CompressedBuffer**. This parameter is required and cannot be NULL.

### -param UncompressedBufferSize [in]

The size, in bytes, of the **UncompressedBuffer** buffer.

### -param CompressedBuffer [in]

A pointer to the buffer that contains the data to decompress. This parameter is required and cannot be NULL.

### -param CompressedBufferSize [in]

The size, in bytes, of the **CompressedBuffer** buffer.

### -param UncompressedChunkSize [in]

The size, in bytes, of each chunk within the compression buffer.  Valid values are 512, 1024, 2048 and 4096.

### -param FinalUncompressedSize [out]

A pointer to a caller-allocated variable that receives the size, in bytes, of the decompressed data stored in **UncompressedBuffer**. This parameter is required and cannot be NULL.

### -param WorkSpace [in, optional]

A pointer to a caller-allocated work space buffer used by the **RtlDecompressBufferEx2** function during decompression. Use the [**RtlGetCompressionWorkSpaceSize**](nf-ntifs-rtlgetcompressionworkspacesize.md) function to determine the correct work space buffer size.

## -returns

**RtlDecompressBufferEx2** returns an appropriate error status value, such as one of the following.

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS           | The **CompressedBuffer** buffer was successfully decompressed. |
| STATUS_INVALID_PARAMETER | An invalid compression format was specified through the **CompressionFormat** parameter. If **CompressionFormat** is either COMPRESSION_FORMAT_NONE or COMPRESSION_FORMAT_DEFAULT (but not both), this value is returned. |
| STATUS_UNSUPPORTED_COMPRESSION | An invalid compression format was specified through the **CompressionFormat** parameter. If **CompressionFormat** is not one of the following, STATUS_UNSUPPORTED_COMPRESSION is returned: COMPRESSION_FORMAT_LZNT1, COMPRESSION_FORMAT_XPRESS, COMPRESSION_FORMAT_XPRESS_HUFF,  COMPRESSION_FORMAT_NONE, COMPRESSION_FORMAT_DEFAULT |
| STATUS_BAD_COMPRESSION_BUFFER | **UncompressedBuffer** is not large enough to contain the uncompressed data. |

## -remarks

The **RtlDecompressBufferEx2** function takes as input an entire compressed buffer and produces its decompressed equivalent provided that the uncompressed data fits within the specified destination buffer.

To decompress only a portion of a compressed buffer (that is, a "fragment" of the buffer), use the [**RtlDecompressFragment**](nf-ntifs-rtldecompressfragment.md) function.

To compress an uncompressed buffer, use the [**RtlCompressBuffer**](nf-ntifs-rtlcompressbuffer.md) function.

## -see-also

<[**FILE_COMPRESSION_INFORMATION**](ns-ntifs-_file_compression_information.md)

[**RtlCompressBuffer**](nf-ntifs-rtlcompressbuffer.md)

[**RtlDecompressBuffer**](nf-ntifs-rtldecompressbuffer.md)

[**RtlDecompressBufferEx**](nf-ntifs-rtldecompressbufferex.md)

[**RtlDecompressFragment**](nf-ntifs-rtldecompressfragment.md)

[**RtlDecompressFragmentEx**](nf-ntifs-rtldecompressfragmentex.md)
