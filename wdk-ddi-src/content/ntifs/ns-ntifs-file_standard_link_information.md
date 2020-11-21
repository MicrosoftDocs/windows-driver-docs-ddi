---
UID: NS:ntifs._FILE_STANDARD_LINK_INFORMATION
title: FILE_STANDARD_LINK_INFORMATION
ms.date: 11/20/2020
ms.assetid: 4a507f6d-6851-45d6-a09c-e5dd72135f55
tech.root: ifsk
ms.topic: language-reference
targetos: Windows
description: FILE_STANDARD_LINK_INFORMATION is used to query file link information.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: FILE_STANDARD_LINK_INFORMATION, *PFILE_STANDARD_LINK_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_STANDARD_LINK_INFORMATION
 - FILE_STANDARD_LINK_INFORMATION
f1_keywords:
 - ntifs/_FILE_STANDARD_LINK_INFORMATION
 - ntifs/FILE_STANDARD_LINK_INFORMATION
dev_langs:
 - c++
---

## -description

**FILE_STANDARD_LINK_INFORMATION** is used to query file link information.

## -struct-fields

### -field NumberOfAccessibleLinks

Number of non-deleted links to this file.

### -field TotalNumberOfLinks

Total number of links to this file, including links marked for delete.

### -field DeletePending

Boolean value. This field must be set to TRUE to indicate that a file deletion has been requested; otherwise, set to FALSE.

### -field Directory

Set to 1 to indicate that the file is a directory; otherwise, set to FALSE.

## -remarks

## -see-also

[**NtQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md)
