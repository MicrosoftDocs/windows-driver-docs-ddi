---
UID: NS:ntddstor._STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT
title: STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT
description: This structure is used in conjunction with IOCTL_STORAGE_QUERY_PROPERTY and IOCTL_STORAGE_SET_PROPERTY to respectively return and set protocol-specific data for a storage device or adapter.
tech.root: storage
ms.date: 03/20/2019
keywords: ["STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT structure"]
ms.keywords: STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT, STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT, *PSTORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT,
req.header: ntddstor.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT, *PSTORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT
 - ntddstor/_STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT
 - PSTORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT
 - ntddstor/PSTORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT
 - STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT
 - ntddstor/STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT
product:
 - Windows
---

# STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT structure


## -description

This structure is used in conjunction with [IOCTL_STORAGE_QUERY_PROPERTY](ni-ntddstor-ioctl_storage_query_property.md) and [IOCTL_STORAGE_SET_PROPERTY](ni-ntddstor-ioctl_storage_set_property.md) to respectively return and set protocol-specific data from a storage device or adapter.

## -struct-fields

### -field Version

Version of this structure. Set this to be **sizeof**(STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT).

### -field Size

Size, in bytes, of the buffer containing the descriptor, including the space for all protocol data. Must be >= **sizeof**(STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT).

### -field ProtocolSpecificData

[STORAGE_PROTOCOL_SPECIFIC_DATA_EXT](ns-ntddstor-storage_protocol_specific_data_ext.md) structure that contains the protocol-specific data.

## -remarks

## -see-also

[IOCTL_STORAGE_QUERY_PROPERTY](ni-ntddstor-ioctl_storage_query_property.md)

[IOCTL_STORAGE_SET_PROPERTY](ni-ntddstor-ioctl_storage_set_property.md)

[STORAGE_PROTOCOL_SPECIFIC_DATA_EXT](ns-ntddstor-storage_protocol_specific_data_ext.md)

