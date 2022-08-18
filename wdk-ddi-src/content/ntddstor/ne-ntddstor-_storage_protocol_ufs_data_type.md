---
UID: NE:ntddstor._STORAGE_PROTOCOL_UFS_DATA_TYPE
title: STORAGE_PROTOCOL_UFS_DATA_TYPE (ntddstor.h)
description: The UFS (Universal Flash Storage) data type. Describes the type of UFS specific data that's to be queried during an IOCTL_STORAGE_QUERY_PROPERTY request.
old-location: storage\storage_protocol_ufs_data_type.htm
tech.root: storage
ms.date: 08/18/2022
keywords: ["STORAGE_PROTOCOL_UFS_DATA_TYPE enumeration"]
ms.keywords: "*PSTORAGE_PROTOCOL_UFS_DATA_TYPE, STORAGE_PROTOCOL_UFS_DATA_TYPE, STORAGE_PROTOCOL_UFS_DATA_TYPE enumeration [Storage Devices], UfsDataTypeMax, UfsDataTypeQueryDescriptor, UfsDataTypeUnknown, _STORAGE_PROTOCOL_UFS_DATA_TYPE, ntddstor/ UfsDataTypeMax, ntddstor/ UfsDataTypeQueryDescriptor, ntddstor/STORAGE_PROTOCOL_UFS_DATA_TYPE, ntddstor/UfsDataTypeUnknown, storage.storage_protocol_ufs_data_type"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: STORAGE_PROTOCOL_UFS_DATA_TYPE, *PSTORAGE_PROTOCOL_UFS_DATA_TYPE
f1_keywords:
 - _STORAGE_PROTOCOL_UFS_DATA_TYPE
 - ntddstor/_STORAGE_PROTOCOL_UFS_DATA_TYPE
 - PSTORAGE_PROTOCOL_UFS_DATA_TYPE
 - ntddstor/PSTORAGE_PROTOCOL_UFS_DATA_TYPE
 - STORAGE_PROTOCOL_UFS_DATA_TYPE
 - ntddstor/STORAGE_PROTOCOL_UFS_DATA_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - _STORAGE_PROTOCOL_UFS_DATA_TYPE
 - PSTORAGE_PROTOCOL_UFS_DATA_TYPE
 - STORAGE_PROTOCOL_UFS_DATA_TYPE
---

# STORAGE_PROTOCOL_UFS_DATA_TYPE enumeration

## -description

The UFS (Universal Flash Storage) data type. Describes the type of UFS-specific data that is to be queried during an [**IOCTL_STORAGE_QUERY_PROPERTY*](ni-ntddstor-ioctl_storage_query_property.md) request.

## -enum-fields

### -field UfsDataTypeUnknown:0

Unknown data type.

### -field UfsDataTypeQueryDescriptor

Query the UFS descriptor data. Retrieved by the QUERY UPIU command.

### -field UfsDataTypeQueryAttribute

Query the UFS attributes. Retrieved by the QUERY UPIU command.

### -field UfsDataTypeQueryFlag

Query the UFS flag. Retrieved by the QUERY UPIU command.

### -field UfsDataTypeQueryDmeAttribute

Query the UFS device management entity (DME) attribute. Retrieved by the QUERY UPIU command.

### -field UfsDataTypeQueryDmePeerAttribute

Query the UFS DME peer attribute. Retrieved by the QUERY UPIU command.

### -field UfsDataTypeMax

Max size of data type.

## -see-also

[**STORAGE_PROTOCOL_DATA_DESCRIPTOR*](ns-ntddstor-_storage_protocol_data_descriptor.md)
