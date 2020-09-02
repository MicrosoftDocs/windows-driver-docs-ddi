---
UID: NE:ntddstor._STORAGE_PROTOCOL_UFS_DATA_TYPE
title: _STORAGE_PROTOCOL_UFS_DATA_TYPE (ntddstor.h)
description: The UFS (Universal Flash Storage) data type. Describes the type of UFS specific data that's to be queried during an IOCTL_STORAGE_QUERY_PROPERTY request.
old-location: storage\storage_protocol_ufs_data_type.htm
tech.root: storage
ms.assetid: A4324FAD-A925-4D65-9697-9CC2878DBE0B
ms.date: 03/29/2018
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
 - STORAGE_PROTOCOL_UFS_DATA_TYPE
---

# _STORAGE_PROTOCOL_UFS_DATA_TYPE enumeration


## -description

The UFS (Universal Flash Storage) data type. Describes the type of UFS specific data that's to be queried during an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> request.

## -enum-fields

### -field UfsDataTypeUnknown

Unknown data type.

### -field UfsDataTypeQueryDescriptor

Query Descriptor data type. Retrieved by command UfsSrbQueryProtocolQueryDescriptor.

### -field UfsDataTypeMax

Max size of data type.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_protocol_data_descriptor">STORAGE_PROTOCOL_DATA_DESCRIPTOR</a>

