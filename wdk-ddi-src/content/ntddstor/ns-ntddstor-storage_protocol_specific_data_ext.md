---
UID: NS:ntddstor._STORAGE_PROTOCOL_SPECIFIC_DATA_EXT
title: STORAGE_PROTOCOL_SPECIFIC_DATA_EXT
author: windows-driver-content
description: The **STORAGE_PROTOCOL_SPECIFIC_DATA_EXT** structure describes the protocol-specific device data for IOCTL_STORAGE_QUERY_PROPERTY and IOCTL_STORAGE_SET_PROPERTY requests.
tech.root: storage
ms.assetid: d033364c-19ba-4091-a9d2-e9afee5ab7dc
ms.author: windowsdriverdev
ms.date: 03/21/2019
ms.topic: struct
f1_keywords:
 - "ntddstor/STORAGE_PROTOCOL_SPECIFIC_DATA_EXT"
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
targetos: Windows
ms.custom: 19H1
---

# STORAGE_PROTOCOL_SPECIFIC_DATA_EXT structure

## -description

The STORAGE_PROTOCOL_SPECIFIC_DATA_EXT structure describes the protocol-specific device data for [IOCTL_STORAGE_QUERY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property) and [IOCTL_STORAGE_SET_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_set_property) requests.

## -struct-fields

### -field ProtocolType

The protocol type. Values for this member are defined in the [STORAGE_PROTOCOL_TYPE](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/ntddstor/ne-ntddstor-_storage_protocol_type) enumeration.

### -field DataType

The protocol data type. Data types are defined in the [STORAGE_PROTOCOL_NVME_DATA_TYPE](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/ntddstor/ne-ntddstor-_storage_protocol_nvme_data_type) and [STORAGE_PROTOCOL_ATA_DATA_TYPE](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/ntddstor/ne-ntddstor-_storage_protocol_ata_data_type) enumerations.

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

[IOCTL_STORAGE_QUERY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property)

[IOCTL_STORAGE_SET_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_set_property)

[STORAGE_PROTOCOL_SPECIFIC_DATA](ns-ntddstor-_storage_protocol_specific_data.md)
