---
UID: NF:ntifs.RtlDecompressFragment
title: RtlDecompressFragment function (ntifs.h)
description: Learn more about the RtlDecompressFragment function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["RtlDecompressFragment function"]
ms.keywords: RtlDecompressFragment, RtlDecompressFragment function [Installable File System Drivers], ifsk.rtldecompressfragment, ntifs/RtlDecompressFragment, rtlref_40a25add-c5bc-40f5-bb79-d5dcd6c11d69.xml
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
 - RtlDecompressFragment
 - ntifs/RtlDecompressFragment
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlDecompressFragment
---

# RtlDecompressFragment function

## -description

The **RtlDecompressFragment** function is used to decompress part of a compressed buffer (that is, a buffer "fragment").

## -parameters

### -param CompressionFormat [in]

Bitmask specifying the compression format of the compressed buffer. This parameter must be set to COMPRESSION_FORMAT_LZNT1. The meaning of this and other related compression format values are as follows:

| Value | Meaning |
| ----- | ------- |
| COMPRESSION_FORMAT_NONE    | Not supported by this function. |
| COMPRESSION_FORMAT_DEFAULT | Not supported by this function. |
| COMPRESSION_FORMAT_LZNT1   | Specifies that compression should be performed. This value is required. |

### -param UncompressedFragment [out]

Pointer to a caller-allocated buffer (allocated from paged or non-paged pool) receiving the decompressed data from **CompressedBuffer**. This parameter is required and cannot be NULL.

### -param UncompressedFragmentSize [in]

The size, in bytes, of the **UncompressedFragment** buffer.

### -param CompressedBuffer [in]

A pointer to the buffer containing the data to decompress. This parameter is required and cannot be NULL.

### -param CompressedBufferSize [in]

The size, in bytes, of the **CompressedBuffer** buffer.

### -param FragmentOffset [in]

The zero-based offset, in bytes, where the uncompressed fragment is being extract from. This offset value is the position within the original uncompressed buffer.

### -param FinalUncompressedSize [out]

A pointer to a caller-allocated variable which receives the size, in bytes, of the decompressed data stored in **UncompressedFragment**. This parameter is required and cannot be NULL.

### -param WorkSpace [in]

A pointer to a caller-allocated work space buffer used by the **RtlDecompressFragment** function during decompression. Use the [**RtlGetCompressionWorkSpaceSize**](nf-ntifs-rtlgetcompressionworkspacesize.md) function to determine the correct work space buffer size.

## -returns

**RtlDecompressFragment**returns an appropriate NTSTATUS code, such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS                 | The **CompressedBuffer** buffer was successfully decompressed into **UncompressedFragment**. |
| STATUS_INVALID_PARAMETER       | An invalid compression format was specified via the **CompressionFormat** parameter. If **CompressionFormat** is either COMPRESSION_FORMAT_NONE or COMPRESSION_FORMAT_DEFAULT (but not both), this value is returned. |
| STATUS_UNSUPPORTED_COMPRESSION | An invalid compression format was specified via the **CompressionFormat** parameter. If **CompressionFormat** is not one of the following, STATUS_UNSUPPORTED_COMPRESSION is returned: COMPRESSION_FORMAT_LZNT1 |
| STATUS_BAD_COMPRESSION_BUFFER  | **UncompressedFragment** is not large enough to contain the uncompressed data. |

## -remarks

Relative to the [**RtlDecompressBuffer**](nf-ntifs-rtldecompressbuffer.md) function, **RtlDecompressFragment** is used for decompressing a portion of the data from a compressed buffer (as opposed to the entire buffer).

To determine the correct buffer size for the **WorkSpace** parameter, use the [**RtlGetCompressionWorkSpaceSize**](nf-ntifs-rtlgetcompressionworkspacesize.md) function (that is, the value returned by the **RtlGetCompressionWorkSpaceSize** parameter).

To compress an uncompressed buffer, use the [**RtlCompressBuffer**](nf-ntifs-rtlcompressbuffer.md) function.

To decompress an entire compressed buffer, use the [**RtlDecompressBuffer**](nf-ntifs-rtldecompressbuffer.md) function.

## -see-also

[**FILE_COMPRESSION_INFORMATION**](ns-ntifs-_file_compression_information.md)

[**RtlCompressBuffer**](nf-ntifs-rtlcompressbuffer.md)

[**RtlDecompressBuffer**](nf-ntifs-rtldecompressbuffer.md)

[**RtlDecompressBufferEx**](nf-ntifs-rtldecompressbufferex.md)

[**RtlDecompressBufferEx2**](nf-ntifs-rtldecompressbufferex2.md)

[**RtlDecompressFragmentEx**](nf-ntifs-rtldecompressfragmentex.md)
