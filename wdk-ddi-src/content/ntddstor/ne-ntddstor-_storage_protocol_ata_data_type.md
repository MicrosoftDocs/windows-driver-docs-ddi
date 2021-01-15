---
UID: NE:ntddstor._STORAGE_PROTOCOL_ATA_DATA_TYPE
title: _STORAGE_PROTOCOL_ATA_DATA_TYPE (ntddstor.h)
description: The ATA protocol data type.
old-location: storage\storage_protocol_ata_data_type.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["STORAGE_PROTOCOL_ATA_DATA_TYPE enumeration"]
ms.keywords: "*PSTORAGE_PROTOCOL_ATA_DATA_TYPE, AtaDataTypeIdentify, AtaDataTypeLogPage, AtaDataTypeUnknown, PSTORAGE_PROTOCOL_ATA_DATA_TYPE, PSTORAGE_PROTOCOL_ATA_DATA_TYPE enumeration pointer [Storage Devices], STORAGE_PROTOCOL_ATA_DATA_TYPE, STORAGE_PROTOCOL_ATA_DATA_TYPE enumeration [Storage Devices], _STORAGE_PROTOCOL_ATA_DATA_TYPE, ntddstor/AtaDataTypeIdentify, ntddstor/AtaDataTypeLogPage, ntddstor/AtaDataTypeUnknown, ntddstor/PSTORAGE_PROTOCOL_ATA_DATA_TYPE, ntddstor/STORAGE_PROTOCOL_ATA_DATA_TYPE, storage.storage_protocol_ata_data_type"
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: STORAGE_PROTOCOL_ATA_DATA_TYPE, *PSTORAGE_PROTOCOL_ATA_DATA_TYPE
f1_keywords:
 - _STORAGE_PROTOCOL_ATA_DATA_TYPE
 - ntddstor/_STORAGE_PROTOCOL_ATA_DATA_TYPE
 - PSTORAGE_PROTOCOL_ATA_DATA_TYPE
 - ntddstor/PSTORAGE_PROTOCOL_ATA_DATA_TYPE
 - STORAGE_PROTOCOL_ATA_DATA_TYPE
 - ntddstor/STORAGE_PROTOCOL_ATA_DATA_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_PROTOCOL_ATA_DATA_TYPE
 - PSTORAGE_PROTOCOL_ATA_DATA_TYPE
 - STORAGE_PROTOCOL_ATA_DATA_TYPE
---

# _STORAGE_PROTOCOL_ATA_DATA_TYPE enumeration


## -description

The ATA protocol data type.

> [!NOTE]
> The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](/windows-hardware/drivers/storage/storport-driver-overview) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -enum-fields

### -field AtaDataTypeUnknown

Unknown data type.

### -field AtaDataTypeIdentify

Identify device data type.

### -field AtaDataTypeLogPage

Log page data type.

## -remarks

When using [IOCTL_STORAGE_QUERY_PROPERTY](./ni-ntddstor-ioctl_storage_query_property.md) to retrieve protocol-specific information in the [STORAGE_PROTOCOL_DATA_DESCRIPTOR](./ns-ntddstor-_storage_protocol_data_descriptor.md), configure the [STORAGE_PROPERTY_QUERY](./ns-ntddstor-_storage_property_query.md) structure as follows:

- Allocate a buffer that can contains both a [STORAGE_PROPERTY_QUERY](./ns-ntddstor-_storage_property_query.md) and a [STORAGE_PROTOCOL_SPECIFIC_DATA](./ns-ntddstor-_storage_protocol_specific_data.md) structure.

- Set the **PropertyID**  field to **StorageAdapterProtocolSpecificProperty** or **StorageDeviceProtocolSpecificProperty** for a controller or device/namespace request, respectively.

- Set the **QueryType**  field to **PropertyStandardQuery**.

- Fill the [STORAGE_PROTOCOL_SPECIFIC_DATA](./ns-ntddstor-_storage_protocol_specific_data.md) structure with the desired values. The start of the **STORAGE_PROTOCOL_SPECIFIC_DATA** is the **AdditionalParameters** field of [STORAGE_PROPERTY_QUERY](./ns-ntddstor-_storage_property_query.md).

To specify a type of ATA protocol-specific information, configure the [STORAGE_PROTOCOL_SPECIFIC_DATA](./ns-ntddstor-_storage_protocol_specific_data.md) structure as follows:

- Set the **ProtocolType**  field to **ProtocolTypeAta**.

- Set the **DataType**  field to an enumeration value defined by **STORAGE_PROTOCOL_ATA_DATA_TYPE**:

  - Use **AtaDataTypeIdentify** to identify the ATA drive.
  - Use **AtaDataTypeLogPage** to get log pages from the ATA drive.

