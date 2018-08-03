---
UID: NE:ntifs._STORAGE_RESERVE_ID
title: _STORAGE_RESERVE_ID
author: windows-driver-content
description: Defines the storage reserve ID of a file, directory, or storage reserve area.
ms.assetid: 70d48fa6-0d49-4fa9-adf8-d84dc91d014e
ms.author: windowsdriverdev
ms.date:  09/30/2018
ms.topic: enum
ms.keywords: _STORAGE_RESERVE_ID, STORAGE_RESERVE_ID, *PSTORAGE_RESERVE_ID, 
ms.prod: windows-hardware
ms.technology: windows-devices
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
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ntifs.h
api_name: 
-	_STORAGE_RESERVE_ID
product: Windows
targetos: Windows
---

# _STORAGE_RESERVE_ID enumeration

## -description
Defines values for the storage reserve ID of a file, directory, or storage reserve area. The values are used by the [**FILE_STORAGE_RESERVE_ID_INFORMATION**](ns-ntifs-_file_storage_reserve_id_information.md) structure.


## -enum-fields

### -field StorageReserveIdNone 
Specifies the file or directory is not associated with any particular storage reserve area.  Files created by users and applications are treated as having StorageReserveIdNone by default, unless they are created inside a directory that has been marked with a different storage reserve ID.

### -field StorageReserveIdHard 
Specifies the file or directory is part of the "Hard" storage reserve area, which is used by the system to help ensure there is sufficient disk space to download and install updates.  Warning: A file or directory marked as StorageReserveIdHard may be deleted automatically by the system at any time, without user consent.

### -field StorageReserveIdSoft 
Specifies the file or directory is part of the "Soft" storage reserve area, which is used by the system to help ensure there is sufficient disk space to install updates.  Warning: A file or directory marked as StorageReserveIdHard may be deleted automatically by the system at any time, without user consent.

### -field StorageReserveIdMax 
Marks the limit of predefined storage reserve IDs currently understood by the system.  File systems that support storage reserves may support IDs beyond this to allow for future use.

## -remarks

## -see-also
[**FILE_STORAGE_RESERVE_ID_INFORMATION**](ns-ntifs-_file_storage_reserve_id_information.md)