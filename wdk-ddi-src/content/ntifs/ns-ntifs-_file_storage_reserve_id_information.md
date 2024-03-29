---
UID: NS:ntifs._FILE_STORAGE_RESERVE_ID_INFORMATION
title: FILE_STORAGE_RESERVE_ID_INFORMATION (ntifs.h)
description: Learn more about the FILE_STORAGE_RESERVE_ID_INFORMATION structure.
ms.date: 01/25/2023
tech.root: ifsk
keywords: ["FILE_STORAGE_RESERVE_ID_INFORMATION structure"]
ms.keywords: _FILE_STORAGE_RESERVE_ID_INFORMATION, FILE_STORAGE_RESERVE_ID_INFORMATION, *PFILE_STORAGE_RESERVE_ID_INFORMATION,
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: FILE_STORAGE_RESERVE_ID_INFORMATION, *PFILE_STORAGE_RESERVE_ID_INFORMATION
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _FILE_STORAGE_RESERVE_ID_INFORMATION
 - ntifs/_FILE_STORAGE_RESERVE_ID_INFORMATION
 - PFILE_STORAGE_RESERVE_ID_INFORMATION
 - ntifs/PFILE_STORAGE_RESERVE_ID_INFORMATION
 - FILE_STORAGE_RESERVE_ID_INFORMATION
 - ntifs/FILE_STORAGE_RESERVE_ID_INFORMATION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_STORAGE_RESERVE_ID_INFORMATION
 - PFILE_STORAGE_RESERVE_ID_INFORMATION
 - FILE_STORAGE_RESERVE_ID_INFORMATION
dev_langs:
 - c++
---

# FILE_STORAGE_RESERVE_ID_INFORMATION structure

## -description

The **FILE_STORAGE_RESERVE_ID_INFORMATION** structure is used by [**NtQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md) and [**NtSetInformationFile**](nf-ntifs-ntsetinformationfile.md) to query and set the storage reserve ID on a file or directory.

## -struct-fields

### -field StorageReserveId

A [**STORAGE_RESERVE_ID**](ne-ntifs-_storage_reserve_id.md) value that indicates the storage reserve ID for the file or directory. The file system uses this ID to change the disk space used by the file or directory as follows:

- To storage space that has been reserved by the operating system for special purposes (called storage reserve areas)
- To storage space that is available for all users and applications

## -remarks

Setting a storage reserve ID on a directory causes all files subsequently created inside that directory to inherit the storage reserve ID.

Attempting to set a storage reserve ID fails with STATUS_STORAGE_RESERVE_ID_INVALID if the value is greater than the maximum value supported by the file system.

Attempting to set a storage reserve ID fails with STATUS_STORAGE_RESERVE_DOES_NOT_EXIST if the corresponding storage reserve area has not been defined on the volume.

## -see-also

[**STORAGE_RESERVE_ID**](ne-ntifs-_storage_reserve_id.md)
