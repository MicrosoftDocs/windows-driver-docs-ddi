---
UID: NF:ntifs.RtlGetCompressionWorkSpaceSize
title: RtlGetCompressionWorkSpaceSize function (ntifs.h)
description: Learn more about the RtlGetCompressionWorkSpaceSize function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["RtlGetCompressionWorkSpaceSize function"]
ms.keywords: RtlGetCompressionWorkSpaceSize, RtlGetCompressionWorkSpaceSize function [Installable File System Drivers], ifsk.rtlgetcompressionworkspacesize, ntifs/RtlGetCompressionWorkSpaceSize, rtlref_26332738-6278-49f9-b948-87bcb7e68c83.xml
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
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

The **RtlGetCompressionWorkSpaceSize** function is used to determine the correct size of the **WorkSpace** buffer for the [**RtlCompressBuffer**](nf-ntifs-rtlcompressbuffer.md) and [**RtlDecompressFragment**](nf-ntifs-rtldecompressfragment.md) functions.

## -parameters

### -param CompressionFormatAndEngine [in]

Bitmask specifying the compression format and engine type. This parameter must be set to a valid bitwise OR combination of one format type and one engine type. For example, COMPRESSION_FORMAT_LZNT1 | COMPRESSION_ENGINE_STANDARD.

The meanings of these, and other related values, are as follows:

| Value | Meaning |
| ----- | ------- |
| COMPRESSION_FORMAT_NONE        | Not supported by this function. |
| COMPRESSION_FORMAT_DEFAULT     | Not supported by this function. |
| COMPRESSION_FORMAT_LZNT1       | The function will perform LZ compression. |
| COMPRESSION_FORMAT_XPRESS      | The function will perform Xpress compression. |
| COMPRESSION_FORMAT_XPRESS_HUFF | The function will perform Xpress Huffman compression. |
| COMPRESSION_ENGINE_STANDARD    | The **UncompressedBuffer** buffer is compressed using an algorithm that provides a balance between data compression and performance. This value cannot be used with COMPRESSION_ENGINE_MAXIMUM. |
| COMPRESSION_ENGINE_MAXIMUM     | The **UncompressedBuffer** buffer is compressed using an algorithm that provides maximum data compression but with relatively slower performance. This value cannot be used with COMPRESSION_ENGINE_STANDARD. |
| COMPRESSION_ENGINE_HIBER       | Not supported by this function. |

### -param CompressBufferWorkSpaceSize [out]

A pointer to a caller-allocated buffer receiving the size, in bytes, required to compress a buffer. This value is used to determine the correct size of [**RtlCompressBuffer**](nf-ntifs-rtlcompressbuffer.md)'s **WorkSpace** buffer.

### -param CompressFragmentWorkSpaceSize [out]

A pointer to a caller-allocated buffer receiving the size, in bytes, required to decompress a compressed buffer to a fragment. This value is used to determine the correct size of [**RtlDecompressFragment**](nf-ntifs-rtldecompressfragment.md)'s **WorkSpace** buffer. Note that the **RtlCompressFragment** function does not currently exist.

## -returns

**RtlGetCompressionWorkSpaceSize**returns an appropriate error status, such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS | The required buffer sizes, in bytes, were successfully returned. |
| STATUS_INVALID_PARAMETER | An invalid compression format was specified via the **CompressionFormatAndEngine** parameter. If **CompressionFormatAndEngine** is either COMPRESSION_FORMAT_NONE or COMPRESSION_FORMAT_DEFAULT (but not both), this value is returned. |
| STATUS_UNSUPPORTED_COMPRESSION | An invalid compression format was specified via the **CompressionFormatAndEngine** parameter. If **CompressionFormatAndEngine** is not one of the following, STATUS_UNSUPPORTED_COMPRESSION is returned: COMPRESSION_FORMAT_LZNT1, COMPRESSION_FORMAT_XPRESS, COMPRESSION_FORMAT_XPRESS_HUF |
| STATUS_NOT_SUPPORTED | An invalid compression engine was specified via the **CompressionFormatAndEngine** parameter. If **CompressionFormatAndEngine** is not COMPRESSION_ENGINE_STANDARD or COMPRESSION_ENGINE_MAXIMUM (but not both), this value is returned. |

## -remarks

The [**RtlCompressBuffer**](nf-ntifs-rtlcompressbuffer.md) and [**RtlDecompressFragment**](nf-ntifs-rtldecompressfragment.md)functions require an appropriately sized work space buffer to compress and decompress successfully. To determine the correct work space buffer size, in bytes, call the **RtlGetCompressionWorkSpaceSize** function.

As an example, the **WorkSpace** parameter of the [**RtlCompressBuffer**](nf-ntifs-rtlcompressbuffer.md) function must point to an adequately sized work space buffer. The **CompressBufferWorkSpaceSize** parameter of the **RtlGetCompressionWorkSpaceSize** provides this size.

To compress an uncompressed buffer, use the [**RtlCompressBuffer**](nf-ntifs-rtlcompressbuffer.md) function.

To decompress a compressed buffer, use the [**RtlDecompressBuffer**](nf-ntifs-rtldecompressbuffer.md) function.

To decompress only a portion of a compressed buffer (that is, a "fragment" of the buffer), use the [**RtlDecompressFragment**](nf-ntifs-rtldecompressfragment.md) function.

## -see-also

[**FILE_COMPRESSION_INFORMATION**](ns-ntifs-_file_compression_information.md)

[**RtlCompressBuffer**](nf-ntifs-rtlcompressbuffer.md)

[**RtlDecompressBuffer**](nf-ntifs-rtldecompressbuffer.md)

[**RtlDecompressFragment**](nf-ntifs-rtldecompressfragment.md)
