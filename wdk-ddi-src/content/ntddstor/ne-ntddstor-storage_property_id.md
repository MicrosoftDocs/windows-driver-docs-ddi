---
UID: NE:ntddstor._STORAGE_PROPERTY_ID
title: STORAGE_PROPERTY_ID
description: STORAGE_PROPERTY_ID enumerates the possible values for STORAGE_PROPERTY_QUERY's PropertyId member.
tech.root: storage
ms.date: 10/27/2020
keywords: ["STORAGE_PROPERTY_ID enumeration"]
ms.keywords: STORAGE_PROPERTY_ID, STORAGE_PROPERTY_ID, *PSTORAGE_PROPERTY_ID,
req.header: ntddstor.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: STORAGE_PROPERTY_ID, *PSTORAGE_PROPERTY_ID
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _STORAGE_PROPERTY_ID
 - ntddstor/_STORAGE_PROPERTY_ID
 - PSTORAGE_PROPERTY_ID
 - ntddstor/PSTORAGE_PROPERTY_ID
 - STORAGE_PROPERTY_ID
 - ntddstor/STORAGE_PROPERTY_ID
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_PROPERTY_ID
 - PSTORAGE_PROPERTY_ID
 - STORAGE_PROPERTY_ID
product:
 - Windows
---

# STORAGE_PROPERTY_ID enumeration


## -description

**STORAGE_PROPERTY_ID** enumerates the possible values for [**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md)'s **PropertyId** member.

## -enum-fields

### -field StorageDeviceProperty

The caller is querying for the device descriptor, [**STORAGE_DEVICE_DESCRIPTOR**](ns-ntddstor-_storage_device_descriptor.md).

### -field StorageAdapterProperty

The caller is querying for the adapter descriptor, [**STORAGE_ADAPTER_DESCRIPTOR**](ns-ntddstor-_storage_adapter_descriptor.md).

### -field StorageDeviceIdProperty

The caller is querying for the device identifiers provided with the SCSI vital product data pages. Data is returned using the [**STORAGE_DEVICE_ID_DESCRIPTOR**](ns-ntddstor-_storage_device_id_descriptor.md) structure.

### -field StorageDeviceUniqueIdProperty

The caller is querying for the unique device identifiers. Data is returned using the [**STORAGE_DEVICE_UNIQUE_IDENTIFIER**](../storduid/ns-storduid-_storage_device_unique_identifier.md) structure.

### -field StorageDeviceWriteCacheProperty

The caller is querying for the write cache property. Data is returned using the [**STORAGE_WRITE_CACHE_PROPERTY**](ns-ntddstor-_storage_write_cache_property.md) structure.

### -field StorageMiniportProperty

Reserved for system use.

### -field StorageAccessAlignmentProperty

The caller is querying for the access alignment descriptor, [**STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR**](ns-ntddstor-_storage_access_alignment_descriptor.md).

### -field StorageDeviceSeekPenaltyProperty

The caller is querying for the seek penalty descriptor, [**DEVICE_SEEK_PENALTY_DESCRIPTOR**](ns-ntddstor-_device_seek_penalty_descriptor.md).

### -field StorageDeviceTrimProperty

The caller is querying for the trim descriptor, [**DEVICE_TRIM_DESCRIPTOR**](ns-ntddstor-_device_trim_descriptor.md).

### -field StorageDeviceWriteAggregationProperty

Reserved for system use.

### -field StorageDeviceDeviceTelemetryProperty

Reserved for system use.

### -field StorageDeviceLBProvisioningProperty

The caller is querying for the logical block provisioning property. Data is returned using the [**DEVICE_LB_PROVISIONING_DESCRIPTOR**](ns-ntddstor-_device_lb_provisioning_descriptor.md) structure.

### -field StorageDevicePowerProperty

The caller is querying for the device power descriptor. Data is returned using the [**DEVICE_POWER_DESCRIPTOR**](ns-ntddstor-_device_power_descriptor.md) structure.

### -field StorageDeviceCopyOffloadProperty

The caller is querying for the copy offload parameters property. Data is returned using the [**DEVICE_COPY_OFFLOAD_DESCRIPTOR**](ns-ntddstor-_device_copy_offload_descriptor.md) structure.

### -field StorageDeviceResiliencyProperty

