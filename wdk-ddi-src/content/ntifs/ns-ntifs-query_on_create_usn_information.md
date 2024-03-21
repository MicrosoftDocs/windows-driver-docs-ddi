---
UID: NS:ntifs._QUERY_ON_CREATE_USN_INFORMATION
tech.root: ifsk
title: QUERY_ON_CREATE_USN_INFORMATION
ms.date: 03/24/2024
targetos: Windows
description: The QUERY_ON_CREATE_USN_INFORMATION structure is used to write file information when FltRequestFileInfoOnCreateCompletion is called with the QoCFileUsnInformation flag set in the InfoClassFlags parameter.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: QUERY_ON_CREATE_USN_INFORMATION, *PQUERY_ON_CREATE_USN_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _QUERY_ON_CREATE_USN_INFORMATION
 - PQUERY_ON_CREATE_USN_INFORMATION
 - QUERY_ON_CREATE_USN_INFORMATION
f1_keywords:
 - _QUERY_ON_CREATE_USN_INFORMATION
 - ntifs/_QUERY_ON_CREATE_USN_INFORMATION
 - PQUERY_ON_CREATE_USN_INFORMATION
 - ntifs/PQUERY_ON_CREATE_USN_INFORMATION
 - QUERY_ON_CREATE_USN_INFORMATION
 - ntifs/QUERY_ON_CREATE_USN_INFORMATION
dev_langs:
 - c++
---

## -description

The **QUERY_ON_CREATE_USN_INFORMATION** structure is used to write file information when [**FltRequestFileInfoOnCreateCompletion**](../fltkernel/nf-fltkernel-fltrequestfileinfooncreatecompletion.md) is called with the **QoCFileUsnInformation** flag set in the **InfoClassFlags** parameter.

## -struct-fields

### -field Usn

The USN (Update Sequence Number) for this file or directory.

### -field FileReferenceNumber

The 128-bit file ID (aka ordinal number) of the file or directory.

## -remarks

The system allocates this structure and the file system fills in the requested information, if supported, while it processes a file create. Filter Manager will eventually free the allocated structure.

## -see-also

[**FltRequestFileInfoOnCreateCompletion**](../fltkernel/nf-fltkernel-fltrequestfileinfooncreatecompletion.md)

[**FltRetrieveFileInfoOnCreateCompletionEx**](../fltkernel/nf-fltkernel-fltretrievefileinfooncreatecompletionex.md)
