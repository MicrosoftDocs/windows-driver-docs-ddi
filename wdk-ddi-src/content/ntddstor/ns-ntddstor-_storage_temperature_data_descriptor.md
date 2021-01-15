---
UID: NS:ntddstor._STORAGE_TEMPERATURE_DATA_DESCRIPTOR
title: _STORAGE_TEMPERATURE_DATA_DESCRIPTOR (ntddstor.h)
description: This structure is used in conjunction with IOCTL_STORAGE_QUERY_PROPERTY to return temperature data from a storage device or adapter.
old-location: storage\storage_temperature_data_descriptor.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["STORAGE_TEMPERATURE_DATA_DESCRIPTOR structure"]
ms.keywords: "*PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR, PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR, PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR structure pointer [Storage Devices], STORAGE_TEMPERATURE_DATA_DESCRIPTOR, STORAGE_TEMPERATURE_DATA_DESCRIPTOR structure [Storage Devices], _STORAGE_TEMPERATURE_DATA_DESCRIPTOR, ntddstor/PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR, ntddstor/STORAGE_TEMPERATURE_DATA_DESCRIPTOR, storage.storage_temperature_data_descriptor"
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
targetos: Windows
req.typenames: STORAGE_TEMPERATURE_DATA_DESCRIPTOR, *PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR
f1_keywords:
 - _STORAGE_TEMPERATURE_DATA_DESCRIPTOR
 - ntddstor/_STORAGE_TEMPERATURE_DATA_DESCRIPTOR
 - PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR
 - ntddstor/PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR
 - STORAGE_TEMPERATURE_DATA_DESCRIPTOR
 - ntddstor/STORAGE_TEMPERATURE_DATA_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_TEMPERATURE_DATA_DESCRIPTOR
 - PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR
 - STORAGE_TEMPERATURE_DATA_DESCRIPTOR
---

# _STORAGE_TEMPERATURE_DATA_DESCRIPTOR structure


## -description

This structure is used in conjunction with <a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> to return temperature data from a storage device or adapter.

## -struct-fields

### -field Version

Contains the size of this structure, in bytes. The value of this member will change as members are added to the structure.

### -field Size

Specifies the total size of the data returned, in bytes. This may include data that follows this structure.

### -field CriticalTemperature

Indicates the minimum temperature in degrees Celsius that may prevent normal operation. Exceeding this temperature may result in possible data loss, automatic device shutdown, extreme performance throttling, or permanent damage.

### -field WarningTemperature

Indicates the maximum temperature in degrees Celsius at which the device is capable of operating continuously without degrading operation or reliability.

### -field InfoCount

Specifies the number of <a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_temperature_info">STORAGE_TEMPERATURE_INFO</a> structures reported in <b>TemperatureInfo</b>. More than one set of temperature data may be returned when there are multiple sensors in the drive.

### -field Reserved0

Reserved for future use.

### -field Reserved1

Reserved for future use.

### -field TemperatureInfo

 




#### - TemperatureInfo[ANYSIZE_ARRAY]

Device temperature data, of type <a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_temperature_info">STORAGE_TEMPERATURE_INFO</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-storage_property_id">STORAGE_PROPERTY_ID</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_property_query">STORAGE_PROPERTY_QUERY</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_temperature_info">STORAGE_TEMPERATURE_INFO</a>