Reserved for system use.

### -field StorageDeviceMediumProductType

The caller is querying for the medium product type. Data is returned using the [**STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR**](ns-ntddstor-_storage_medium_product_type_descriptor.md) structure.

### -field StorageAdapterRpmbProperty

The caller is querying for RPMB support and properties. Data is returned using the [**STORAGE_RPMB_DESCRIPTOR**](ns-ntddstor-storage_rpmb_descriptor.md) structure.

### -field StorageAdapterCryptoProperty

Provides information on the storage adapter encryption capabilities. This is currently supported on UFS (Universal Flash Storage) adapters.

### -field StorageDeviceTieringProperty

Reserved for system use.

### -field StorageDeviceFaultDomainProperty

Reserved for system use.

### -field StorageDeviceClusportProperty

Reserved for system use.

### -field StorageDeviceDependantDevicesProperty

Reserved for system use.

### -field StorageDeviceIoCapabilityProperty

The caller is querying for the device I/O capability property. Data is returned using the [**STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR**](ns-ntddstor-_storage_device_io_capability_descriptor.md) structure.

### -field StorageAdapterProtocolSpecificProperty

The caller is querying for protocol-specific data from the adapter. Data is returned using the [**STORAGE_PROTOCOL_DATA_DESCRIPTOR**](ns-ntddstor-_storage_protocol_data_descriptor.md) structure. See the Remarks for more info.

### -field StorageDeviceProtocolSpecificProperty

The caller is querying for protocol-specific data from the device. Data is returned using the [**STORAGE_PROTOCOL_DATA_DESCRIPTOR**](ns-ntddstor-_storage_protocol_data_descriptor.md) structure. See the Remarks for more info.

### -field StorageAdapterTemperatureProperty

The caller is querying temperature data from the adapter. Data is returned using the [**STORAGE_TEMPERATURE_DATA_DESCRIPTOR**](ns-ntddstor-_storage_temperature_data_descriptor.md) structure.

### -field StorageDeviceTemperatureProperty

The caller is querying for temperature data from the device. Data is returned using the [**STORAGE_TEMPERATURE_DATA_DESCRIPTOR**](ns-ntddstor-_storage_temperature_data_descriptor.md) structure.

### -field StorageAdapterPhysicalTopologyProperty

The caller is querying for topology information from the adapter. Data is returned using the [**STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR**](ns-ntddstor-_storage_physical_topology_descriptor.md) structure.

### -field StorageDevicePhysicalTopologyProperty

The caller is querying for topology information from the device. Data is returned using the [**STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR**](ns-ntddstor-_storage_physical_topology_descriptor.md) structure.

### -field StorageDeviceAttributesProperty

Reserved for future use.

### -field StorageDeviceManagementStatus

Provides health information about the storage device (specifically for the persistent memory stack).

### -field StorageAdapterSerialNumberProperty

The caller is querying for the adapter serial number. Data is returned using the [**STORAGE_ADAPTER_SERIAL_NUMBER**](/windows/win32/api/winioctl/ns-winioctl-storage_adapter_serial_number) structure.

### -field StorageDeviceLocationProperty

Reserved for system use.

### -field StorageDeviceNumaProperty

Provides the non-uniform memory access (NUMA) node of the storage device.

### -field StorageDeviceZonedDeviceProperty

Reserved for system use.

### -field StorageDeviceUnsafeShutdownCount

Provides the unsafe shutdown count value used to determine if the device data might have been lost during a power loss event (specifically for the persistent memory stack).

### -field StorageDeviceEnduranceProperty

Provides info on how many bytes have been read/write from a solid-state drive (SSD). This property is supported only for Non-Volatile Memory Express (NVMe) devices that implement a certain NVMe feature.

## -remarks

The [**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md) structure is passed as input to an [**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) request to retrieve the properties of a storage device or adapter.

The optional output buffer returned from an **IOCTL_STORAGE_QUERY_PROPERTY** control code request can be one of several structures, depending on the value of the **PropertyId** member of the [**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md) structure. If the **QueryType** member of the **STORAGE_PROPERTY_QUERY** is set to **PropertyExistsQuery**, then no structure is returned.

## -see-also

[**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md)

[**STORAGE_QUERY_TYPE**](ne-ntddstor-_storage_query_type.md)

