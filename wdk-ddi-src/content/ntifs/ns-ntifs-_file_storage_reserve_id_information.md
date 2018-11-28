---
UID: NS:ntifs._FILE_STORAGE_RESERVE_ID_INFORMATION
title: _FILE_STORAGE_RESERVE_ID_INFORMATION
author: windows-driver-content
description: Queries and sets the storage reserve ID on a file or directory.
ms.assetid: 3114a6fb-3728-41a7-b4f4-d4463eec019b
ms.date: 09/30/2018
ms.topic: struct
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
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ntifs.h
api_name: 
-	_FILE_STORAGE_RESERVE_ID_INFORMATION
product: Windows
targetos: Windows
ms.custom: RS5
---

# _FILE_STORAGE_RESERVE_ID_INFORMATION structure

## -description
The structure is used by [**NtQueryInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntqueryinformationfile) and [**NtSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntsetinformationfile) routines to query and set the storage reserve ID on a file or directory.

## -struct-fields

### -field StorageReserveId
Specifies a [**STORAGE_RESERVE_ID**](ne-ntifs-_storage_reserve_id.md) value that indicates the storage reserve ID for the file or directory. This is used by the file system to change the disk space used by the file or directory:
- Toward space that has been reserved by the operating system for special purposes (called storage reserve areas)
- Toward space that is available for all users and applications.

## -remarks
Setting a storage reserve ID on a directory causes all files subsequently created inside that directory to inherit the storage reserve ID.

Attempting to set a storage reserve ID fails with STATUS_STORAGE_RESERVE_ID_INVALID if the value is greater than the maximum value supported by the file system.

Attempting to set a storage reserve ID fails with STATUS_STORAGE_RESERVE_DOES_NOT_EXIST if the corresponding storage reserve area has not been defined on the volume.

## -see-also

[**STORAGE_RESERVE_ID**](ne-ntifs-_storage_reserve_id.md)
