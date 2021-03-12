---
UID: NF:fltkernel.FltRetrieveFileInfoOnCreateCompletionEx
title: FltRetrieveFileInfoOnCreateCompletionEx function
description: FltRetrieveFileInfoOnCreateCompletionEx queries for the specified file information upon file creation completion.
tech.root: ifsk
ms.date: 03/11/2021
keywords: ["FltRetrieveFileInfoOnCreateCompletionEx function"]
ms.keywords: FltRetrieveFileInfoOnCreateCompletionEx, FltRetrieveFileInfoOnCreateCompletion
req.header: fltkernel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
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
ms.custom: 19H1
f1_keywords:
 - FltRetrieveFileInfoOnCreateCompletionEx
 - fltkernel/FltRetrieveFileInfoOnCreateCompletionEx
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FltRetrieveFileInfoOnCreateCompletionEx
product:
 - Windows
dev_langs:
 - c++
---

# FltRetrieveFileInfoOnCreateCompletionEx function

## -description

**FltRetrieveFileInfoOnCreateCompletionEx** queries for the specified file information upon file creation completion.

## -parameters

### -param Filter

[in] Opaque filter pointer that uniquely identifies the minifilter driver. It is returned by [**FltRegisterFilter**](nf-fltkernel-fltregisterfilter.md), and remains constant as long as the minifilter driver is loaded.

### -param Data

[in] Pointer to the [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md) callback data representing the I/O operation.

### -param InfoClass

[in] Flag that indicates the type of file information to return. Note that flags cannot be combined. Can be one of the following values:

| Flag | Meaning |
| ---- | ------- |
| **QoCFileStatInformation** (0x00000001) | The file system will return file stat information in a [**QUERY_ON_CREATE_FILE_STAT_INFORMATION**](../ntifs/ns-ntifs-query_on_create_file_stat_information.md) structure. |
| **QoCFileLxInformation** (0x00000002) | The file system will return extended Linux-like information in a [**QUERY_ON_CREATE_FILE_LX_INFORMATION**](../ntifs/ns-ntifs-query_on_create_file_lx_information.md) structure. |
| **QoCFileEaInformation** (0x00000004) | The file system will return extended attributes (EA) in a [**QUERY_ON_CREATE_EA_INFORMATION**](../ntifs/ns-ntifs-query_on_create_ea_information.md) structure. |

### -param RetInfoSize

[out] Pointer to a ULONG that receives the size, in bytes, of the buffer that **RetInfoBuffer** points to.

### -param RetInfoBuffer

[out] Receives a pointer to the requested **InfoClass** structure. If the file system is able to process the request but can't find the requested file information, this parameter is set to NULL.

## -returns

| Return code | Description |
| ----------- | ----------- |
| **STATUS_SUCCESS** | The file system successfully returned the requested file information. |
| **STATUS_NOT_FOUND** | The file system processed the request, but the requested information was not present on the file, or the file system does not recognize the information request in *InfoClass*. The caller should not use traditional file system APIs to request the information. |
| **STATUS_NOT_SUPPORTED** | The file system was unable to retrieve the requested information. This error occurs when the file system doesn't support the information request or associated ECP, or because [**FltRequestFileInfoOnCreateCompletion**](nf-fltkernel-fltrequestfileinfooncreatecompletion.md) wasn't called during file pre-creation. The caller should instead use traditional file system APIs to retry requesting the information. |
| **STATUS_UNSUCCESSFUL** | The file system received an error while trying to retrieve the requested information. The caller can try requesting the information by way of normal file system APIs, but that will likely fail. |

## -remarks

[**FltRequestFileInfoOnCreateCompletion**](nf-fltkernel-fltrequestfileinfooncreatecompletion.md) and **FltRetrieveFileInfoOnCreateCompletionEx** allow a minifilter to get information about a file during file create, thus avoiding the performance cost of a later query that would require a stack traversal.

- In pre-create, the minifilter makes one call to [**FltRequestFileInfoOnCreateCompletion**](nf-fltkernel-fltrequestfileinfooncreatecompletion.md) with a combination of input **InfoClassFlags** that identify the requested information.
- The file system allocates the appropriate structure(s) and fills in the requested information, if supported, while it processes the create.
- In post-create, the minifilter calls **FltRetrieveFileInfoOnCreateCompletionEx** to get the information it requested in the pre-create call. If the minifilter requested more than one info type, it must call **FltRetrieveFileInfoOnCreateCompletionEx** once for each info type. For example:

``` C

// Pre-create:
NTSTATUS status;
status = FltRequestFileInfoOnCreateCompletion( Filter,
                                               CallbackData,
                                               QoCFileStatInformation | QoCFileLxInformation | QoCFileEaInformation );

// Post-create:
NTSTATUS status;
ULONG fileStatSize, fileLxSize, fileEaSize;
QUERY_ON_CREATE_FILE_STAT_INFORMATION* fileStatInfo;
QUERY_ON_CREATE_FILE_LX_INFORMATION* fileLxInfo;
QUERY_ON_CREATE_EA_INFORMATION* fileEaInfo;

status = FltRetrieveFileInfoOnCreateCompletionEx( Filter,
                                                  CallbackData,
                                                  QoCFileStatInformation,
                                                  &fileStatSize,
                                                  &fileStatInfo );
status = FltRetrieveFileInfoOnCreateCompletionEx( Filter,
                                                  CallbackData,
                                                  QoCFileLxInformation,
                                                  &fileLxSize,
                                                  &fileLxInfo );
status = FltRetrieveFileInfoOnCreateCompletionEx( Filter,
                                                  CallbackData,
                                                  QoCFileEaInformation, 
                                                  &fileEaSize, 
                                                  &fileEaInfo );
```

Once **FltRetrieveFileInfoOnCreateCompletionEx** returns, a minifilter can write into the buffer that **RetInfoBuffer** points to. Any filters above that minifilter will see the changes if they call **FltRetrieveFileInfoOnCreateCompletionEx** on the modified information type.

## -see-also

[**ECP_LIST**](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85))

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FltRequestFileInfoOnCreateCompletion**](nf-fltkernel-fltrequestfileinfooncreatecompletion.md)

[**QUERY_ON_CREATE_EA_INFORMATION**](../ntifs/ns-ntifs-query_on_create_ea_information.md)

[**QUERY_ON_CREATE_FILE_STAT_INFORMATION**](../ntifs/ns-ntifs-query_on_create_file_stat_information.md)

[**QUERY_ON_CREATE_FILE_LX_INFORMATION**](../ntifs/ns-ntifs-query_on_create_file_lx_information.md)
