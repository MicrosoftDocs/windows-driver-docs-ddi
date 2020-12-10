---
UID: NS:ntddstor._STORAGE_PROTOCOL_SPECIFIC_DATA_EXT
title: STORAGE_PROTOCOL_SPECIFIC_DATA_EXT
description: The **STORAGE_PROTOCOL_SPECIFIC_DATA_EXT** structure describes the protocol-specific device data for IOCTL_STORAGE_QUERY_PROPERTY and IOCTL_STORAGE_SET_PROPERTY requests.
tech.root: storage
ms.date: 03/21/2019
keywords: ["STORAGE_PROTOCOL_SPECIFIC_DATA_EXT structure"]
ms.keywords: STORAGE_PROTOCOL_SPECIFIC_DATA_EXT, STORAGE_PROTOCOL_SPECIFIC_DATA_EXT, *PSTORAGE_PROTOCOL_SPECIFIC_DATA_EXT,
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
req.typenames: STORAGE_PROTOCOL_SPECIFIC_DATA_EXT, *PSTORAGE_PROTOCOL_SPECIFIC_DATA_EXT
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _STORAGE_PROTOCOL_SPECIFIC_DATA_EXT
 - ntddstor/_STORAGE_PROTOCOL_SPECIFIC_DATA_EXT
 - PSTORAGE_PROTOCOL_SPECIFIC_DATA_EXT
 - ntddstor/PSTORAGE_PROTOCOL_SPECIFIC_DATA_EXT
 - STORAGE_PROTOCOL_SPECIFIC_DATA_EXT
 - ntddstor/STORAGE_PROTOCOL_SPECIFIC_DATA_EXT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - STORAGE_PROTOCOL_SPECIFIC_DATA_EXT
product:
 - Windows
---

# STORAGE_PROTOCOL_SPECIFIC_DATA_EXT structure


## -description

The STORAGE_PROTOCOL_SPECIFIC_DATA_EXT structure describes the protocol-specific device data for [IOCTL_STORAGE_QUERY_PROPERTY](./ni-ntddstor-ioctl_storage_query_property.md) and [IOCTL_STORAGE_SET_PROPERTY](./ni-ntddstor-ioctl_storage_set_property.md) requests.

## -struct-fields

### -field ProtocolType

The protocol type. Values for this member are defined in the [STORAGE_PROTOCOL_TYPE](./ne-ntddstor-_storage_protocol_type.md) enumeration.

### -field DataType

The protocol data type. Data types are defined in the [STORAGE_PROTOCOL_NVME_DATA_TYPE](./ne-ntddstor-_storage_protocol_nvme_data_type.md) and [STORAGE_PROTOCOL_ATA_DATA_TYPE](./ne-ntddstor-_storage_protocol_ata_data_type.md) enumerations.

### -field ProtocolDataValue

The protocol data value.

### -field ProtocolDataSubValue

Sub-value of the protocol data value.

### -field ProtocolDataOffset

The offset of the data buffer from the beginning of this structure. The typical value is **sizeof**(STORAGE_PROTOCOL_SPECIFIC_DATA_EXT).

### -field ProtocolDataLength

The length of the protocol data.

### -field FixedProtocolReturnData

The returned data.

### -field ProtocolDataRequestSubValue2

First additional data sub-value.

### -field ProtocolDataRequestSubValue3

Second additional data sub-value.

### -field ProtocolDataSubValue4

Third additional data sub-value.

### -field ProtocolDataSubValue5

Fourth additional data sub-value.

### -field Reserved

Reserved for future use; do not use.

## -remarks

## -see-also

[IOCTL_STORAGE_QUERY_PROPERTY](./ni-ntddstor-ioctl_storage_query_property.md)

[IOCTL_STORAGE_SET_PROPERTY](./ni-ntddstor-ioctl_storage_set_property.md)

[STORAGE_PROTOCOL_SPECIFIC_DATA](ns-ntddstor-_storage_protocol_specific_data.md)
