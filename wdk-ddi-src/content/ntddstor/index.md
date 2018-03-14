---
UID: NA:ntddstor
ms.assetid: 10772569-e4d6-31f4-93aa-6bf1fcf4cb77
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntddstor.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Ntddstor.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [STORAGE_BREAK_RESERVATION_REQUEST structure](ns-ntddstor-storage_break_reservation_request.md) | The STORAGE_BREAK_RESERVATION_REQUEST structure is used in conjunction with the IOCTL_STORAGE_BREAK_RESERVATION request to free a disk resource that was previously reserved. |
| [_DEVICE_COPY_OFFLOAD_DESCRIPTOR structure](ns-ntddstor-_device_copy_offload_descriptor.md) | Used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to describe the copy offload capabilities of a storage device. |
| [_DEVICE_DATA_SET_LB_PROVISIONING_STATE structure](ns-ntddstor-_device_data_set_lb_provisioning_state.md) | The DEVICE_DATA_SET_LB_PROVISIONING_STATE structure is returned by an IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request when requesting logical block provisioning information for a data set range. |
| [_DEVICE_DATA_SET_RANGE structure](ns-ntddstor-_device_data_set_range.md) | The DEVICE_DATA_SET_RANGE structure specifies a block of data set ranges for the attributes for a device. |
| [_DEVICE_DATA_SET_REPAIR_PARAMETERS structure](ns-ntddstor-_device_data_set_repair_parameters.md) | The DEVICE_DATA_SET_REPAIR_PARAMETERS structure specifies the parameters of a storage spaces repair operation specified for a data set management action. |
| [_DEVICE_DSM_NOTIFICATION_PARAMETERS structure](ns-ntddstor-_device_dsm_notification_parameters.md) | The DEVICE_DSM_NOTIFICATION_PARAMETERS structure specifies the parameters for a notification action related to the data-set attributes for a device. |
| [_DEVICE_DSM_OFFLOAD_READ_PARAMETERS structure](ns-ntddstor-_device_dsm_offload_read_parameters.md) | The DEVICE_DSM_OFFLOAD_READ_PARAMETERS structure specifies the parameters for an offload read action related to the data-set attributes for a device. |
| [_DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS structure](ns-ntddstor-_device_dsm_offload_write_parameters.md) | The DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS structure specifies the parameters for an offload write action related to the data-set attributes for a device. |
| [_DEVICE_LB_PROVISIONING_DESCRIPTOR structure](ns-ntddstor-_device_lb_provisioning_descriptor.md) | The DEVICE_LB_PROVISIONING_DESCRIPTOR structure is one of the query result structures returned from an IOCTL_STORAGE_QUERY_PROPERTY request. This structure contains the thin provisioning capabilities for a storage device. |
| [_DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure](ns-ntddstor-_device_manage_data_set_attributes.md) | The DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure specifies a management action for the data-set attributes for a device. |
| [_DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT structure](ns-ntddstor-_device_manage_data_set_attributes_output.md) | The DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT structure describes output for IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control code requests for some data set management actions. |
| [_DEVICE_MEDIA_INFO structure](ns-ntddstor-_device_media_info.md) | A storage class driver returns an array of DEVICE_MEDIA_INFO structures, embedded in a GET_MEDIA_TYPES structure, in response to an IOCTL_STORAGE_GET_MEDIA_TYPES_EX device-control request. |
| [_DEVICE_POWER_DESCRIPTOR structure](ns-ntddstor-_device_power_descriptor.md) | Used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY control code to describes the power capabilities of a storage device. |
| [_DEVICE_SEEK_PENALTY_DESCRIPTOR structure](ns-ntddstor-_device_seek_penalty_descriptor.md) | The DEVICE_SEEK_PENALTY_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the seek penalty descriptor data for a device. |
| [_DEVICE_TRIM_DESCRIPTOR structure](ns-ntddstor-_device_trim_descriptor.md) | The DEVICE_TRIM_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the trim descriptor data for a device. |
| [_DEVICE_WRITE_AGGREGATION_DESCRIPTOR structure](ns-ntddstor-_device_write_aggregation_descriptor.md) | Reserved for system use. |
| [_GET_MEDIA_TYPES structure](ns-ntddstor-_get_media_types.md) | The GET_MEDIA_TYPES structure is used in conjunction with the IOCTL_STORAGE_GET_MEDIA_TYPES_EX request to retrieve information about the types of media supported by a device. |
| [_PERSISTENT_RESERVE_COMMAND structure](ns-ntddstor-_persistent_reserve_command.md) | The PERSISTENT_RESERVE_COMMAND structure is used together with the IOCTL_STORAGE_PERSISTENT_RESERVE_IN and IOCTL_STORAGE_PERSISTENT_RESERVE_OUT requests to obtain and control information about persistent reservations and reservation keys that are active within a device server. |
| [_STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure](ns-ntddstor-_storage_access_alignment_descriptor.md) | The STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the storage access alignment descriptor data for a device. |
| [_STORAGE_ADAPTER_DESCRIPTOR structure](ns-ntddstor-_storage_adapter_descriptor.md) | The STORAGE_ADAPTER_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the storage adapter descriptor data for a device. |
| [_STORAGE_BUS_RESET_REQUEST structure](ns-ntddstor-_storage_bus_reset_request.md) | The STORAGE_BUS_RESET_REQUEST structure is used in conjunction with the IOCTL_STORAGE_RESET_BUS request to specify the path of the bus to be reset. |
| [_STORAGE_CRYPTO_CAPABILITY structure](ns-ntddstor-_storage_crypto_capability.md) | Reserved for system use. |
| [_STORAGE_CRYPTO_DESCRIPTOR structure](ns-ntddstor-_storage_crypto_descriptor.md) | Reserved for system use. |
| [_STORAGE_DESCRIPTOR_HEADER structure](ns-ntddstor-_storage_descriptor_header.md) | The STORAGE_DESCRIPTOR_HEADER structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the properties of a storage device or adapter. |
| [_STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR structure](ns-ntddstor-_storage_device_attributes_descriptor.md) | The STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR structure is used to retrieve the attributes information for a device. |
| [_STORAGE_DEVICE_DESCRIPTOR structure](ns-ntddstor-_storage_device_descriptor.md) | The STORAGE_DEVICE_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the storage device descriptor data for a device. |
| [_STORAGE_DEVICE_ID_DESCRIPTOR structure](ns-ntddstor-_storage_device_id_descriptor.md) | The STORAGE_DEVICE_ID_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the device ID descriptor data for a device. |
| [_STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR structure](ns-ntddstor-_storage_device_io_capability_descriptor.md) | The output buffer for the StorageDeviceIoCapabilityProperty as defined in STORAGE_PROPERTY_ID. |
| [_STORAGE_DEVICE_NUMBER structure](ns-ntddstor-_storage_device_number.md) | The STORAGE_DEVICE_NUMBER structure is used in conjunction with the IOCTL_STORAGE_GET_DEVICE_NUMBER request to retrieve the FILE_DEVICE_XXX device type, the device number, and, for a device that can be partitioned, the partition number assigned to a device by the driver when the device is started. |
| [_STORAGE_DEVICE_POWER_CAP structure](ns-ntddstor-_storage_device_power_cap.md) | This structure is used as an input and output buffer for the IOCTL_STORAGE_DEVICE_POWER_CAP. |
| [_STORAGE_DEVICE_RESILIENCY_DESCRIPTOR structure](ns-ntddstor-_storage_device_resiliency_descriptor.md) | Reserved for system use. |
| [_STORAGE_DIAGNOSTIC_DATA structure](ns-ntddstor-_storage_diagnostic_data.md) | Describes diagnostic data about the storage driver stack. The STORAGE_DIAGNOSTIC_DATA structure is provided in the output buffer of an IOCTL_STORAGE_DIAGNOSTIC request. |
| [_STORAGE_DIAGNOSTIC_REQUEST structure](ns-ntddstor-_storage_diagnostic_request.md) | Describes a diagnostic request about the storage driver stack. The STORAGE_DIAGNOSTIC_REQUEST structure is provided in the input buffer of an IOCTL_STORAGE_DIAGNOSTIC request. |
| [_STORAGE_HOTPLUG_INFO structure](ns-ntddstor-_storage_hotplug_info.md) | The STORAGE_HOTPLUG_INFO structure provides hotplug information for a device. |
| [_STORAGE_HW_FIRMWARE_ACTIVATE structure](ns-ntddstor-_storage_hw_firmware_activate.md) | This structure contains information about the downloaded firmware to activate. |
| [_STORAGE_HW_FIRMWARE_DOWNLOAD structure](ns-ntddstor-_storage_hw_firmware_download.md) | This structure contains a firmware image payload to be downloaded to the target. |
| [_STORAGE_HW_FIRMWARE_INFO structure](ns-ntddstor-_storage_hw_firmware_info.md) | This structure contains information about the device firmware. |
| [_STORAGE_HW_FIRMWARE_INFO_QUERY structure](ns-ntddstor-_storage_hw_firmware_info_query.md) | This structure contains information about the device firmware. |
| [_STORAGE_HW_FIRMWARE_SLOT_INFO structure](ns-ntddstor-_storage_hw_firmware_slot_info.md) | This structure contains information about a slot on a device. |
| [_STORAGE_IDENTIFIER structure](ns-ntddstor-_storage_identifier.md) | The STORAGE_IDENTIFIER structure represents a SCSI identification descriptor. |
| [_STORAGE_LB_PROVISIONING_MAP_RESOURCES structure](ns-ntddstor-_storage_lb_provisioning_map_resources.md) | The STORAGE_LB_PROVISIONING_MAP_RESOURCES structure contains, when valid, the count of available and used bytes mapped to a storage device. This structure is returned from an IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES request. |
| [_STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR structure](ns-ntddstor-_storage_medium_product_type_descriptor.md) | Used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to describe the product type of a storage device. |
| [_STORAGE_MINIPORT_DESCRIPTOR structure](ns-ntddstor-_storage_miniport_descriptor.md) | Reserved for system use. |
| [_STORAGE_OFFLOAD_READ_OUTPUT structure](ns-ntddstor-_storage_offload_read_output.md) | The STORAGE_OFFLOAD_READ_OUTPUT structure is the output of an IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control code request when the Action member of DEVICE_MANAGE_DATA_SET_ATTRIBUTES is set to DeviceDsmAction_OffloadRead. |
| [_STORAGE_OFFLOAD_TOKEN structure](ns-ntddstor-_storage_offload_token.md) | The STORAGE_OFFLOAD_TOKEN structure contains a token value that serves as a representation of a data set range within a file on a volume. This structure is used in performing offload reads and writes. |
| [_STORAGE_OFFLOAD_WRITE_OUTPUT structure](ns-ntddstor-_storage_offload_write_output.md) | The STORAGE_OFFLOAD_WRITE_OUTPUT structure is the output of an IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control code request when the Action member of DEVICE_MANAGE_DATA_SET_ATTRIBUTES is set to DeviceDsmAction_OffloadWrite. |
| [_STORAGE_PHYSICAL_ADAPTER_DATA structure](ns-ntddstor-_storage_physical_adapter_data.md) | Specifies the physical device data of a storage adapter. |
| [_STORAGE_PHYSICAL_DEVICE_DATA structure](ns-ntddstor-_storage_physical_device_data.md) | Specifies the physical device data of a storage device. |
| [_STORAGE_PHYSICAL_NODE_DATA structure](ns-ntddstor-_storage_physical_node_data.md) | Specifies the physical device data of a storage node. |
| [_STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR structure](ns-ntddstor-_storage_physical_topology_descriptor.md) | Describes the physical topology of storage in a system. |
| [_STORAGE_PREDICT_FAILURE structure](ns-ntddstor-_storage_predict_failure.md) | The STORAGE_PREDICT_FAILURE structure is used in conjunction with IOCTL_STORAGE_PREDICT_FAILURE to report whether a device is currently predicting a failure. |
| [_STORAGE_PROPERTY_QUERY structure](ns-ntddstor-_storage_property_query.md) | This structure is used in conjunction with IOCTL_STORAGE_QUERY_PROPERTY to retrieve the properties of a storage device or adapter. |
| [_STORAGE_PROTOCOL_COMMAND structure](ns-ntddstor-_storage_protocol_command.md) | This structure is used as an input buffer when using the pass-through mechanism to issue a vendor-specific command to a storage device (via IOCTL_STORAGE_PROTOCOL_COMMAND). |
| [_STORAGE_PROTOCOL_DATA_DESCRIPTOR structure](ns-ntddstor-_storage_protocol_data_descriptor.md) | This structure is used in conjunction with IOCTL_STORAGE_QUERY_PROPERTY to return protocol-specific data from a storage device or adapter. |
| [_STORAGE_PROTOCOL_SPECIFIC_DATA structure](ns-ntddstor-_storage_protocol_specific_data.md) | Describes protocol-specific device data, provided in the input and output buffer of an IOCTL_STORAGE_QUERY_PROPERTY request. |
| [_STORAGE_READ_CAPACITY structure](ns-ntddstor-_storage_read_capacity.md) | The STORAGE_READ_CAPACITY contains the disk read capacity information returned from a IOCTL_STORAGE_READ_CAPACITIY request. |
| [_STORAGE_SPEC_VERSION structure](ns-ntddstor-_storage_spec_version.md) | Indicates the specification of the storage device. |
| [_STORAGE_TEMPERATURE_DATA_DESCRIPTOR structure](ns-ntddstor-_storage_temperature_data_descriptor.md) | This structure is used in conjunction with IOCTL_STORAGE_QUERY_PROPERTY to return temperature data from a storage device or adapter. |
| [_STORAGE_TEMPERATURE_INFO structure](ns-ntddstor-_storage_temperature_info.md) | Describes device temperature data. Returned as part of STORAGE_TEMPERATURE_DATA_DESCRIPTOR when querying for temperature data with an IOCTL_STORAGE_QUERY_PROPERTY request. |
| [_STORAGE_TEMPERATURE_THRESHOLD structure](ns-ntddstor-_storage_temperature_threshold.md) | This structure is used to set the over or under temperature threshold of a storage device (via IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD). |
| [_STORAGE_WRITE_CACHE_PROPERTY structure](ns-ntddstor-_storage_write_cache_property.md) | The STORAGE_WRITE_CACHE_PROPERTY structure is used with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve information about a device's write cache property. |
| [_STORAGE_ZONE_DESCRIPTOR structure](ns-ntddstor-_storage_zone_descriptor.md) | Note  This structure is for internal use only and should not be called from your code. . |
| [_STORAGE_ZONE_GROUP structure](ns-ntddstor-_storage_zone_group.md) | Note  This structure is for internal use only and should not be called from your code. . |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_STORAGE_BREAK_RESERVATION IOCTL](ni-ntddstor-ioctl_storage_break_reservation.md) | Breaks a disk reservation. |
| [IOCTL_STORAGE_CHECK_VERIFY IOCTL](ni-ntddstor-ioctl_storage_check_verify.md) | Determines whether the media has changed on a removable-media device that the caller has opened for read or write access. |
| [IOCTL_STORAGE_CHECK_VERIFY2 IOCTL](ni-ntddstor-ioctl_storage_check_verify2.md) | Determines whether the media has changed on a removable-media device - the caller has opened with FILE_READ_ATTRIBUTES. |
| [IOCTL_STORAGE_DEVICE_POWER_CAP IOCTL](ni-ntddstor-ioctl_storage_device_power_cap.md) | A driver can use IOCTL_STORAGE_DEVICE_POWER_CAP to specify a maximum operational power consumption level for a storage device. |
| [IOCTL_STORAGE_EJECTION_CONTROL IOCTL](ni-ntddstor-ioctl_storage_ejection_control.md) | Locks the device to prevent removal of the media. |
| [IOCTL_STORAGE_EJECT_MEDIA IOCTL](ni-ntddstor-ioctl_storage_eject_media.md) | Causes the device to eject the media if the device supports ejection capabilities. |
| [IOCTL_STORAGE_FIND_NEW_DEVICES IOCTL](ni-ntddstor-ioctl_storage_find_new_devices.md) | Determines whether another device that the driver supports has been connected to the I/O bus, either since the system was booted or since the driver last processed this request. |
| [IOCTL_STORAGE_FIRMWARE_ACTIVATE IOCTL](ni-ntddstor-ioctl_storage_firmware_activate.md) | A driver can use IOCTL_STORAGE_FIRMWARE_ACTIVATE to activate a firmware image on a storage device. |
| [IOCTL_STORAGE_FIRMWARE_DOWNLOAD IOCTL](ni-ntddstor-ioctl_storage_firmware_download.md) | A driver can use IOCTL_STORAGE_FIRMWARE_DOWNLOAD to download a firmware image to a storage device, but does not activate it. |
| [IOCTL_STORAGE_FIRMWARE_GET_INFO IOCTL](ni-ntddstor-ioctl_storage_firmware_get_info.md) | A driver can use IOCTL_STORAGE_FIRMWARE_GET_INFO to query a storage device for detailed firmware information. |
| [IOCTL_STORAGE_GET_DEVICE_NUMBER IOCTL](ni-ntddstor-ioctl_storage_get_device_number.md) | Returns a STORAGE_DEVICE_NUMBER structure that contains the FILE_DEVICE_XXX type, device number, and, for a partitionable device, the partition number assigned to a device by the driver when the device is started. |
| [IOCTL_STORAGE_GET_HOTPLUG_INFO IOCTL](ni-ntddstor-ioctl_storage_get_hotplug_info.md) | Retrieves the hotplug configuration of the specified device. |
| [IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES IOCTL](ni-ntddstor-ioctl_storage_get_lb_provisioning_map_resources.md) | The IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES request is sent to the storage class driver to determine available and used mapping resources on a storage device. |
| [IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER IOCTL](ni-ntddstor-ioctl_storage_get_media_serial_number.md) | Queries the USB generic parent driver for the serial number of a USB device. |
| [IOCTL_STORAGE_GET_MEDIA_TYPES IOCTL](ni-ntddstor-ioctl_storage_get_media_types.md) | Returns information about the geometry of floppy drives. |
| [IOCTL_STORAGE_GET_MEDIA_TYPES_EX IOCTL](ni-ntddstor-ioctl_storage_get_media_types_ex.md) | Returns information about the types of media supported by a device. |
| [IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS IOCTL](ni-ntddstor-ioctl_storage_get_physical_element_status.md) | The IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS control code queries for and returns the physical element status from a device. |
| [IOCTL_STORAGE_LOAD_MEDIA IOCTL](ni-ntddstor-ioctl_storage_load_media.md) | Causes media to be loaded in a device that the caller has opened for read or write access. |
| [IOCTL_STORAGE_LOAD_MEDIA2 IOCTL](ni-ntddstor-ioctl_storage_load_media2.md) | Causes media to be loaded in a device that the caller has opened with FILE_READ_ATTRIBUTES. |
| [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES IOCTL](ni-ntddstor-ioctl_storage_manage_data_set_attributes.md) | This IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request is used to send a manage data set attributes request to a storage device. |
| [IOCTL_STORAGE_MCN_CONTROL IOCTL](ni-ntddstor-ioctl_storage_mcn_control.md) | Temporarily enables or disables delivery of the custom PnP events GUID_IO_MEDIA_ARRIVAL and GUID_IO_MEDIA_REMOVAL on a removable-media device. |
| [IOCTL_STORAGE_MEDIA_REMOVAL IOCTL](ni-ntddstor-ioctl_storage_media_removal.md) | Locks the device to prevent removal of the media. |
| [IOCTL_STORAGE_PERSISTENT_RESERVE_IN IOCTL](ni-ntddstor-ioctl_storage_persistent_reserve_in.md) | The generic storage class driver (classpnp.sys) exposes an I/O control (IOCTL) interface for issuing Persistent Reserve In commands. |
| [IOCTL_STORAGE_PERSISTENT_RESERVE_OUT IOCTL](ni-ntddstor-ioctl_storage_persistent_reserve_out.md) | The generic storage class driver (classpnp.sys) exposes an I/O control (IOCTL) interface for issuing Persistent Reserve Out commands. |
| [IOCTL_STORAGE_PREDICT_FAILURE IOCTL](ni-ntddstor-ioctl_storage_predict_failure.md) | Polls for a prediction of device failure. |
| [IOCTL_STORAGE_PROTOCOL_COMMAND IOCTL](ni-ntddstor-ioctl_storage_protocol_command.md) | A driver can use IOCTL_STORAGE_PROTOCOL_COMMAND to pass vendor-specific commands to a storage device. |
| [IOCTL_STORAGE_QUERY_PROPERTY IOCTL](ni-ntddstor-ioctl_storage_query_property.md) | A driver can use IOCTL_STORAGE_QUERY_PROPERTY to return properties of a storage device or adapter. |
| [IOCTL_STORAGE_READ_CAPACITY IOCTL](ni-ntddstor-ioctl_storage_read_capacity.md) | The IOCTL_STORAGE_READ_CAPACITY request returns the read capacity information for the target storage device. |
| [IOCTL_STORAGE_REINITIALIZE_MEDIA IOCTL](ni-ntddstor-ioctl_storage_reinitialize_media.md) | A driver can use the IOCTL_STORAGE_REINITIALIZE_MEDIA control code to reinitialize/erase a device. |
| [IOCTL_STORAGE_RELEASE IOCTL](ni-ntddstor-ioctl_storage_release.md) | Releases a device previously reserved for the exclusive use of the caller on a bus that supports multiple initiators and the concept of reserving a device, such as a SCSI bus. |
| [IOCTL_STORAGE_RESERVE IOCTL](ni-ntddstor-ioctl_storage_reserve.md) | Claims a device for the exclusive use of the caller on a bus that supports multiple initiators and the concept of reserving a device, such as a SCSI bus. |
| [IOCTL_STORAGE_RESET_BUS IOCTL](ni-ntddstor-ioctl_storage_reset_bus.md) | Resets an I/O bus and, indirectly, each device on the bus. |
| [IOCTL_STORAGE_RESET_DEVICE IOCTL](ni-ntddstor-ioctl_storage_reset_device.md) | If possible, resets a non-SCSI storage device without affecting other devices on the bus. |
| [IOCTL_STORAGE_SET_HOTPLUG_INFO IOCTL](ni-ntddstor-ioctl_storage_set_hotplug_info.md) | Sets the hotplug configuration of the specified device. |
| [IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD IOCTL](ni-ntddstor-ioctl_storage_set_temperature_threshold.md) | A driver can use IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD to set the temperature threshold of a storage device (when supported by the hardware). |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_STORAGE_COMPONENT_HEALTH_STATUS enumeration](ne-ntddstor-_storage_component_health_status.md) | Indicates the health status of a storage device. |
| [_STORAGE_CRYPTO_ALGORITHM_ID enumeration](ne-ntddstor-_storage_crypto_algorithm_id.md) | The STORAGE_CRYPTO_ALGORITHM_ID enum provides an output buffer for StorageAdapterCryptoProperty and PropertyStandardQuery. |
| [_STORAGE_CRYPTO_KEY_SIZE enumeration](ne-ntddstor-_storage_crypto_key_size.md) | The STORAGE_CRYPTO_KEY_SIZE enum returns the Size of the key in bits. |
| [_STORAGE_DEVICE_FORM_FACTOR enumeration](ne-ntddstor-_storage_device_form_factor.md) | Indicates the form factor of a storage device. |
| [_STORAGE_DEVICE_POWER_CAP_UNITS enumeration](ne-ntddstor-_storage_device_power_cap_units.md) | The units of the maximum power threshold. |
| [_STORAGE_DIAGNOSTIC_LEVEL enumeration](ne-ntddstor-_storage_diagnostic_level.md) | The STORAGE_DIAGNOSTIC_LEVEL enumeration specifies the target type of a storage diagnostic. |
| [_STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration](ne-ntddstor-_storage_diagnostic_target_type.md) | The STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration specifies the target type of a storage diagnostic. |
| [_STORAGE_MEDIA_TYPE enumeration](ne-ntddstor-_storage_media_type.md) | The STORAGE_MEDIA_TYPE enumeration is used in conjunction with the IOCTL_STORAGE_GET_MEDIA_TYPES_EX request to query the class driver for the types of media that a device supports. |
| [_STORAGE_PROTOCOL_ATA_DATA_TYPE enumeration](ne-ntddstor-_storage_protocol_ata_data_type.md) | The ATA protocol data type. |
| [_STORAGE_PROTOCOL_NVME_DATA_TYPE enumeration](ne-ntddstor-_storage_protocol_nvme_data_type.md) | Describes the type of NVMe protocol-specific data that's to be queried during an IOCTL_STORAGE_QUERY_PROPERTY request. |
| [_STORAGE_PROTOCOL_TYPE enumeration](ne-ntddstor-_storage_protocol_type.md) | This enumeration is used to define the different storage command protocols that are used between software and hardware. |
| [_STORAGE_PROTOCOL_UFS_DATA_TYPE enumeration](ne-ntddstor-_storage_protocol_ufs_data_type.md) | The UFS (Universal Flash Storage) data type. Describes the type of UFS specific data that's to be queried during an IOCTL_STORAGE_QUERY_PROPERTY request. |
| [_STORAGE_QUERY_TYPE enumeration](ne-ntddstor-_storage_query_type.md) | The STORAGE_QUERY_TYPE enumeration is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the properties of a storage device or adapter. |
| [_STORAGE_ZONES_ATTRIBUTES enumeration](ne-ntddstor-_storage_zones_attributes.md) | Note  This structure is for internal use only and should not be called from your code. . |
| [_STORAGE_ZONE_CONDITION enumeration](ne-ntddstor-_storage_zone_condition.md) | Note  This structure is for internal use only and should not be called from your code. . |
