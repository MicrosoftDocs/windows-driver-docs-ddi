---
UID: NS:ntddstor._STORAGE_PROTOCOL_DATA_DESCRIPTOR
title: _STORAGE_PROTOCOL_DATA_DESCRIPTOR (ntddstor.h)
description: This structure is used in conjunction with IOCTL_STORAGE_QUERY_PROPERTY to return protocol-specific data from a storage device or adapter.
old-location: storage\storage_protocol_data_descriptor.htm
tech.root: storage
ms.assetid: 292EE243-2952-4020-8EB0-C5127DF92318
ms.date: 03/29/2018
keywords: ["_STORAGE_PROTOCOL_DATA_DESCRIPTOR structure"]
ms.keywords: "*PSTORAGE_PROTOCOL_DATA_DESCRIPTOR, PSTORAGE_PROTOCOL_DATA_DESCRIPTOR, PSTORAGE_PROTOCOL_DATA_DESCRIPTOR structure pointer [Storage Devices], STORAGE_PROTOCOL_DATA_DESCRIPTOR, STORAGE_PROTOCOL_DATA_DESCRIPTOR structure [Storage Devices], _STORAGE_PROTOCOL_DATA_DESCRIPTOR, ntddstor/PSTORAGE_PROTOCOL_DATA_DESCRIPTOR, ntddstor/STORAGE_PROTOCOL_DATA_DESCRIPTOR, storage.storage_protocol_data_descriptor"
f1_keywords:
 - "ntddstor/STORAGE_PROTOCOL_DATA_DESCRIPTOR"
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddstor.h
api_name:
- STORAGE_PROTOCOL_DATA_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: STORAGE_PROTOCOL_DATA_DESCRIPTOR, *PSTORAGE_PROTOCOL_DATA_DESCRIPTOR
ms.custom: 19H1
---

# _STORAGE_PROTOCOL_DATA_DESCRIPTOR structure

## -description

This structure is used in conjunction with [IOCTL_STORAGE_SET_PROPERTY](ni-ntddstor-ioctl_storage_set_property.md) and [IOCTL_STORAGE_QUERY_PROPERTY](ni-ntddstor-ioctl_storage_query_property.md) to respectively set or query protocol-specific data from a storage device or adapter.

## -struct-fields

### -field Version

Version of this structure. Set to **sizeof**(STORAGE_PROTOCOL_DATA_DESCRIPTOR).

### -field Size

Total size in bytes of the descriptor, including the space for all protocol data. Must be => **sizeof**(STORAGE_PROTOCOL_DATA_DESCRIPTOR).

### -field ProtocolSpecificData

The protocol-specific data, of type [STORAGE_PROTOCOL_SPECIFIC_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_protocol_specific_data).

## -remarks

When using [IOCTL_STORAGE_QUERY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property) to retrieve protocol-specific information in the STORAGE_PROTOCOL_DATA_DESCRIPTOR, configure the [STORAGE_PROPERTY_QUERY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_property_query) structure as follows:

* Allocate a buffer that can contains both a [STORAGE_PROPERTY_QUERY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_property_query) and a [STORAGE_PROTOCOL_SPECIFIC_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_protocol_specific_data) structure.
* Set the **PropertyID**  field to **StorageAdapterProtocolSpecificProperty** or **StorageDeviceProtocolSpecificProperty** for a controller or device/namespace request, respectively.
* Set the **QueryType**  field to **PropertyStandardQuery**.
* Fill the [STORAGE_PROTOCOL_SPECIFIC_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_protocol_specific_data) structure with the desired values. The start of the STORAGE_PROTOCOL_SPECIFIC_DATA is the **AdditionalParameters** field of [STORAGE_PROPERTY_QUERY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_property_query).

To specify a type of NVMe protocol-specific information,  configure the [STORAGE_PROTOCOL_SPECIFIC_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_protocol_specific_data) structure as follows:

* Set the **ProtocolType**  field to **ProtocolTypeNVMe**.
* Set the **DataType**  field to an enumeration value defined by [STORAGE_PROTOCOL_NVME_DATA_TYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-_storage_protocol_nvme_data_type):
  * Use **NVMeDataTypeIdentify** to get Identify Controller data or Identify Namespace data.
  * Use **NVMeDataTypeLogPage** to get log pages (including SMART/health data).
  * Use **NVMeDataTypeFeature** to get features of the NVMe drive.

To specify a type of ATA protocol-specific information,  configure the [STORAGE_PROTOCOL_SPECIFIC_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_protocol_specific_data) structure as follows:

* Set the **ProtocolType**  field to **ProtocolTypeAta**.
* Set the **DataType**  field to an enumeration value defined by [STORAGE_PROTOCOL_ATA_DATA_TYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-_storage_protocol_ata_data_type):
  * Use **AtaDataTypeIdentify** to identify the ATA drive.
  * Use **AtaDataTypeLogPage** to get log pages from the ATA drive.

## -see-also

[IOCTL_STORAGE_QUERY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property)

[IOCTL_STORAGE_SET_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_set_property)

[STORAGE_PROPERTY_ID](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-storage_property_id)

[STORAGE_PROPERTY_QUERY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_property_query)

[STORAGE_PROTOCOL_SPECIFIC_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_protocol_specific_data)

[STORAGE_PROTOCOL_SPECIFIC_DATA_EXT](ns-ntddstor-storage_protocol_specific_data_ext.md)
