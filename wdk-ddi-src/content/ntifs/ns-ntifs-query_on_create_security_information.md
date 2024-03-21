---
UID: NS:ntifs._QUERY_ON_CREATE_SECURITY_INFORMATION
tech.root: ifsk
title: QUERY_ON_CREATE_SECURITY_INFORMATION
ms.date: 03/24/2024
targetos: Windows
description: The QUERY_ON_CREATE_SECURITY_INFORMATION structure is used to write file information when FltRequestSecurityInfoOnCreateCompletion is called in pre-create.
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
req.typenames: QUERY_ON_CREATE_SECURITY_INFORMATION, *PQUERY_ON_CREATE_SECURITY_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _QUERY_ON_CREATE_SECURITY_INFORMATION
 - PQUERY_ON_CREATE_SECURITY_INFORMATION
 - QUERY_ON_CREATE_SECURITY_INFORMATION
f1_keywords:
 - _QUERY_ON_CREATE_SECURITY_INFORMATION
 - ntifs/_QUERY_ON_CREATE_SECURITY_INFORMATION
 - PQUERY_ON_CREATE_SECURITY_INFORMATION
 - ntifs/PQUERY_ON_CREATE_SECURITY_INFORMATION
 - QUERY_ON_CREATE_SECURITY_INFORMATION
 - ntifs/QUERY_ON_CREATE_SECURITY_INFORMATION
dev_langs:
 - c++
---

## -description

The **QUERY_ON_CREATE_SECURITY_INFORMATION** structure is used to write file information when [**FltRequestSecurityInfoOnCreateCompletion**](../fltkernel/nf-fltkernel-fltrequestsecurityinfooncreatecompletion.md) is called in pre-create.

## -struct-fields

### -field Reserved

This is undefined and reserved for future use.

### -field SecurityDescriptorSize

Size, in bytes, of the SecurityDescriptor buffer.

### -field SecurityDescriptor

Pointer to a buffer that receives a copy of the security descriptor for the specified object. The [**SECURITY_DESCRIPTOR**](../ntifs/ns-ntifs-_security_descriptor.md) structure is returned in self-relative format.

## -remarks

The system allocates this structure and the file system fills in the requested information, if supported, while it processes a file create. Filter Manager will eventually free the allocated structure.

## -see-also

[**FltQuerySecurityObject**](../fltkernel/nf-fltkernel-fltquerysecurityobject.md)

[**FltRequestFileInfoOnCreateCompletion**](../fltkernel/nf-fltkernel-fltrequestfileinfooncreatecompletion.md)

[**FltRetrieveFileInfoOnCreateCompletionEx**](../fltkernel/nf-fltkernel-fltretrievefileinfooncreatecompletionex.md)
