---
UID: NS:ntifs._QUERY_ON_CREATE_EA_INFORMATION
tech.root: ifsk
title: QUERY_ON_CREATE_EA_INFORMATION
ms.date: 03/11/2021
targetos: Windows
description: The QUERY_ON_CREATE_EA_INFORMATION structure is used to write file information when FltRequestFileInfoOnCreateCompletion is called with the QoCFileEaInformation flag set in the InfoClassFlags parameter.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.target-type: 
req.typenames: QUERY_ON_CREATE_EA_INFORMATION, *PQUERY_ON_CREATE_EA_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _QUERY_ON_CREATE_EA_INFORMATION
 - PQUERY_ON_CREATE_EA_INFORMATION
 - QUERY_ON_CREATE_EA_INFORMATION
f1_keywords:
 - _QUERY_ON_CREATE_EA_INFORMATION
 - ntifs/_QUERY_ON_CREATE_EA_INFORMATION
 - PQUERY_ON_CREATE_EA_INFORMATION
 - ntifs/PQUERY_ON_CREATE_EA_INFORMATION
 - QUERY_ON_CREATE_EA_INFORMATION
 - ntifs/QUERY_ON_CREATE_EA_INFORMATION
dev_langs:
 - c++
---

## -description

The **QUERY_ON_CREATE_EA_INFORMATION** structure is used to write file information when [**FltRequestFileInfoOnCreateCompletion**](../fltkernel/nf-fltkernel-fltrequestfileinfooncreatecompletion.md) is called with the **QoCFileEaInformation** flag set in the **InfoClassFlags** parameter.

## -struct-fields

### -field EaBufferSize

Size, in bytes, of the buffer that **EaBuffer** points to.

### -field EaBuffer

A list of [**FILE_FULL_EA_INFORMATION**](../wdm/ns-wdm-_file_full_ea_information.md) structures with extended attribute (EA) information.

## -remarks

The file system allocates this structure and fills in the requested information, if supported, while it processes a file create. Filter Manager will free the allocated structure.

## -see-also

[**FILE_FULL_EA_INFORMATION**](../wdm/ns-wdm-_file_full_ea_information.md)

[**FltRequestFileInfoOnCreateCompletion**](../fltkernel/nf-fltkernel-fltrequestfileinfooncreatecompletion.md)

[**FltRetrieveFileInfoOnCreateCompletionEx**](../fltkernel/nf-fltkernel-fltretrievefileinfooncreatecompletionex.md)
