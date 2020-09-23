---
UID: NF:fltkernel.FltRequestFileInfoOnCreateCompletion
title: FltRequestFileInfoOnCreateCompletion function
description: A minifilter calls FltRequestFileInfoOnCreateCompletion during file pre-create to request that the file manager stores the specified file information for retrieval upon create complete.
tech.root: ifsk
ms.assetid: d33f4ab5-9f50-42d6-8944-0836e090a67a
ms.author: windowsdriverdev
ms.date: 01/11/2019
keywords: ["FltRequestFileInfoOnCreateCompletion function"]
ms.keywords: FltRequestFileInfoOnCreateCompletion, FltRetrieveFileInfoOnCreateCompletion, FltRetrieveFileInfoOnCreateCompletionEx
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - FltRequestFileInfoOnCreateCompletion
 - fltkernel/FltRequestFileInfoOnCreateCompletion
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FltRequestFileInfoOnCreateCompletion
product:
 - Windows
---

# FltRequestFileInfoOnCreateCompletion function


## -description

A minifilter calls **FltRequestFileInfoOnCreateCompletion** during file pre-create to request that the file manager store file information for retrieval during post create.

## -parameters

### -param Filter

Opaque filter pointer that uniquely identifies the minifilter driver.

### -param Data

Pointer to the [FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md) callback data representing the I/O create operation.

### -param InfoClassFlags

Flag bitmask indicating the type of file information that the file system should store for retrieval during post create. Can be any combination of the following flags:

| Flag | Meaning |
| ---- | ------- |
| **QoCFileStatInformation** (0x00000001) | If set, the file system will store file stat information in a QUERY_ON_CREATE_FILE_STAT_INFORMATION structure for retrieval. |
| **QoCFileLxInformation** (0x00000002) | If set, the file system will store extended Linux-like information in a QUERY_ON_CREATE_FILE_LX_INFORMATION structure for retrieval. |
| **QoCFileEaInformation** (0x00000004) | If set, the file system will store extended attributes (EA) in a QUERY_ON_CREATE_EA_INFORMATION structure for retrieval. |

## -returns

**FltRequestFileInfoOnCreateCompletion** can return one of the following values:

| Return code | Description |
| ----------- | ----------- |
| **STATUS_SUCCESS** | The file system successfully stored the requested file information. |
| **STATUS_INSUFFICIENT_RESOURCES** | **FltRequestFileInfoOnCreateCompletion** was unable to allocate sufficient memory in which to store the requested file information. |
| **STATUS_INVALID_PARAMETER_2** | The provided callback data object was not an IRP-based create operation. |

## -remarks

The minifilter can retrieve the file information by calling [**FltRetrieveFileInfoOnCreateCompletionEx**](nf-fltkernel-fltretrievefileinfooncreatecompletionex.md) or [**FltRetrieveFileInfoOnCreateCompletion**](nf-fltkernel-fltretrievefileinfooncreatecompletion.md) during post create. A minifilter's performance is typically better when it requests and retrieves file information in this manner, rather than querying file information at a later time.

## -see-also

[FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md)

[**FltRetrieveFileInfoOnCreateCompletion**](nf-fltkernel-fltretrievefileinfooncreatecompletion.md)

[**FltRetrieveFileInfoOnCreateCompletionEx**](nf-fltkernel-fltretrievefileinfooncreatecompletionex.md)

