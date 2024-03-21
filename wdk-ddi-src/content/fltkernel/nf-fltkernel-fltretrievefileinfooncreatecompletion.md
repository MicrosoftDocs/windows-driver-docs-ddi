---
UID: NF:fltkernel.FltRetrieveFileInfoOnCreateCompletion
title: FltRetrieveFileInfoOnCreateCompletion function
description: FltRetrieveFileInfoOnCreateCompletion retrieves the requested file information during file post create.
tech.root: ifsk
ms.date: 03/12/2019
keywords: ["FltRetrieveFileInfoOnCreateCompletion function"]
ms.keywords: FltRetrieveFileInfoOnCreateCompletion
req.header: fltkernel.h
req.include-header: 
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
 - FltRetrieveFileInfoOnCreateCompletion
 - fltkernel/FltRetrieveFileInfoOnCreateCompletion
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FltRetrieveFileInfoOnCreateCompletion
---

# FltRetrieveFileInfoOnCreateCompletion function

## -description

**FltRetrieveFileInfoOnCreateCompletion** retrieves the requested file information during file post create. Use [FltRetrieveFileInfoOnCreateCompletionEx](nf-fltkernel-fltretrievefileinfooncreatecompletionex.md) to get an NTSTATUS code along with the requested information.

## -parameters

### -param Filter [in]

Opaque filter pointer that uniquely identifies the minifilter driver.

### -param Data [in]

Pointer to the [FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md) callback data representing the I/O operation.

### -param InfoClass [in]

Flag that indicates the type of information to return. Note that flags cannot be combined. Can be one of the following values:

| Flag | Meaning |
| ---- | ------- |
| **QoCFileStatInformation** (0x00000001) | The file system will return file stat information in a [**QUERY_ON_CREATE_FILE_STAT_INFORMATION**](../ntifs/ns-ntifs-query_on_create_file_stat_information.md) structure. |
| **QoCFileLxInformation** (0x00000002) | The file system will return extended Linux-like information in a [**QUERY_ON_CREATE_FILE_LX_INFORMATION**](../ntifs/ns-ntifs-query_on_create_file_lx_information.md) structure. |
| **QoCFileEaInformation** (0x00000004) | The file system will return extended attributes (EA) in a [**QUERY_ON_CREATE_EA_INFORMATION**](../ntifs/ns-ntifs-query_on_create_ea_information.md) structure. |
| **QoCFileUsnInformation** (0x00000008) | The file system will return USN information in a [**QUERY_ON_CREATE_USN_INFORMATION**](../ntifs/ns-ntifs-query_on_create_usn_information.md) structure. |
| **QoCFileSecurityInformation** (0x00000010) | The file system will return file security information in a [**QUERY_ON_CREATE_SECURITY_INFORMATION**](../ntifs/ns-ntifs-query_on_create_security_information.md) structure. |

### -param Size [out]

Pointer to a ULONG that specifies the size, in bytes, of the buffer that this function returns.

## -returns

**FltRetrieveFileInfoOnCreateCompletion** returns a pointer to a buffer with the requested file information. The structure within the buffer is determined by the value of *InfoClass*. If the file system processes the request but can't find the requested file information, this parameter is set to NULL.

## -remarks

A minifilter must call **FltRequestFileInfoOnCreateCompletion** during file pre-create to specify which file information the file system should track.

## -see-also

[FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md)

[FltRequestFileInfoOnCreateCompletion](nf-fltkernel-fltrequestfileinfooncreatecompletion.md)

[FltRetrieveFileInfoOnCreateCompletionEx](nf-fltkernel-fltretrievefileinfooncreatecompletionex.md)

