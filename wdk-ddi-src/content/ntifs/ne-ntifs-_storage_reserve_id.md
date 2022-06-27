---
UID: NE:ntifs._STORAGE_RESERVE_ID
title: STORAGE_RESERVE_ID (ntifs.h)
description: Defines the storage reserve ID of a file, directory, or storage reserve area.
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["STORAGE_RESERVE_ID enumeration"]
ms.keywords: _STORAGE_RESERVE_ID, STORAGE_RESERVE_ID, *PSTORAGE_RESERVE_ID,
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: STORAGE_RESERVE_ID, *PSTORAGE_RESERVE_ID
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _STORAGE_RESERVE_ID
 - ntifs/_STORAGE_RESERVE_ID
 - PSTORAGE_RESERVE_ID
 - ntifs/PSTORAGE_RESERVE_ID
 - STORAGE_RESERVE_ID
 - ntifs/STORAGE_RESERVE_ID
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _STORAGE_RESERVE_ID
 - PSTORAGE_RESERVE_ID
 - STORAGE_RESERVE_ID
dev_langs:
 - c++
---

# STORAGE_RESERVE_ID enumeration

## -description

**STORAGE_RESERVE_ID** defines values for the storage reserve ID of a file, directory, or storage reserve area. The values are used by the [**FILE_STORAGE_RESERVE_ID_INFORMATION**](ns-ntifs-_file_storage_reserve_id_information.md) structure.

## -enum-fields

### -field StorageReserveIdNone

The file or directory is not associated with any particular storage reserve area.  Files created by users and applications are treated as having StorageReserveIdNone by default, unless they are created inside a directory that has been marked with a different storage reserve ID.

### -field StorageReserveIdHard

The file or directory is part of the "Hard" storage reserve area, which is used by the system to help ensure there is sufficient disk space to download and install updates.  **_Warning: A file or directory marked as StorageReserveIdHard may be deleted automatically by the system at any time, without user consent._**

### -field StorageReserveIdSoft

The file or directory is part of the "Soft" storage reserve area, which is used by the system to help ensure there is sufficient disk space to install updates.  **_Warning: A file or directory marked as StorageReserveIdSoft may be deleted automatically by the system at any time, without user consent._**

### -field StorageReserveIdUpdateScratch

The file or directory is part of the "Update Scratch" storage reserve area, which is used by the system to help ensure there is sufficient disk space to install an update from scratch. **_Warning: A file or directory marked as StorageReserveIdSoft may be deleted automatically by the system at any time, without user consent._**

### -field StorageReserveIdMax

Marks the limit of predefined storage reserve IDs currently understood by the system.  File systems that support storage reserves may support IDs beyond this to allow for future use.

## -see-also

[**FILE_STORAGE_RESERVE_ID_INFORMATION**](ns-ntifs-_file_storage_reserve_id_information.md)
