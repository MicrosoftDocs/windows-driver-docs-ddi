---
UID: NS:ntifs._FILE_DESIRED_STORAGE_CLASS_INFORMATION
title: _FILE_DESIRED_STORAGE_CLASS_INFORMATION
author: windows-driver-content
description: Contains the information for the Desired Storage Class attribute.
ms.assetid: 0a6927e5-e1cb-439e-a899-1583baff7cbb
ms.date: 09/30/2018
ms.topic: struct
ms.keywords: _FILE_DESIRED_STORAGE_CLASS_INFORMATION, FILE_DESIRED_STORAGE_CLASS_INFORMATION, *PFILE_DESIRED_STORAGE_CLASS_INFORMATION, 
req.header: ntifs.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: FILE_DESIRED_STORAGE_CLASS_INFORMATION, *PFILE_DESIRED_STORAGE_CLASS_INFORMATION
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ntifs.h
api_name: 
-	_FILE_DESIRED_STORAGE_CLASS_INFORMATION
product: Windows
targetos: Windows
ms.custom: RS5
---

# _FILE_DESIRED_STORAGE_CLASS_INFORMATION structure

## -description
Contains the information for the desired storage class attribute. The class information is set by calling [**NtSetInformationFile**](nf-ntifs-ntsetinformationfile.md)

## -struct-fields

### -field Class
A [**FILE_STORAGE_TIER_CLASS**](ne-ntifs-_file_storage_tier_class.md)-value that the storage class. This is the tier type for the file/directory.
 
### -field Flags
Flags for the class type. Here are the possible values:

- QUERY_STORAGE_CLASSES_FLAGS_MEASURE_WRITE
- QUERY_STORAGE_CLASSES_FLAGS_MEASURE_READ

## -remarks

## -see-also
