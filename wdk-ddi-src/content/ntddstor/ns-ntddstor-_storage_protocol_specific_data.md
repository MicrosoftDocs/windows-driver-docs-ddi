---
UID: NS:ntddstor._STORAGE_PROTOCOL_SPECIFIC_DATA
title: _STORAGE_PROTOCOL_SPECIFIC_DATA (ntddstor.h)
description: Describes protocol-specific device data, provided in the input and output buffer of an IOCTL_STORAGE_QUERY_PROPERTY request.
old-location: storage\storage_protocol_specific_data.htm
tech.root: storage
ms.assetid: 74569A0A-5828-4533-8974-4DE0B4EAAAEB
ms.date: 03/29/2018
keywords: ["_STORAGE_PROTOCOL_SPECIFIC_DATA structure"]
ms.keywords: "*PSTORAGE_PROTOCOL_SPECIFIC_DATA, PSTORAGE_PROTOCOL_SPECIFIC_DATA, PSTORAGE_PROTOCOL_SPECIFIC_DATA structure pointer [Storage Devices], STORAGE_PROTOCOL_SPECIFIC_DATA, STORAGE_PROTOCOL_SPECIFIC_DATA structure [Storage Devices], _STORAGE_PROTOCOL_SPECIFIC_DATA, ntddstor/PSTORAGE_PROTOCOL_SPECIFIC_DATA, ntddstor/STORAGE_PROTOCOL_SPECIFIC_DATA, storage.storage_protocol_specific_data"
f1_keywords:
 - "ntddstor/STORAGE_PROTOCOL_SPECIFIC_DATA"
 - "STORAGE_PROTOCOL_SPECIFIC_DATA"
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
- STORAGE_PROTOCOL_SPECIFIC_DATA
targetos: Windows
req.typenames: STORAGE_PROTOCOL_SPECIFIC_DATA, *PSTORAGE_PROTOCOL_SPECIFIC_DATA
ms.custom: 19H1
---

# _STORAGE_PROTOCOL_SPECIFIC_DATA structure

## -description

Describes  protocol-specific device data, provided in the input and output buffer of an  [IOCTL_STORAGE_QUERY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property) request.

## -struct-fields

### -field ProtocolType

The protocol type. Values for this member are defined in the [STORAGE_PROTOCOL_TYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-_storage_protocol_type) enumeration.

### -field DataType

The protocol data type. Data types are defined in the [STORAGE_PROTOCOL_NVME_DATA_TYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-_storage_protocol_nvme_data_type) and [STORAGE_PROTOCOL_ATA_DATA_TYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-_storage_protocol_ata_data_type) enumerations.

### -field ProtocolDataRequestValue

The protocol data request value.

### -field ProtocolDataRequestSubValue

The sub value of the protocol data request.

### -field ProtocolDataOffset

The offset of the data buffer that is from the beginning of this structure. The typical value can be **sizeof**(STORAGE_PROTOCOL_SPECIFIC_DATA).

### -field ProtocolDataLength

The length of the protocol data.

### -field FixedProtocolReturnData

The returned data.

### -field ProtocolDataRequestSubValue2

First additional data sub request value

### -field ProtocolDataRequestSubValue3

Second additional data sub request value.

## -remarks

When using [IOCTL_STORAGE_QUERY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property) to retrieve protocol-specific information in the [STORAGE_PROTOCOL_DATA_DESCRIPTOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_protocol_data_descriptor), configure the [STORAGE_PROPERTY_QUERY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_property_query) structure as follows:

* Allocate a buffer that can contains both a [STORAGE_PROPERTY_QUERY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_property_query) and a STORAGE_PROTOCOL_SPECIFIC_DATA structure.
* Set the **PropertyID**  field to **StorageAdapterProtocolSpecificProperty** or **StorageDeviceProtocolSpecificProperty** for a controller or device/namespace request, respectively.
* Set the **QueryType**  field to **PropertyStandardQuery**.
* Fill the STORAGE_PROTOCOL_SPECIFIC_DATA structure with the desired values. The start of STORAGE_PROTOCOL_SPECIFIC_DATA is the **AdditionalParameters** field of [STORAGE_PROPERTY_QUERY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_property_query).

To specify a type of NVMe protocol-specific information,  configure the STORAGE_PROTOCOL_SPECIFIC_DATA structure as follows:

* Set the **ProtocolType**  field to **ProtocolTypeNVMe**.
* Set the **DataType**  field to an enumeration value defined by [STORAGE_PROTOCOL_NVME_DATA_TYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-_storage_protocol_nvme_data_type):
  * **NVMeDataTypeIdentify** to get Identify Controller data or Identify Namespace data.
  * **NVMeDataTypeLogPage** to get log pages (including SMART/health data).
  * **NVMeDataTypeFeature** to get features of the NVMe drive.

To specify a type of ATA protocol-specific information, configure the STORAGE_PROTOCOL_SPECIFIC_DATA structure as follows:

* Set the **ProtocolType**  field to **ProtocolTypeAta**.
* Set the **DataType**  field to an enumeration value defined by [STORAGE_PROTOCOL_ATA_DATA_TYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-_storage_protocol_ata_data_type):
  * Use **AtaDataTypeIdentify** to identify the ATA drive.
  * Use **AtaDataTypeLogPage** to get log pages from the ATA drive.

## -see-also

[IOCTL_STORAGE_QUERY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property)

[STORAGE_PROPERTY_ID](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-storage_property_id)

[STORAGE_PROPERTY_QUERY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_property_query)

[STORAGE_PROTOCOL_SPECIFIC_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_protocol_specific_data)

[STORAGE_PROTOCOL_SPECIFIC_DATA_EXT](ns-ntddstor-storage_protocol_specific_data_ext.md)
