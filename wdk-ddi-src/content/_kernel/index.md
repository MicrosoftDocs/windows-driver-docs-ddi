---
UID: TP:kernel
ms.assetid: f7c71d77-9a5b-3320-80a1-302b75314d1e
ms.author: windowsdriverdev
ms.date: 03/29/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Windows kernel


Overview of the Windows kernel technology.

To develop Windows kernel, you need these headers:

 * [ntpoapi.h](..\ntpoapi\index.md)
 * [aux_klib.h](..\aux_klib\index.md)
 * [ntintsafe.h](..\ntintsafe\index.md)
 * [pwmutil.h](..\pwmutil\index.md)
 * [poclass.h](..\poclass\index.md)
 * [ntnls.h](..\ntnls\index.md)
 * [hwnclx.h](..\hwnclx\index.md)
 * [ntddk.h](..\ntddk\index.md)
 * [ioaccess.h](..\ioaccess\index.md)
 * [pepfx.h](..\pepfx\index.md)
 * [vpci.h](..\vpci\index.md)
 * [pep_x.h](..\pep_x\index.md)
 * [iointex.h](..\iointex\index.md)
 * [wmistr.h](..\wmistr\index.md)
 * [wdm.h](..\wdm\index.md)
 * [wmidata.h](..\wmidata\index.md)
 * [procgrp.h](..\procgrp\index.md)
 * [pcivirt.h](..\pcivirt\index.md)
 * [ntstrsafe.h](..\ntstrsafe\index.md)
 * [wmilib.h](..\wmilib\index.md)
 * [ntddsfio.h](..\ntddsfio\index.md)
 * [wdmsec.h](..\wdmsec\index.md)
 * [ntddsysenv.h](..\ntddsysenv\index.md)

For the programming guide, see [Windows kernel](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel).

## Structures

| Title   | Description   |
| ---- |:---- |
| [CM_Power_Data_s structure](..\wmiguid\ns-ntpoapi-cm_power_data_s.md) | The CM_POWER_DATA structure contains information about a device's power management state and capabilities. |
| [CM_Power_Data_s structure](..\wmiguid\ns-wdm-cm_power_data_s.md) | The CM_POWER_DATA structure contains information about a device's power management state and capabilities. |
| [CORRELATION_VECTOR structure](..\wmiguid\ns-ntddk-correlation_vector.md) | Store the correlation vector that is used to reference events and the generated logs for diagnostic purposes. |
| [WMIREGGUIDW structure](..\wmiguid\ns-wmistr-wmiregguidw.md) | The WMIREGGUID structure contains new or updated registration information for a data block or event block. |
| [WMIREGINFOW structure](..\wmiguid\ns-wmistr-wmireginfow.md) | The WMIREGINFO structure contains information provided by a driver to register or update its data blocks and event blocks. |
| [_AUX_MODULE_BASIC_INFO structure](..\wmiguid\ns-aux_klib-_aux_module_basic_info.md) | The AUX_MODULE_BASIC_INFO structure contains basic information about a loaded image module. |
| [_AUX_MODULE_EXTENDED_INFO structure](..\wmiguid\ns-aux_klib-_aux_module_extended_info.md) | The AUX_MODULE_EXTENDED_INFO structure contains extended information about a loaded image module. |
| [_BDCB_IMAGE_INFORMATION structure](..\wmiguid\ns-ntddk-_bdcb_image_information.md) | The BDCB_IMAGE_INFORMATION structure describes information about a boot-start driver that is about to be initialized, provided by Windows to a boot-start driver's BOOT_DRIVER_CALLBACK_FUNCTION routine. |
| [_BDCB_STATUS_UPDATE_CONTEXT structure](..\wmiguid\ns-ntddk-_bdcb_status_update_context.md) | The BDCB_STATUS_UPDATE_CONTEXT structure describes a status update provided by Windows to a boot-start driver's BOOT_DRIVER_CALLBACK_FUNCTION routine. |
| [_BOOTDISK_INFORMATION structure](..\wmiguid\ns-wdm-_bootdisk_information.md) | The BOOTDISK_INFORMATION structure contains basic information describing the boot and system disks. |
| [_BOOTDISK_INFORMATION_EX structure](..\wmiguid\ns-wdm-_bootdisk_information_ex.md) | The BOOTDISK_INFORMATION_EX structure contains extended information describing the boot and system disks. |
| [_BUS_INTERFACE_STANDARD structure](..\wmiguid\ns-wdm-_bus_interface_standard.md) | The BUS_INTERFACE_STANDARD interface structure enables device drivers to make direct calls to parent bus driver routines. This structure defines the GUID_BUS_INTERFACE_STANDARD interface. |
| [_CLFS_LOG_NAME_INFORMATION structure](..\wmiguid\ns-wdm-_clfs_log_name_information.md) | The CLFS_LOG_NAME_INFORMATION structure holds the name of a Common Log File System (CLFS) stream or log. |
| [_CLFS_MGMT_CLIENT_REGISTRATION structure](..\wmiguid\ns-wdm-_clfs_mgmt_client_registration.md) | The CLFS_MGMT_CLIENT_REGISTRATION structure is given to CLFS management by clients who manage their own logs. |
| [_CLFS_MGMT_POLICY structure](..\wmiguid\ns-wdm-_clfs_mgmt_policy.md) | The CLFS_MGMT_POLICY structure holds a description of a policy for managing a CLFS log. |
| [_CLFS_STREAM_ID_INFORMATION structure](..\wmiguid\ns-wdm-_clfs_stream_id_information.md) | The CLFS_STREAM_ID_INFORMATION structure holds a value that identifies a stream in a Common Log File System (CLFS) log. |
| [_CLS_CONTAINER_INFORMATION structure](..\wmiguid\ns-wdm-_cls_container_information.md) | The CLFS_CONTAINER_INFORMATION structure holds descriptive information for an individual container in a Common Log File System (CLFS) log. |
| [_CLS_INFORMATION structure](..\wmiguid\ns-wdm-_cls_information.md) | The CLFS_INFORMATION structure holds metadata and state information for a Common Log File System (CLFS) stream and/or its underlying physical log. |
| [_CLS_IO_STATISTICS structure](..\wmiguid\ns-wdm-_cls_io_statistics.md) | The CLFS_IO_STATISTICS structure holds I/O statistics data for a Common Log File System (CLFS) log. |
| [_CLS_IO_STATISTICS_HEADER structure](..\wmiguid\ns-wdm-_cls_io_statistics_header.md) | The CLFS_IO_STATISTICS_HEADER structure holds the header portion of a CLFS_IO_STATISTICS structure. |
| [_CLS_LSN structure](..\wmiguid\ns-wdm-_cls_lsn.md) | The CLFS_LSN structure identifies an individual record in a Common Log File System (CLFS) stream. |
| [_CLS_SCAN_CONTEXT structure](..\wmiguid\ns-wdm-_cls_scan_context.md) | The CLFS_SCAN_CONTEXT structure holds context information to support a scan of the containers in a Common Log File System (CLFS) log. |
| [_CLS_WRITE_ENTRY structure](..\wmiguid\ns-wdm-_cls_write_entry.md) | The CLFS_WRITE_ENTRY structure holds the address and size of a buffer that contains one unit of data to be written to a Common Log File System (CLFS) stream. |
| [_CM_EISA_FUNCTION_INFORMATION structure](..\wmiguid\ns-wdm-_cm_eisa_function_information.md) | The CM_EISA_FUNCTION_INFORMATION structure defines detailed EISA configuration information returned by HalGetBusData for the input BusDataType EisaConfiguration, or by HalGetBusDataByOffset for the input BusDataType EisaConfiguration and the Offset zero, assuming the caller-allocated Buffer is of sufficient Length. |
| [_CM_EISA_SLOT_INFORMATION structure](..\wmiguid\ns-wdm-_cm_eisa_slot_information.md) | The CM_EISA_SLOT_INFORMATION structure defines EISA configuration header information returned by HalGetBusData for the input BusDataType = EisaConfiguration, or by HalGetBusDataByOffset for the inputs BusDataType = EisaConfiguration and Offset = 0, assuming the caller-allocated Buffer is of sufficient Length. |
| [_CM_FLOPPY_DEVICE_DATA structure](..\wmiguid\ns-wdm-_cm_floppy_device_data.md) | The CM_FLOPPY_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a floppy controller if the system can collect this information during the boot process. |
| [_CM_FULL_RESOURCE_DESCRIPTOR structure](..\wmiguid\ns-wdm-_cm_full_resource_descriptor.md) | The CM_FULL_RESOURCE_DESCRIPTOR structure specifies a set of system hardware resources of various types, assigned to a device that is connected to a specific bus. This structure is contained within a CM_RESOURCE_LIST structure. |
| [_CM_INT13_DRIVE_PARAMETER structure](..\wmiguid\ns-wdm-_cm_int13_drive_parameter.md) | The CM_INT13_DRIVE_PARAMETER structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a disk controller if the system can collect this information during the boot process. |
| [_CM_KEYBOARD_DEVICE_DATA structure](..\wmiguid\ns-wdm-_cm_keyboard_device_data.md) | The CM_KEYBOARD_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a keyboard peripheral if the system can collect this information during the boot process. |
| [_CM_MCA_POS_DATA structure](..\wmiguid\ns-wdm-_cm_mca_pos_data.md) | The CM_MCA_POS_DATA structure is obsolete. It defines IBM-compatible MCA POS configuration information for a slot. |
| [_CM_PARTIAL_RESOURCE_DESCRIPTOR structure](..\wmiguid\ns-wdm-_cm_partial_resource_descriptor.md) | The CM_PARTIAL_RESOURCE_DESCRIPTOR structure specifies one or more system hardware resources, of a single type, assigned to a device. |
| [_CM_PARTIAL_RESOURCE_LIST structure](..\wmiguid\ns-wdm-_cm_partial_resource_list.md) | The CM_PARTIAL_RESOURCE_LIST structure specifies a set of system hardware resources, of various types, assigned to a device. This structure is contained within a CM_FULL_RESOURCE_DESCRIPTOR structure. |
| [_CM_RESOURCE_LIST structure](..\wmiguid\ns-wdm-_cm_resource_list.md) | The CM_RESOURCE_LIST structure specifies all of the system hardware resources assigned to a device. |
| [_CM_SCSI_DEVICE_DATA structure](..\wmiguid\ns-wdm-_cm_scsi_device_data.md) | The CM_SCSI_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a SCSI HBA if the system can collect this information during the boot process. |
| [_CM_SERIAL_DEVICE_DATA structure](..\wmiguid\ns-wdm-_cm_serial_device_data.md) | The CM_SERIAL_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a serial controller if the system can collect this information during the boot process. |
| [_CONTROLLER_OBJECT structure](..\wmiguid\ns-ntddk-_controller_object.md) | A controller object represents a hardware adapter or controller with homogenous devices that are the actual targets for I/O requests. |
| [_COUNTED_REASON_CONTEXT structure](..\wmiguid\ns-ntpoapi-_counted_reason_context.md) | The COUNTED_REASON_CONTEXT structure contains one or more strings that give reasons for a power request. |
| [_COUNTED_REASON_CONTEXT structure](..\wmiguid\ns-wdm-_counted_reason_context.md) | The COUNTED_REASON_CONTEXT structure contains one or more strings that give reasons for a power request. |
| [_CPTABLEINFO structure](..\wmiguid\ns-ntnls-_cptableinfo.md) | Stores the NLS file formats. |
| [_D3COLD_SUPPORT_INTERFACE structure](..\wmiguid\ns-wdm-_d3cold_support_interface.md) | The D3COLD_SUPPORT_INTERFACE interface structure contains pointers to the routines in the GUID_D3COLD_SUPPORT_INTERFACE driver interface. |
| [_DEVICE_CAPABILITIES structure](..\wmiguid\ns-wdm-_device_capabilities.md) | A DEVICE_CAPABILITIES structure describes PnP and power capabilities of a device. This structure is returned in response to an IRP_MN_QUERY_CAPABILITIES IRP. |
| [_DEVICE_DESCRIPTION structure](..\wmiguid\ns-wdm-_device_description.md) | The DEVICE_DESCRIPTION structure describes the attributes of the physical device for which a driver is requesting a DMA adapter. |
| [_DEVICE_INTERFACE_CHANGE_NOTIFICATION structure](..\wmiguid\ns-wdm-_device_interface_change_notification.md) | The DEVICE_INTERFACE_CHANGE_NOTIFICATION structure describes a device interface that has been enabled (arrived) or disabled (removed). |
| [_DEVICE_OBJECT structure](..\wmiguid\ns-wdm-_device_object.md) | A device object represents a logical, virtual, or physical device for which a driver handles I/O requests. |
| [_DEVICE_RESET_INTERFACE_STANDARD structure](..\wmiguid\ns-wdm-_device_reset_interface_standard.md) | The DEVICE_RESET_INTERFACE_STANDARD structure enables function drivers to reset and recover malfunctioning devices. This structure describes the GUID_DEVICE_RESET_INTERFACE_STANDARD interface. |
| [_DMA_ADAPTER structure](..\wmiguid\ns-wdm-_dma_adapter.md) | The DMA_ADAPTER structure describes a system-defined interface to a DMA controller for a given device. A driver calls IoGetDmaAdapter to obtain this structure. |
| [_DMA_ADAPTER_INFO structure](..\wmiguid\ns-wdm-_dma_adapter_info.md) | The DMA_ADAPTER_INFO structure is a container for a DMA_ADAPTER_INFO_XXX structure that describes the capabilities of a system DMA controller. |
| [_DMA_ADAPTER_INFO_V1 structure](..\wmiguid\ns-wdm-_dma_adapter_info_v1.md) | The DMA_ADAPTER_INFO_V1 structure describes the capabilities of the system DMA controller that is represented by an adapter object. |
| [_DMA_OPERATIONS structure](..\wmiguid\ns-wdm-_dma_operations.md) | The DMA_OPERATIONS structure provides a table of pointers to functions that control the operation of a DMA controller. |
| [_DMA_TRANSFER_INFO structure](..\wmiguid\ns-wdm-_dma_transfer_info.md) | The DMA_TRANSFER_INFO structure is a container for a DMA_TRANSFER_INFO_XXX structure that describes the allocation requirements for a scatter/gather list. |
| [_DMA_TRANSFER_INFO_V1 structure](..\wmiguid\ns-wdm-_dma_transfer_info_v1.md) | The DMA_TRANSFER_INFO_V1 structure contains the allocation requirements for a scatter/gather list that describes the I/O data buffer for a DMA transfer. |
| [_DRIVER_OBJECT structure](..\wmiguid\ns-wdm-_driver_object.md) | Each driver object represents the image of a loaded kernel-mode driver. |
| [_ENLISTMENT_BASIC_INFORMATION structure](..\wmiguid\ns-wdm-_enlistment_basic_information.md) | The ENLISTMENT_BASIC_INFORMATION structure contains information about an enlistment object. |
| [_EXT_DELETE_PARAMETERS structure](..\wmiguid\ns-wdm-_ext_delete_parameters.md) | The EXT_DELETE_PARAMETERS structure contains an extended set of parameters for the ExDeleteTimer routine. |
| [_EXT_SET_PARAMETERS_V0 structure](..\wmiguid\ns-wdm-_ext_set_parameters_v0.md) | The EXT_SET_PARAMETERS structure contains an extended set of parameters for the ExSetTimer routine. |
| [_FILE_ALIGNMENT_INFORMATION structure](..\wmiguid\ns-ntddk-_file_alignment_information.md) | The FILE_ALIGNMENT_INFORMATION structure is used as an argument to the ZwQueryInformationFile routine. |
| [_FILE_ATTRIBUTE_TAG_INFORMATION structure](..\wmiguid\ns-ntddk-_file_attribute_tag_information.md) | The FILE_ATTRIBUTE_TAG_INFORMATION structure is used as an argument to ZwQueryInformationFile. |
| [_FILE_BASIC_INFORMATION structure](..\wmiguid\ns-wdm-_file_basic_information.md) | The FILE_BASIC_INFORMATION structure is used as an argument to routines that query or set file information. |
| [_FILE_DISPOSITION_INFORMATION structure](..\wmiguid\ns-ntddk-_file_disposition_information.md) | The FILE_DISPOSITION_INFORMATION structure is used as an argument to the ZwSetInformationFile routine. |
| [_FILE_END_OF_FILE_INFORMATION structure](..\wmiguid\ns-ntddk-_file_end_of_file_information.md) | The FILE_END_OF_FILE_INFORMATION structure is used as an argument to the ZwSetInformationFile routine. |
| [_FILE_FS_DEVICE_INFORMATION structure](..\wmiguid\ns-wdm-_file_fs_device_information.md) | The FILE_FS_DEVICE_INFORMATION structure provides file system device information about the type of device object associated with a file object. |
| [_FILE_FULL_EA_INFORMATION structure](..\wmiguid\ns-wdm-_file_full_ea_information.md) | The FILE_FULL_EA_INFORMATION structure provides extended attribute (EA) information. This structure is used primarily by network drivers. |
| [_FILE_IO_PRIORITY_HINT_INFORMATION structure](..\wmiguid\ns-wdm-_file_io_priority_hint_information.md) | The FILE_IO_PRIORITY_HINT_INFORMATION structure is used by the ZwQueryInformationFile and ZwSetInformationFile routines to query and set the default IRP priority hint for requests on the specified file handle. |
| [_FILE_IS_REMOTE_DEVICE_INFORMATION structure](..\wmiguid\ns-wdm-_file_is_remote_device_information.md) | The FILE_IS_REMOTE_DEVICE_INFORMATION structure is used as an argument to the ZwQueryInformationFile routine. |
| [_FILE_NAME_INFORMATION structure](..\wmiguid\ns-ntddk-_file_name_information.md) | The FILE_NAME_INFORMATION structure is used as argument to the ZwQueryInformationFile and ZwSetInformationFile routines. |
| [_FILE_NETWORK_OPEN_INFORMATION structure](..\wmiguid\ns-wdm-_file_network_open_information.md) | The FILE_NETWORK_OPEN_INFORMATION structure is used as an argument to ZwQueryInformationFile. |
| [_FILE_OBJECT structure](..\wmiguid\ns-wdm-_file_object.md) | The FILE_OBJECT structure is used by the system to represent a file object. |
| [_FILE_POSITION_INFORMATION structure](..\wmiguid\ns-wdm-_file_position_information.md) | The FILE_POSITION_INFORMATION structure is used as an argument to routines that query or set file information. |
| [_FILE_STANDARD_INFORMATION structure](..\wmiguid\ns-wdm-_file_standard_information.md) | The FILE_STANDARD_INFORMATION structure is used as an argument to routines that query or set file information. |
| [_FILE_STANDARD_INFORMATION_EX structure](..\wmiguid\ns-wdm-_file_standard_information_ex.md) | The FILE_STANDARD_INFORMATION_EX structure is used as an argument to routines that query or set file information. |
| [_FILE_VALID_DATA_LENGTH_INFORMATION structure](..\wmiguid\ns-ntddk-_file_valid_data_length_information.md) | The FILE_VALID_DATA_LENGTH_INFORMATION structure is used as an argument to ZwSetInformationFile. |
| [_FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS structure](..\wmiguid\ns-wdm-_function_level_device_reset_parameters.md) | The FUNCTION_LEVEL_DEVICE_RESET_PARAMETER structure is used as an argument to the DeviceReset routine of the GUID_DEVICE_RESET_INTERFACE_STANDARD interface. |
| [_GENERIC_MAPPING structure](..\wmiguid\ns-wdm-_generic_mapping.md) | The GENERIC_MAPPING structure describes the ACCESS_MASK value of specific access rights associated with each type of generic access right. |
| [_HARDWARE_COUNTER structure](..\wmiguid\ns-ntddk-_hardware_counter.md) | The HARDWARE_COUNTER structure contains information about a hardware counter. |
| [_HWPROFILE_CHANGE_NOTIFICATION structure](..\wmiguid\ns-wdm-_hwprofile_change_notification.md) | The HWPROFILE_CHANGE_NOTIFICATION structure describes an event related to a hardware profile configuration change. |
| [_IMAGE_INFO structure](..\wmiguid\ns-ntddk-_image_info.md) | Used by driver's load-image routine (PLOAD_IMAGE_NOTIFY_ROUTINE) to specify image information. |
| [_IMAGE_INFO_EX structure](..\wmiguid\ns-ntddk-_image_info_ex.md) | Extended version of the image information structure (see IMAGE_INFO). |
| [_IMAGE_POLICY_ENTRY structure](..\wmiguid\ns-wdm-_image_policy_entry.md) | This structure is not supported. |
| [_IMAGE_POLICY_METADATA structure](..\wmiguid\ns-wdm-_image_policy_metadata.md) | This structure is not supported. |
| [_INTERFACE structure](..\wmiguid\ns-wdm-_interface.md) | The INTERFACE structure describes an interface that is exported by a driver for use by other drivers. |
| [_IO_CONNECT_INTERRUPT_PARAMETERS structure](..\wmiguid\ns-wdm-_io_connect_interrupt_parameters.md) | The IO_CONNECT_INTERRUPT_PARAMETERS structure contains the parameters that a driver supplies to the IoConnectInterruptEx routine to register an interrupt service routine (ISR). |
| [_IO_DISCONNECT_INTERRUPT_PARAMETERS structure](..\wmiguid\ns-wdm-_io_disconnect_interrupt_parameters.md) | The IO_DISCONNECT_INTERRUPT_PARAMETERS structure describes the parameters when unregistering an interrupt-handling routine with IoDisconnectInterruptEx. |
| [_IO_ERROR_LOG_PACKET structure](..\wmiguid\ns-wdm-_io_error_log_packet.md) | The IO_ERROR_LOG_PACKET structure serves as the header for an error log entry. |
| [_IO_INTERRUPT_MESSAGE_INFO structure](..\wmiguid\ns-wdm-_io_interrupt_message_info.md) | The IO_INTERRUPT_MESSAGE_INFO structure describes the driver's message-signaled interrupts. |
| [_IO_INTERRUPT_MESSAGE_INFO_ENTRY structure](..\wmiguid\ns-wdm-_io_interrupt_message_info_entry.md) | The IO_INTERRUPT_MESSAGE_INFO_ENTRY structure describes the properties of a single message-signaled interrupt. |
| [_IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS structure](..\wmiguid\ns-wdm-_io_report_interrupt_active_state_parameters.md) | The IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS structure contains the connection context for a registered interrupt service routine (ISR) that was connected to an interrupt or interrupts by a previous call to the IoConnectInterruptEx routine. |
| [_IO_RESOURCE_DESCRIPTOR structure](..\wmiguid\ns-wdm-_io_resource_descriptor.md) | The IO_RESOURCE_DESCRIPTOR structure describes a range of raw hardware resources, of one type, that can be used by a device. An array of IO_RESOURCE_DESCRIPTOR structures is contained within each IO_RESOURCE_LIST structure. |
| [_IO_RESOURCE_LIST structure](..\wmiguid\ns-wdm-_io_resource_list.md) | The IO_RESOURCE_LIST structure describes a range of raw hardware resources, of various types, that can be used by a device. |
| [_IO_RESOURCE_REQUIREMENTS_LIST structure](..\wmiguid\ns-wdm-_io_resource_requirements_list.md) | The IO_RESOURCE_REQUIREMENTS_LIST structure describes sets of resource configurations that can be used by a device. Each configuration represents a range of raw resources, of various types, that can be used by a device. |
| [_IO_SECURITY_CONTEXT structure](..\wmiguid\ns-wdm-_io_security_context.md) | The IO_SECURITY_CONTEXT structure represents the security context of an IRP_MJ_CREATE request. |
| [_IO_SESSION_CONNECT_INFO structure](..\wmiguid\ns-wdm-_io_session_connect_info.md) | The IO_SESSION_CONNECT_INFO structure provides information about a user session. |
| [_IO_SESSION_STATE_INFORMATION structure](..\wmiguid\ns-wdm-_io_session_state_information.md) | The IO_SESSION_STATE_INFORMATION structure contains information about the state of a user session. |
| [_IO_SESSION_STATE_NOTIFICATION structure](..\wmiguid\ns-wdm-_io_session_state_notification.md) | The IO_SESSION_STATE_NOTIFICATION structure contains information that a kernel-mode driver supplies to the IoRegisterContainerNotification routine when the driver registers to receive notifications of session events. |
| [_IO_STACK_LOCATION structure](..\wmiguid\ns-wdm-_io_stack_location.md) | The IO_STACK_LOCATION structure defines an I/O stack location, which is an entry in the I/O stack that is associated with each IRP. |
| [_IO_STATUS_BLOCK structure](..\wmiguid\ns-wdm-_io_status_block.md) | A driver sets an IRP's I/O status block to indicate the final status of an I/O request, before calling IoCompleteRequest for the IRP. |
| [_IRP structure](..\wmiguid\ns-wdm-_irp.md) | The IRP structure is a partially opaque structure that represents an I/O request packet. Drivers can use the following members of the IRP structure. |
| [_KBUGCHECK_ADD_PAGES structure](..\wmiguid\ns-wdm-_kbugcheck_add_pages.md) | The KBUGCHECK_ADD_PAGES structure describes one or more pages of driver-supplied data to be written by a BugCheckAddPagesCallback callback routine to the crash dump file. |
| [_KBUGCHECK_DATA structure](..\wmiguid\ns-aux_klib-_kbugcheck_data.md) | The KBUGCHECK_DATA structure contains bug check parameters. |
| [_KBUGCHECK_DUMP_IO structure](..\wmiguid\ns-wdm-_kbugcheck_dump_io.md) | The KBUGCHECK_DUMP_IO structure describes an I/O operation on the crash dump file. |
| [_KBUGCHECK_SECONDARY_DUMP_DATA structure](..\wmiguid\ns-wdm-_kbugcheck_secondary_dump_data.md) | The KBUGCHECK_SECONDARY_DUMP_DATA structure describes a section of driver-supplied data to be written by BugCheckSecondaryDumpDataCallback to the crash dump file. |
| [_KDPC_WATCHDOG_INFORMATION structure](..\wmiguid\ns-wdm-_kdpc_watchdog_information.md) | The KDPC_WATCHDOG_INFORMATION structure holds time-out information about the current deferred procedure call (DPC). |
| [_KEY_BASIC_INFORMATION structure](..\wmiguid\ns-wdm-_key_basic_information.md) | The KEY_BASIC_INFORMATION structure defines a subset of the full information that is available for a registry key. |
| [_KEY_CACHED_INFORMATION structure](..\wmiguid\ns-ntddk-_key_cached_information.md) | The KEY_CACHED_INFORMATION structure holds the cached information available for a registry key or subkey. |
| [_KEY_FULL_INFORMATION structure](..\wmiguid\ns-wdm-_key_full_information.md) | The KEY_FULL_INFORMATION structure defines the information available for a registry key, including information about its subkeys and the maximum length for their names and value entries. |
| [_KEY_NAME_INFORMATION structure](..\wmiguid\ns-ntddk-_key_name_information.md) | The KEY_NAME_INFORMATION structure holds the name and name length of the key. |
| [_KEY_NODE_INFORMATION structure](..\wmiguid\ns-wdm-_key_node_information.md) | The KEY_NODE_INFORMATION structure defines the basic information available for a registry (sub)key. |
| [_KEY_VALUE_BASIC_INFORMATION structure](..\wmiguid\ns-wdm-_key_value_basic_information.md) | The KEY_VALUE_BASIC_INFORMATION structure defines a subset of the full information available for a value entry of a registry key. |
| [_KEY_VALUE_ENTRY structure](..\wmiguid\ns-wdm-_key_value_entry.md) | The KEY_VALUE_ENTRY structure is used by the REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION structure to describe a single value entry for a registry key. |
| [_KEY_VALUE_FULL_INFORMATION structure](..\wmiguid\ns-wdm-_key_value_full_information.md) | The KEY_VALUE_FULL_INFORMATION structure defines information available for a value entry of a registry key. |
| [_KEY_VALUE_PARTIAL_INFORMATION structure](..\wmiguid\ns-wdm-_key_value_partial_information.md) | The KEY_VALUE_PARTIAL_INFORMATION structure defines a subset of the value information available for a value entry of a registry key. |
| [_KEY_VIRTUALIZATION_INFORMATION structure](..\wmiguid\ns-ntddk-_key_virtualization_information.md) | The KEY_VIRTUALIZATION_INFORMATION structure defines the basic information that is available for a registry key or subkey. |
| [_KEY_WRITE_TIME_INFORMATION structure](..\wmiguid\ns-wdm-_key_write_time_information.md) | The KEY_WRITE_TIME_INFORMATION structure is used by the system to set the last write time for a registry key. |
| [_KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT structure](..\wmiguid\ns-wdm-_ke_processor_change_notify_context.md) | The KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT structure describes the notification context that is passed to a registered callback function when a new processor is dynamically added to a hardware partition. |
| [_KTMOBJECT_CURSOR structure](..\wmiguid\ns-wdm-_ktmobject_cursor.md) | The KTMOBJECT_CURSOR structure receives enumeration information about KTM objects when a component calls ZwEnumerateTransactionObject. |
| [_LINK_SHARE_ACCESS structure](..\wmiguid\ns-wdm-_link_share_access.md) | The share access structure used by file systems for only link files. |
| [_MDL structure](..\wmiguid\ns-wdm-_mdl.md) | An MDL structure is a partially opaque structure that represents a memory descriptor list (MDL). |
| [_MM_COPY_ADDRESS structure](..\wmiguid\ns-ntddk-_mm_copy_address.md) | The MM_COPY_ADDRESS structure contains either a virtual memory address or a physical memory address. |
| [_MM_PHYSICAL_ADDRESS_LIST structure](..\wmiguid\ns-wdm-_mm_physical_address_list.md) | The MM_PHYSICAL_ADDRESS_LIST structure specifies a range of physical addresses. |
| [_NLSTABLEINFO structure](..\wmiguid\ns-ntnls-_nlstableinfo.md) | Stores the NLS file formats . |
| [_OB_CALLBACK_REGISTRATION structure](..\wmiguid\ns-wdm-_ob_callback_registration.md) | The OB_CALLBACK_REGISTRATION structure specifies the parameters when the ObRegisterCallbacks routine registers ObjectPreCallback and ObjectPostCallback callback routines. |
| [_OB_OPERATION_REGISTRATION structure](..\wmiguid\ns-wdm-_ob_operation_registration.md) | The OB_OPERATION_REGISTRATION structure specifies ObjectPreCallback and ObjectPostCallback callback routines and the types of operations that the routines are called for. |
| [_OB_POST_CREATE_HANDLE_INFORMATION structure](..\wmiguid\ns-wdm-_ob_post_create_handle_information.md) | The OB_POST_CREATE_HANDLE_INFORMATION structure provides information to a ObjectPostCallback routine about a thread or process handle that has been opened. |
| [_OB_POST_DUPLICATE_HANDLE_INFORMATION structure](..\wmiguid\ns-wdm-_ob_post_duplicate_handle_information.md) | The OB_POST_DUPLICATE_HANDLE_INFORMATION structure provides information to an ObjectPostCallback routine about a thread or process handle that has been duplicated. |
| [_OB_POST_OPERATION_INFORMATION structure](..\wmiguid\ns-wdm-_ob_post_operation_information.md) | The OB_POST_OPERATION_INFORMATION structure provides information about a process or thread handle operation to an ObjectPostCallback routine. |
| [_OB_POST_OPERATION_PARAMETERS structure](..\wmiguid\ns-wdm-_ob_post_operation_parameters.md) | The OB_POST_OPERATION_PARAMETERS union describes the operation-specific parameters for an ObjectPostCallback routine. |
| [_OB_PRE_CREATE_HANDLE_INFORMATION structure](..\wmiguid\ns-wdm-_ob_pre_create_handle_information.md) | The OB_PRE_CREATE_HANDLE_INFORMATION structure provides information to an ObjectPreCallback routine about a thread or process handle that is being opened. |
| [_OB_PRE_DUPLICATE_HANDLE_INFORMATION structure](..\wmiguid\ns-wdm-_ob_pre_duplicate_handle_information.md) | The OB_PRE_DUPLICATE_HANDLE_INFORMATION structure provides information to an ObjectPreCallback routine about a thread or process handle that is being duplicated. |
| [_OB_PRE_OPERATION_INFORMATION structure](..\wmiguid\ns-wdm-_ob_pre_operation_information.md) | The OB_PRE_OPERATION_INFORMATION structure provides information about a process or thread handle operation to an ObjectPreCallback routine. |
| [_OB_PRE_OPERATION_PARAMETERS structure](..\wmiguid\ns-wdm-_ob_pre_operation_parameters.md) | The OB_PRE_OPERATION_PARAMETERS union describes the operation-specific parameters for an ObjectPreCallback routine. |
| [_OSVERSIONINFOEXW structure](..\wmiguid\ns-wdm-_osversioninfoexw.md) | The RTL_OSVERSIONINFOEXW structure contains operating system version information. |
| [_OSVERSIONINFOW structure](..\wmiguid\ns-wdm-_osversioninfow.md) | The RTL_OSVERSIONINFOW structure contains operating system version information. |
| [_PCI_COMMON_CONFIG structure](..\wmiguid\ns-wdm-_pci_common_config.md) | The PCI_COMMON_CONFIG structure is obsolete. |
| [_PCI_MSIX_TABLE_CONFIG_INTERFACE structure](..\wmiguid\ns-wdm-_pci_msix_table_config_interface.md) | The PCI_MSIX_TABLE_CONFIG_INTERFACE structure enables device drivers to modify their MSI-X interrupt settings. This structure describes the GUID_MSIX_TABLE_CONFIG_INTERFACE interface. |
| [_PCI_SLOT_NUMBER structure](..\wmiguid\ns-wdm-_pci_slot_number.md) | The PCI_SLOT_NUMBER structure is obsolete. |
| [_PEP_ABANDON_DEVICE structure](..\wmiguid\ns-pep_x-_pep_abandon_device.md) | The PEP_ABANDON_DEVICE structure identifies a device that has been abandoned and will no longer be used by the operating system. |
| [_PEP_ABANDON_DEVICE structure](..\wmiguid\ns-pepfx-_pep_abandon_device.md) | The PEP_ABANDON_DEVICE structure identifies a device that has been abandoned and will no longer be used by the operating system. |
| [_PEP_ACPI_ABANDON_DEVICE structure](..\wmiguid\ns-pep_x-_pep_acpi_abandon_device.md) | The PEP_ACPI_ABANDON_DEVICE structure indicates whether the platform extension plug-in (PEP) accepts ownership of an abandoned device. |
| [_PEP_ACPI_ABANDON_DEVICE structure](..\wmiguid\ns-pepfx-_pep_acpi_abandon_device.md) | The PEP_ACPI_ABANDON_DEVICE structure indicates whether the platform extension plug-in (PEP) accepts ownership of an abandoned device. |
| [_PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure](..\wmiguid\ns-pep_x-_pep_acpi_enumerate_device_namespace.md) | The PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure contains an enumeration of the objects in the namespace of the device. |
| [_PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure](..\wmiguid\ns-pepfx-_pep_acpi_enumerate_device_namespace.md) | The PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure contains an enumeration of the objects in the namespace of the device. |
| [_PEP_ACPI_EVALUATE_CONTROL_METHOD structure](..\wmiguid\ns-pep_x-_pep_acpi_evaluate_control_method.md) | The PEP_ACPI_EVALUATE_CONTROL_METHOD structure specifies an ACPI control method to evaluate, an input argument to supply to this method, and an output buffer for the result of the evaluation. |
| [_PEP_ACPI_EVALUATE_CONTROL_METHOD structure](..\wmiguid\ns-pepfx-_pep_acpi_evaluate_control_method.md) | The PEP_ACPI_EVALUATE_CONTROL_METHOD structure specifies an ACPI control method to evaluate, an input argument to supply to this method, and an output buffer for the result of the evaluation. |
| [_PEP_ACPI_EXTENDED_ADDRESS structure](..\wmiguid\ns-pep_x-_pep_acpi_extended_address.md) | The PEP_ACPI_EXTENDED_ADDRESS structure is used to report resource usage in the address space such as memory and IO. |
| [_PEP_ACPI_EXTENDED_ADDRESS structure](..\wmiguid\ns-pepfx-_pep_acpi_extended_address.md) | The PEP_ACPI_EXTENDED_ADDRESS structure is used to report resource usage in the address space such as memory and IO. |
| [_PEP_ACPI_GPIO_RESOURCE structure](..\wmiguid\ns-pep_x-_pep_acpi_gpio_resource.md) | The PEP_ACPI_GPIO_RESOURCE structure describes the ACPI configuration for a general purpose input/output (GPIO) resource. |
| [_PEP_ACPI_GPIO_RESOURCE structure](..\wmiguid\ns-pepfx-_pep_acpi_gpio_resource.md) | The PEP_ACPI_GPIO_RESOURCE structure describes the ACPI configuration for a general purpose input/output (GPIO) resource. |
| [_PEP_ACPI_INTERRUPT_RESOURCE structure](..\wmiguid\ns-pep_x-_pep_acpi_interrupt_resource.md) | The PEP_ACPI_INTERRUPT_RESOURCE structure describes an ACPI interrupt resource. |
| [_PEP_ACPI_INTERRUPT_RESOURCE structure](..\wmiguid\ns-pepfx-_pep_acpi_interrupt_resource.md) | The PEP_ACPI_INTERRUPT_RESOURCE structure describes an ACPI interrupt resource. |
| [_PEP_ACPI_IO_MEMORY_RESOURCE structure](..\wmiguid\ns-pep_x-_pep_acpi_io_memory_resource.md) | The PEP_ACPI_IO_MEMORY_RESOURCE structure describes an ACPI IO port descriptor resource. |
| [_PEP_ACPI_IO_MEMORY_RESOURCE structure](..\wmiguid\ns-pepfx-_pep_acpi_io_memory_resource.md) | The PEP_ACPI_IO_MEMORY_RESOURCE structure describes an ACPI IO port descriptor resource. |
| [_PEP_ACPI_OBJECT_NAME structure](..\wmiguid\ns-pep_x-_pep_acpi_object_name.md) | The PEP_ACPI_OBJECT_NAME union contains the four-character name of an ACPI object. |
| [_PEP_ACPI_OBJECT_NAME structure](..\wmiguid\ns-pepfx-_pep_acpi_object_name.md) | The PEP_ACPI_OBJECT_NAME union contains the four-character name of an ACPI object. |
| [_PEP_ACPI_OBJECT_NAME_WITH_TYPE structure](..\wmiguid\ns-pep_x-_pep_acpi_object_name_with_type.md) | The PEP_ACPI_OBJECT_NAME_WITH_TYPE structure that specifies both the path-relative name of an ACPI object and the type of this object. |
| [_PEP_ACPI_OBJECT_NAME_WITH_TYPE structure](..\wmiguid\ns-pepfx-_pep_acpi_object_name_with_type.md) | The PEP_ACPI_OBJECT_NAME_WITH_TYPE structure that specifies both the path-relative name of an ACPI object and the type of this object. |
| [_PEP_ACPI_PREPARE_DEVICE structure](..\wmiguid\ns-pep_x-_pep_acpi_prepare_device.md) | The PEP_ACPI_PREPARE_DEVICE structure indicates whether a platform extension plug-in (PEP) is prepared to provide ACPI services for the specified device. |
| [_PEP_ACPI_PREPARE_DEVICE structure](..\wmiguid\ns-pepfx-_pep_acpi_prepare_device.md) | The PEP_ACPI_PREPARE_DEVICE structure indicates whether a platform extension plug-in (PEP) is prepared to provide ACPI services for the specified device. |
| [_PEP_ACPI_QUERY_DEVICE_CONTROL_RESOURCES structure](..\wmiguid\ns-pep_x-_pep_acpi_query_device_control_resources.md) | The PEP_ACPI_QUERY_DEVICE_CONTROL_RESOURCES structure contains a list of raw resources that are needed to control power to the device. |
| [_PEP_ACPI_QUERY_DEVICE_CONTROL_RESOURCES structure](..\wmiguid\ns-pepfx-_pep_acpi_query_device_control_resources.md) | The PEP_ACPI_QUERY_DEVICE_CONTROL_RESOURCES structure contains a list of raw resources that are needed to control power to the device. |
| [_PEP_ACPI_QUERY_OBJECT_INFORMATION structure](..\wmiguid\ns-pep_x-_pep_acpi_query_object_information.md) | The PEP_ACPI_QUERY_OBJECT_INFORMATION structure contains information about an ACPI object. |
| [_PEP_ACPI_QUERY_OBJECT_INFORMATION structure](..\wmiguid\ns-pepfx-_pep_acpi_query_object_information.md) | The PEP_ACPI_QUERY_OBJECT_INFORMATION structure contains information about an ACPI object. |
| [_PEP_ACPI_REGISTER_DEVICE structure](..\wmiguid\ns-pep_x-_pep_acpi_register_device.md) | The PEP_ACPI_REGISTER_DEVICE structure contains registration information about a device for which the platform extension plug-in (PEP) is to provide ACPI services. |
| [_PEP_ACPI_REGISTER_DEVICE structure](..\wmiguid\ns-pepfx-_pep_acpi_register_device.md) | The PEP_ACPI_REGISTER_DEVICE structure contains registration information about a device for which the platform extension plug-in (PEP) is to provide ACPI services. |
| [_PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure](..\wmiguid\ns-pep_x-_pep_acpi_request_convert_to_bios_resources.md) | The PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure is used in the process of converting ACPI resources to BIOS resources by one of the PEP initialization functions. |
| [_PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure](..\wmiguid\ns-pepfx-_pep_acpi_request_convert_to_bios_resources.md) | The PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure is used in the process of converting ACPI resources to BIOS resources by one of the PEP initialization functions. |
| [_PEP_ACPI_RESOURCE structure](..\wmiguid\ns-pep_x-_pep_acpi_resource.md) | The PEP_ACPI_RESOURCE structure contains hardware details for a specific ACPI resource. |
| [_PEP_ACPI_RESOURCE structure](..\wmiguid\ns-pepfx-_pep_acpi_resource.md) | The PEP_ACPI_RESOURCE structure contains hardware details for a specific ACPI resource. |
| [_PEP_ACPI_RESOURCE_FLAGS structure](..\wmiguid\ns-pep_x-_pep_acpi_resource_flags.md) | The PEP_ACPI_RESOURCE_FLAGS structure contains flags describing an ACPI resource. |
| [_PEP_ACPI_RESOURCE_FLAGS structure](..\wmiguid\ns-pepfx-_pep_acpi_resource_flags.md) | The PEP_ACPI_RESOURCE_FLAGS structure contains flags describing an ACPI resource. |
| [_PEP_ACPI_SPB_I2C_RESOURCE structure](..\wmiguid\ns-pep_x-_pep_acpi_spb_i2c_resource.md) | The PEP_ACPI_SPB_I2C_RESOURCE structure describes an ACPI I2C serial bus resource. |
| [_PEP_ACPI_SPB_I2C_RESOURCE structure](..\wmiguid\ns-pepfx-_pep_acpi_spb_i2c_resource.md) | The PEP_ACPI_SPB_I2C_RESOURCE structure describes an ACPI I2C serial bus resource. |
| [_PEP_ACPI_SPB_RESOURCE structure](..\wmiguid\ns-pep_x-_pep_acpi_spb_resource.md) | The PEP_ACPI_SPB_RESOURCE structure describes an ACPI serial bus connection resource. |
| [_PEP_ACPI_SPB_RESOURCE structure](..\wmiguid\ns-pepfx-_pep_acpi_spb_resource.md) | The PEP_ACPI_SPB_RESOURCE structure describes an ACPI serial bus connection resource. |
| [_PEP_ACPI_SPB_SPI_RESOURCE structure](..\wmiguid\ns-pep_x-_pep_acpi_spb_spi_resource.md) | The PEP_ACPI_SPB_SPI_RESOURCE structure describes an ACPI SPI serial bus resource. |
| [_PEP_ACPI_SPB_SPI_RESOURCE structure](..\wmiguid\ns-pepfx-_pep_acpi_spb_spi_resource.md) | The PEP_ACPI_SPB_SPI_RESOURCE structure describes an ACPI SPI serial bus resource. |
| [_PEP_ACPI_SPB_UART_RESOURCE structure](..\wmiguid\ns-pep_x-_pep_acpi_spb_uart_resource.md) | The PEP_ACPI_SPB_UART_RESOURCE structure describes an ACPI UART serial bus resource. |
| [_PEP_ACPI_SPB_UART_RESOURCE structure](..\wmiguid\ns-pepfx-_pep_acpi_spb_uart_resource.md) | The PEP_ACPI_SPB_UART_RESOURCE structure describes an ACPI UART serial bus resource. |
| [_PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure](..\wmiguid\ns-pep_x-_pep_acpi_translated_device_control_resources.md) | The PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure contains a list of translated power-control resources for the platform extension plug-in (PEP) to use. |
| [_PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure](..\wmiguid\ns-pepfx-_pep_acpi_translated_device_control_resources.md) | The PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure contains a list of translated power-control resources for the platform extension plug-in (PEP) to use. |
| [_PEP_ACPI_UNREGISTER_DEVICE structure](..\wmiguid\ns-pep_x-_pep_acpi_unregister_device.md) | The PEP_ACPI_UNREGISTER_DEVICE structure contains information about a device that has been unregistered from ACPI services. |
| [_PEP_ACPI_UNREGISTER_DEVICE structure](..\wmiguid\ns-pepfx-_pep_acpi_unregister_device.md) | The PEP_ACPI_UNREGISTER_DEVICE structure contains information about a device that has been unregistered from ACPI services. |
| [_PEP_COMPONENT_ACTIVE structure](..\wmiguid\ns-pep_x-_pep_component_active.md) | The PEP_COMPONENT_ACTIVE structure identifies a component that is making a transition between the idle condition and the active condition. |
| [_PEP_COMPONENT_PERF_INFO structure](..\wmiguid\ns-pep_x-_pep_component_perf_info.md) | The PEP_COMPONENT_PERF_INFO structure describes the performance states (P-states) of a component. |
| [_PEP_COMPONENT_PERF_INFO structure](..\wmiguid\ns-pepfx-_pep_component_perf_info.md) | The PEP_COMPONENT_PERF_INFO structure describes the performance states (P-states) of a component. |
| [_PEP_COMPONENT_PERF_SET structure](..\wmiguid\ns-pep_x-_pep_component_perf_set.md) | The PEP_COMPONENT_PERF_SET structure describes the performance states (P-states) in a P-state set. |
| [_PEP_COMPONENT_PERF_SET structure](..\wmiguid\ns-pepfx-_pep_component_perf_set.md) | The PEP_COMPONENT_PERF_SET structure describes the performance states (P-states) in a P-state set. |
| [_PEP_COMPONENT_PERF_STATE_REQUEST structure](..\wmiguid\ns-pep_x-_pep_component_perf_state_request.md) | The PEP_COMPONENT_PERF_STATE_REQUEST structure specifies a performance state (P-state) set and a new performance level to assign to this set. |
| [_PEP_COMPONENT_PERF_STATE_REQUEST structure](..\wmiguid\ns-pepfx-_pep_component_perf_state_request.md) | The PEP_COMPONENT_PERF_STATE_REQUEST structure specifies a performance state (P-state) set and a new performance level to assign to this set. |
| [_PEP_COMPONENT_PLATFORM_CONSTRAINTS structure](..\wmiguid\ns-pep_x-_pep_component_platform_constraints.md) | The PEP_COMPONENT_PLATFORM_CONSTRAINTS structure describes the lowest-powered Fx state of that a component can be in when the platform is in a particular idle state. |
| [_PEP_COMPONENT_PLATFORM_CONSTRAINTS structure](..\wmiguid\ns-pepfx-_pep_component_platform_constraints.md) | The PEP_COMPONENT_PLATFORM_CONSTRAINTS structure describes the lowest-powered Fx state of that a component can be in when the platform is in a particular idle state. |
| [_PEP_COMPONENT_V2 structure](..\wmiguid\ns-pep_x-_pep_component_v2.md) | The PEP_COMPONENT_V2 structure specifies the power state attributes of a component in the device. |
| [_PEP_COMPONENT_V2 structure](..\wmiguid\ns-pepfx-_pep_component_v2.md) | The PEP_COMPONENT_V2 structure specifies the power state attributes of a component in the device. |
| [_PEP_COORDINATED_DEPENDENCY_OPTION structure](..\wmiguid\ns-pep_x-_pep_coordinated_dependency_option.md) | The PEP_COORIDNATED_DEPENDENCY_OPTION structure describes a coordinated idle stateâ€™s dependency to the OS. |
| [_PEP_COORDINATED_DEPENDENCY_OPTION structure](..\wmiguid\ns-pepfx-_pep_coordinated_dependency_option.md) | The PEP_COORIDNATED_DEPENDENCY_OPTION structure describes a coordinated idle stateâ€™s dependency to the OS. |
| [_PEP_COORDINATED_IDLE_STATE structure](..\wmiguid\ns-pep_x-_pep_coordinated_idle_state.md) | The PEP_COORIDNATED_IDLE_STATE structure describes a coordinated idle state to the OS. |
| [_PEP_COORDINATED_IDLE_STATE structure](..\wmiguid\ns-pepfx-_pep_coordinated_idle_state.md) | The PEP_COORIDNATED_IDLE_STATE structure describes a coordinated idle state to the OS. |
| [_PEP_CRASHDUMP_INFORMATION structure](..\wmiguid\ns-pep_x-_pep_crashdump_information.md) | The PEP_CRASHDUMP_INFORMATION structure contains information about a crash-dump device. |
| [_PEP_CRASHDUMP_INFORMATION structure](..\wmiguid\ns-pepfx-_pep_crashdump_information.md) | The PEP_CRASHDUMP_INFORMATION structure contains information about a crash-dump device. |
| [_PEP_DEBUGGER_TRANSITION_REQUIREMENTS structure](..\wmiguid\ns-pep_x-_pep_debugger_transition_requirements.md) | The PEP_DEBUGGER_TRANSITION_REQUIREMENTS structure indicates the platform idle states for which the debugger device must be turned on. |
| [_PEP_DEBUGGER_TRANSITION_REQUIREMENTS structure](..\wmiguid\ns-pepfx-_pep_debugger_transition_requirements.md) | The PEP_DEBUGGER_TRANSITION_REQUIREMENTS structure indicates the platform idle states for which the debugger device must be turned on. |
| [_PEP_DEVICE_PLATFORM_CONSTRAINTS structure](..\wmiguid\ns-pep_x-_pep_device_platform_constraints.md) | The PEP_DEVICE_PLATFORM_CONSTRAINTS structure specifies the constraints for entry to the various Dx power states that are supported by a device. |
| [_PEP_DEVICE_PLATFORM_CONSTRAINTS structure](..\wmiguid\ns-pepfx-_pep_device_platform_constraints.md) | The PEP_DEVICE_PLATFORM_CONSTRAINTS structure specifies the constraints for entry to the various Dx power states that are supported by a device. |
| [_PEP_DEVICE_POWER_STATE structure](..\wmiguid\ns-pep_x-_pep_device_power_state.md) | The PEP_DEVICE_POWER_STATE structure indicates the status of a transition to a new Dx (device power) state. |
| [_PEP_DEVICE_POWER_STATE structure](..\wmiguid\ns-pepfx-_pep_device_power_state.md) | The PEP_DEVICE_POWER_STATE structure indicates the status of a transition to a new Dx (device power) state. |
| [_PEP_DEVICE_REGISTER_V2 structure](..\wmiguid\ns-pep_x-_pep_device_register_v2.md) | The PEP_DEVICE_REGISTER structure describes all the components in a particular device. |
| [_PEP_DEVICE_REGISTER_V2 structure](..\wmiguid\ns-pepfx-_pep_device_register_v2.md) | The PEP_DEVICE_REGISTER structure describes all the components in a particular device. |
| [_PEP_DEVICE_STARTED structure](..\wmiguid\ns-pep_x-_pep_device_started.md) | The PEP_DEVICE_STARTED structure identifies a device whose driver has completed its registration with the Windows power management framework (PoFx). |
| [_PEP_DEVICE_STARTED structure](..\wmiguid\ns-pepfx-_pep_device_started.md) | The PEP_DEVICE_STARTED structure identifies a device whose driver has completed its registration with the Windows power management framework (PoFx). |
| [_PEP_INFORMATION structure](..\wmiguid\ns-pep_x-_pep_information.md) | The PEP_INFORMATION structure specifies the interface that the platform extension plug-in (PEP) uses to receive notifications from the Windows power management framework (PoFx). |
| [_PEP_INFORMATION structure](..\wmiguid\ns-pepfx-_pep_information.md) | The PEP_INFORMATION structure specifies the interface that the platform extension plug-in (PEP) uses to receive notifications from the Windows power management framework (PoFx). |
| [_PEP_KERNEL_INFORMATION_STRUCT_V1 structure](..\wmiguid\ns-pep_x-_pep_kernel_information_struct_v1.md) | The PEP_KERNEL_INFORMATION structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows power management framework (PoFx). |
| [_PEP_KERNEL_INFORMATION_STRUCT_V2 structure](..\wmiguid\ns-pep_x-_pep_kernel_information_struct_v2.md) | The PEP_KERNEL_INFORMATION structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows power management framework (PoFx). |
| [_PEP_KERNEL_INFORMATION_STRUCT_V3 structure](..\wmiguid\ns-pep_x-_pep_kernel_information_struct_v3.md) | The PEP_KERNEL_INFORMATION_STRUCT_V3 structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows power management framework (PoFx). |
| [_PEP_KERNEL_INFORMATION_STRUCT_V3 structure](..\wmiguid\ns-pepfx-_pep_kernel_information_struct_v3.md) | The PEP_KERNEL_INFORMATION_STRUCT_V3 structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows power management framework (PoFx). |
| [_PEP_LOW_POWER_EPOCH structure](..\wmiguid\ns-pep_x-_pep_low_power_epoch.md) | The PEP_LOW_POWER_EPOCH structure is used to provide data for a PEP_DPM_LOW_POWER_EPOCH notification (deprecated). |
| [_PEP_LOW_POWER_EPOCH structure](..\wmiguid\ns-pepfx-_pep_low_power_epoch.md) | The PEP_LOW_POWER_EPOCH structure is used to provide data for a PEP_DPM_LOW_POWER_EPOCH notification (deprecated). |
| [_PEP_NOTIFY_COMPONENT_IDLE_STATE structure](..\wmiguid\ns-pep_x-_pep_notify_component_idle_state.md) | The PEP_NOTIFY_COMPONENT_IDLE_STATE structure contains status information about a component's pending transition to a new Fx power state. |
| [_PEP_NOTIFY_COMPONENT_IDLE_STATE structure](..\wmiguid\ns-pepfx-_pep_notify_component_idle_state.md) | The PEP_NOTIFY_COMPONENT_IDLE_STATE structure contains status information about a component's pending transition to a new Fx power state. |
| [_PEP_PERF_STATE structure](..\wmiguid\ns-pep_x-_pep_perf_state.md) | The PEP_PERF_STATE structure describes a performance state (P-state) in a P-state set in which the P-states are specified as a list of one or more discrete values. |
| [_PEP_PERF_STATE structure](..\wmiguid\ns-pepfx-_pep_perf_state.md) | The PEP_PERF_STATE structure describes a performance state (P-state) in a P-state set in which the P-states are specified as a list of one or more discrete values. |
| [_PEP_PLATFORM_IDLE_STATE structure](..\wmiguid\ns-pep_x-_pep_platform_idle_state.md) | The PEP_PLATFORM_IDLE_STATE structure specifies the properties of a platform idle state. |
| [_PEP_PLATFORM_IDLE_STATE structure](..\wmiguid\ns-pepfx-_pep_platform_idle_state.md) | The PEP_PLATFORM_IDLE_STATE structure specifies the properties of a platform idle state. |
| [_PEP_PLATFORM_IDLE_STATE_UPDATE structure](..\wmiguid\ns-pep_x-_pep_platform_idle_state_update.md) | The PEP_PLATFORM_IDLE_STATE_UPDATE structure contains the updated properties of a platform idle state. |
| [_PEP_PLATFORM_IDLE_STATE_UPDATE structure](..\wmiguid\ns-pepfx-_pep_platform_idle_state_update.md) | The PEP_PLATFORM_IDLE_STATE_UPDATE structure contains the updated properties of a platform idle state. |
| [_PEP_POWER_CONTROL_COMPLETE structure](..\wmiguid\ns-pep_x-_pep_power_control_complete.md) | The PEP_POWER_CONTROL_COMPLETE structure contains status information for a power control operation that the PEP previously requested and that the device driver has completed. |
| [_PEP_POWER_CONTROL_COMPLETE structure](..\wmiguid\ns-pepfx-_pep_power_control_complete.md) | The PEP_POWER_CONTROL_COMPLETE structure contains status information for a power control operation that the PEP previously requested and that the device driver has completed. |
| [_PEP_POWER_CONTROL_REQUEST structure](..\wmiguid\ns-pep_x-_pep_power_control_request.md) | The PEP_POWER_CONTROL_REQUEST structure contains a request from a driver for a power control operation. |
| [_PEP_POWER_CONTROL_REQUEST structure](..\wmiguid\ns-pepfx-_pep_power_control_request.md) | The PEP_POWER_CONTROL_REQUEST structure contains a request from a driver for a power control operation. |
| [_PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure](..\wmiguid\ns-pep_x-_pep_ppm_context_query_parking_page.md) | The PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure describes the parking page for a processor. |
| [_PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure](..\wmiguid\ns-pepfx-_pep_ppm_context_query_parking_page.md) | The PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure describes the parking page for a processor. |
| [_PEP_PPM_CST_STATE structure](..\wmiguid\ns-pep_x-_pep_ppm_cst_state.md) | The PEP_PPM_CST_STATE structure specifies the properties of a C state (ACPI processor power state). |
| [_PEP_PPM_CST_STATE structure](..\wmiguid\ns-pepfx-_pep_ppm_cst_state.md) | The PEP_PPM_CST_STATE structure specifies the properties of a C state (ACPI processor power state). |
| [_PEP_PPM_CST_STATES structure](..\wmiguid\ns-pep_x-_pep_ppm_cst_states.md) | The PEP_PPM_CST_STATES structure specifies the properties of the C states (ACPI processor power states) that are supported for a processor. |
| [_PEP_PPM_CST_STATES structure](..\wmiguid\ns-pepfx-_pep_ppm_cst_states.md) | The PEP_PPM_CST_STATES structure specifies the properties of the C states (ACPI processor power states) that are supported for a processor. |
| [_PEP_PPM_ENTER_SYSTEM_STATE structure](..\wmiguid\ns-pep_x-_pep_ppm_enter_system_state.md) | Used in the PEP_NOTIFY_PPM_ENTER_SYSTEM_STATE notification to notify PEP that the system is about to enter a system power state.  . |
| [_PEP_PPM_ENTER_SYSTEM_STATE structure](..\wmiguid\ns-pepfx-_pep_ppm_enter_system_state.md) | Used in the PEP_NOTIFY_PPM_ENTER_SYSTEM_STATE notification to notify PEP that the system is about to enter a system power state.  . |
| [_PEP_PPM_FEEDBACK_READ structure](..\wmiguid\ns-pep_x-_pep_ppm_feedback_read.md) | The PEP_PPM_FEEDBACK_READ structure contains the value read from a processor performance feedback counter. |
| [_PEP_PPM_FEEDBACK_READ structure](..\wmiguid\ns-pepfx-_pep_ppm_feedback_read.md) | The PEP_PPM_FEEDBACK_READ structure contains the value read from a processor performance feedback counter. |
| [_PEP_PPM_IDLE_CANCEL structure](..\wmiguid\ns-pep_x-_pep_ppm_idle_cancel.md) | The PEP_PPM_IDLE_CANCEL structure indicates why the processor could not enter the previously selected idle state. |
| [_PEP_PPM_IDLE_COMPLETE structure](..\wmiguid\ns-pep_x-_pep_ppm_idle_complete.md) | The PEP_PPM_IDLE_COMPLETE structure describe the idle states from which the processor and hardware platform are waking. |
| [_PEP_PPM_IDLE_COMPLETE structure](..\wmiguid\ns-pepfx-_pep_ppm_idle_complete.md) | The PEP_PPM_IDLE_COMPLETE structure describe the idle states from which the processor and hardware platform are waking. |
| [_PEP_PPM_IDLE_COMPLETE_V2 structure](..\wmiguid\ns-pep_x-_pep_ppm_idle_complete_v2.md) | The PEP_PPM_IDLE_COMPLETE_V2 structure describe the idle states from which the processor and hardware platform are waking. |
| [_PEP_PPM_IDLE_COMPLETE_V2 structure](..\wmiguid\ns-pepfx-_pep_ppm_idle_complete_v2.md) | The PEP_PPM_IDLE_COMPLETE_V2 structure describe the idle states from which the processor and hardware platform are waking. |
| [_PEP_PPM_IDLE_EXECUTE structure](..\wmiguid\ns-pep_x-_pep_ppm_idle_execute.md) | The PEP_PPM_IDLE_EXECUTE structure specifies the idle state that the processor is to enter. |
| [_PEP_PPM_IDLE_EXECUTE structure](..\wmiguid\ns-pepfx-_pep_ppm_idle_execute.md) | The PEP_PPM_IDLE_EXECUTE structure specifies the idle state that the processor is to enter. |
| [_PEP_PPM_IDLE_EXECUTE_V2 structure](..\wmiguid\ns-pep_x-_pep_ppm_idle_execute_v2.md) | The PEP_PPM_IDLE_EXECUTE_V2 structure specifies the idle state that the processor is to enter. |
| [_PEP_PPM_IDLE_EXECUTE_V2 structure](..\wmiguid\ns-pepfx-_pep_ppm_idle_execute_v2.md) | The PEP_PPM_IDLE_EXECUTE_V2 structure specifies the idle state that the processor is to enter. |
| [_PEP_PPM_IDLE_SELECT structure](..\wmiguid\ns-pep_x-_pep_ppm_idle_select.md) | The PEP_PPM_IDLE_SELECT structure describes the most energy-efficient idle state that the processor can enter and still satisfy the constraints specified by the operating system. |
| [_PEP_PPM_INITIATE_WAKE structure](..\wmiguid\ns-pep_x-_pep_ppm_initiate_wake.md) | The PEP_PPM_INITIATE_WAKE structure indicates whether a processor requires an interrupt to wake up from an idle state. |
| [_PEP_PPM_INITIATE_WAKE structure](..\wmiguid\ns-pepfx-_pep_ppm_initiate_wake.md) | The PEP_PPM_INITIATE_WAKE structure indicates whether a processor requires an interrupt to wake up from an idle state. |
| [_PEP_PPM_IS_PROCESSOR_HALTED structure](..\wmiguid\ns-pep_x-_pep_ppm_is_processor_halted.md) | The PEP_PPM_IS_PROCESSOR_HALTED structure indicates whether the processor is currently halted in its selected idle state. |
| [_PEP_PPM_IS_PROCESSOR_HALTED structure](..\wmiguid\ns-pepfx-_pep_ppm_is_processor_halted.md) | The PEP_PPM_IS_PROCESSOR_HALTED structure indicates whether the processor is currently halted in its selected idle state. |
| [_PEP_PPM_LPI_COMPLETE structure](..\wmiguid\ns-pep_x-_pep_ppm_lpi_complete.md) | The PEP_PPM_QUERY_FEEDBACK_COUNTERS structure describes all the processor performance counters that the platform extension plug-in (PEP) supports for a particular processor. |
| [_PEP_PPM_PARK_MASK structure](..\wmiguid\ns-pep_x-_pep_ppm_park_mask.md) | The PEP_PROCESSOR_PARK_MASK structure contains the current core parking mask. |
| [_PEP_PPM_PARK_MASK structure](..\wmiguid\ns-pepfx-_pep_ppm_park_mask.md) | The PEP_PROCESSOR_PARK_MASK structure contains the current core parking mask. |
| [_PEP_PPM_PARK_SELECTION structure](..\wmiguid\ns-pep_x-_pep_ppm_park_selection.md) | The PEP_PPM_PARK_SELECTION structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding which processors in the platform should be parked to reduce power consumption. |
| [_PEP_PPM_PARK_SELECTION structure](..\wmiguid\ns-pepfx-_pep_ppm_park_selection.md) | The PEP_PPM_PARK_SELECTION structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding which processors in the platform should be parked to reduce power consumption. |
| [_PEP_PPM_PARK_SELECTION_V2 structure](..\wmiguid\ns-pep_x-_pep_ppm_park_selection_v2.md) | The PEP_PPM_PARK_SELECTION_V2 structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding which processors in the platform should be parked to reduce power consumption. |
| [_PEP_PPM_PARK_SELECTION_V2 structure](..\wmiguid\ns-pepfx-_pep_ppm_park_selection_v2.md) | The PEP_PPM_PARK_SELECTION_V2 structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding which processors in the platform should be parked to reduce power consumption. |
| [_PEP_PPM_PERF_CHECK_COMPLETE structure](..\wmiguid\ns-pep_x-_pep_ppm_perf_check_complete.md) | The PEP_PPM_PERF_CHECK_COMPLETE structure is used to inform the PEP of details regarding the completion of a periodic performance check evaluation. |
| [_PEP_PPM_PERF_CHECK_COMPLETE structure](..\wmiguid\ns-pepfx-_pep_ppm_perf_check_complete.md) | The PEP_PPM_PERF_CHECK_COMPLETE structure is used to inform the PEP of details regarding the completion of a periodic performance check evaluation. |
| [_PEP_PPM_PERF_SET structure](..\wmiguid\ns-pep_x-_pep_ppm_perf_set.md) | The PEP_PPM_PERF_SET structure specifies the new performance level that the operating system is requesting for the processor. |
| [_PEP_PPM_PERF_SET structure](..\wmiguid\ns-pepfx-_pep_ppm_perf_set.md) | The PEP_PPM_PERF_SET structure specifies the new performance level that the operating system is requesting for the processor. |
| [_PEP_PPM_PERF_SET_STATE structure](..\wmiguid\ns-pep_x-_pep_ppm_perf_set_state.md) | Used in the PEP_NOTIFY_PPM_PERF_SET notification at runtime to set the current operating performance of the processor.  . |
| [_PEP_PPM_PERF_SET_STATE structure](..\wmiguid\ns-pepfx-_pep_ppm_perf_set_state.md) | Used in the PEP_NOTIFY_PPM_PERF_SET notification at runtime to set the current operating performance of the processor.  . |
| [_PEP_PPM_PLATFORM_STATE_RESIDENCIES structure](..\wmiguid\ns-pep_x-_pep_ppm_platform_state_residencies.md) | The PEP_PPM_PLATFORM_STATE_RESIDENCIES structure contains the accumulated residency times and transition counts for the idle states that are supported by the hardware platform. |
| [_PEP_PPM_PLATFORM_STATE_RESIDENCIES structure](..\wmiguid\ns-pepfx-_pep_ppm_platform_state_residencies.md) | The PEP_PPM_PLATFORM_STATE_RESIDENCIES structure contains the accumulated residency times and transition counts for the idle states that are supported by the hardware platform. |
| [_PEP_PPM_PLATFORM_STATE_RESIDENCY structure](..\wmiguid\ns-pep_x-_pep_ppm_platform_state_residency.md) | The PEP_PPM_PLATFORM_STATE_RESIDENCY structure specifies the accumulated residency time and transition count for a particular platform idle state. |
| [_PEP_PPM_PLATFORM_STATE_RESIDENCY structure](..\wmiguid\ns-pepfx-_pep_ppm_platform_state_residency.md) | The PEP_PPM_PLATFORM_STATE_RESIDENCY structure specifies the accumulated residency time and transition count for a particular platform idle state. |
| [_PEP_PPM_QUERY_CAPABILITIES structure](..\wmiguid\ns-pep_x-_pep_ppm_query_capabilities.md) | The PEP_PPM_QUERY_CAPABILITIES structure contains information about the processor power management (PPM) capabilities of the platform extension plug-in (PEP). |
| [_PEP_PPM_QUERY_CAPABILITIES structure](..\wmiguid\ns-pepfx-_pep_ppm_query_capabilities.md) | The PEP_PPM_QUERY_CAPABILITIES structure contains information about the processor power management (PPM) capabilities of the platform extension plug-in (PEP). |
| [_PEP_PPM_QUERY_COORDINATED_DEPENDENCY structure](..\wmiguid\ns-pep_x-_pep_ppm_query_coordinated_dependency.md) | The PEP_PPM_QUERY_COORDINATED_DEPENDENCY structure describes dependencies for coordinated idle states. |
| [_PEP_PPM_QUERY_COORDINATED_DEPENDENCY structure](..\wmiguid\ns-pepfx-_pep_ppm_query_coordinated_dependency.md) | The PEP_PPM_QUERY_COORDINATED_DEPENDENCY structure describes dependencies for coordinated idle states. |
| [_PEP_PPM_QUERY_COORDINATED_STATES structure](..\wmiguid\ns-pep_x-_pep_ppm_query_coordinated_states.md) | The PEP_PPM_QUERY_COORDINATED_STATES structure contains information about each coordinated idle state that the platform extension plug-in (PEP) supports. |
| [_PEP_PPM_QUERY_COORDINATED_STATES structure](..\wmiguid\ns-pepfx-_pep_ppm_query_coordinated_states.md) | The PEP_PPM_QUERY_COORDINATED_STATES structure contains information about each coordinated idle state that the platform extension plug-in (PEP) supports. |
| [_PEP_PPM_QUERY_DISCRETE_PERF_STATES structure](..\wmiguid\ns-pep_x-_pep_ppm_query_discrete_perf_states.md) | Used in the PEP_NOTIFY_PPM_QUERY_DISCRETE_PERF_STATES notification that stores the list of discrete performance states that PEP supports, if the PEP_NOTIFY_PPM_QUERY_CAPABILITIES notification indicates support for discrete performance states. . |
| [_PEP_PPM_QUERY_DISCRETE_PERF_STATES structure](..\wmiguid\ns-pepfx-_pep_ppm_query_discrete_perf_states.md) | Used in the PEP_NOTIFY_PPM_QUERY_DISCRETE_PERF_STATES notification that stores the list of discrete performance states that PEP supports, if the PEP_NOTIFY_PPM_QUERY_CAPABILITIES notification indicates support for discrete performance states. . |
| [_PEP_PPM_QUERY_DOMAIN_INFO structure](..\wmiguid\ns-pep_x-_pep_ppm_query_domain_info.md) | Used in the PEP_NOTIFY_PPM_QUERY_DOMAIN_INFO notification that queries for information about a performance domain. . |
| [_PEP_PPM_QUERY_DOMAIN_INFO structure](..\wmiguid\ns-pepfx-_pep_ppm_query_domain_info.md) | Used in the PEP_NOTIFY_PPM_QUERY_DOMAIN_INFO notification that queries for information about a performance domain. . |
| [_PEP_PPM_QUERY_FEEDBACK_COUNTERS structure](..\wmiguid\ns-pep_x-_pep_ppm_query_feedback_counters.md) | The PEP_PPM_QUERY_FEEDBACK_COUNTERS structure describes all the processor performance counters that the platform extension plug-in (PEP) supports for a particular processor. |
| [_PEP_PPM_QUERY_FEEDBACK_COUNTERS structure](..\wmiguid\ns-pepfx-_pep_ppm_query_feedback_counters.md) | The PEP_PPM_QUERY_FEEDBACK_COUNTERS structure describes all the processor performance counters that the platform extension plug-in (PEP) supports for a particular processor. |
| [_PEP_PPM_QUERY_IDLE_STATES structure](..\wmiguid\ns-pep_x-_pep_ppm_query_idle_states.md) | The PEP_PPM_QUERY_IDLE_STATES structure describes the idle states of a particular processor. |
| [_PEP_PPM_QUERY_IDLE_STATES_V2 structure](..\wmiguid\ns-pep_x-_pep_ppm_query_idle_states_v2.md) | The PEP_PPM_QUERY_IDLE_STATES_V2 structure is used during processor initialization to query the platform extension plug-in (PEP) for a list of processor idle states that the processor supports. |
| [_PEP_PPM_QUERY_IDLE_STATES_V2 structure](..\wmiguid\ns-pepfx-_pep_ppm_query_idle_states_v2.md) | The PEP_PPM_QUERY_IDLE_STATES_V2 structure is used during processor initialization to query the platform extension plug-in (PEP) for a list of processor idle states that the processor supports. |
| [_PEP_PPM_QUERY_LP_SETTINGS structure](..\wmiguid\ns-pep_x-_pep_ppm_query_lp_settings.md) | The PEP_PPM_QUERY_LP_SETTINGS structure contains a kernel handle to the registry key that contains the power optimization settings that the platform extension plug-in (PEP) has defined for each power scenario. |
| [_PEP_PPM_QUERY_PERF_CAPABILITIES structure](..\wmiguid\ns-pep_x-_pep_ppm_query_perf_capabilities.md) | The PEP_PPM_QUERY_PERF_CAPABILITIES structure describes the performance capabilities of the processors in the specified processor performance domain. |
| [_PEP_PPM_QUERY_PERF_CAPABILITIES structure](..\wmiguid\ns-pepfx-_pep_ppm_query_perf_capabilities.md) | The PEP_PPM_QUERY_PERF_CAPABILITIES structure describes the performance capabilities of the processors in the specified processor performance domain. |
| [_PEP_PPM_QUERY_PERF_CONSTRAINTS structure](..\wmiguid\ns-pep_x-_pep_ppm_query_perf_constraints.md) | The PEP_PPM_PERF_CONSTRAINTS structure describes the performance limits to apply to the processor. |
| [_PEP_PPM_QUERY_PERF_CONSTRAINTS structure](..\wmiguid\ns-pepfx-_pep_ppm_query_perf_constraints.md) | The PEP_PPM_PERF_CONSTRAINTS structure describes the performance limits to apply to the processor. |
| [_PEP_PPM_QUERY_PLATFORM_STATE structure](..\wmiguid\ns-pep_x-_pep_ppm_query_platform_state.md) | The PEP_PPM_QUERY_PLATFORM_STATE structure contains information about a platform idle state. |
| [_PEP_PPM_QUERY_PLATFORM_STATE structure](..\wmiguid\ns-pepfx-_pep_ppm_query_platform_state.md) | The PEP_PPM_QUERY_PLATFORM_STATE structure contains information about a platform idle state. |
| [_PEP_PPM_QUERY_PLATFORM_STATES structure](..\wmiguid\ns-pep_x-_pep_ppm_query_platform_states.md) | The PEP_PPM_QUERY_PLATFORM_STATES structure specifies the number of platform idle states the hardware platform supports. |
| [_PEP_PPM_QUERY_PLATFORM_STATES structure](..\wmiguid\ns-pepfx-_pep_ppm_query_platform_states.md) | The PEP_PPM_QUERY_PLATFORM_STATES structure specifies the number of platform idle states the hardware platform supports. |
| [_PEP_PPM_QUERY_STATE_NAME structure](..\wmiguid\ns-pep_x-_pep_ppm_query_state_name.md) | The PEP_PPM_QUERY_STATE_NAME structure contains information about a specific coordinated or platform idle state. |
| [_PEP_PPM_QUERY_STATE_NAME structure](..\wmiguid\ns-pepfx-_pep_ppm_query_state_name.md) | The PEP_PPM_QUERY_STATE_NAME structure contains information about a specific coordinated or platform idle state. |
| [_PEP_PPM_QUERY_VETO_REASON structure](..\wmiguid\ns-pep_x-_pep_ppm_query_veto_reason.md) | The PEP_PPM_QUERY_VETO_REASON structure supplies a wide-character, null-terminated string that contains a descriptive, human-readable name for a veto reason. |
| [_PEP_PPM_QUERY_VETO_REASON structure](..\wmiguid\ns-pepfx-_pep_ppm_query_veto_reason.md) | The PEP_PPM_QUERY_VETO_REASON structure supplies a wide-character, null-terminated string that contains a descriptive, human-readable name for a veto reason. |
| [_PEP_PPM_QUERY_VETO_REASONS structure](..\wmiguid\ns-pep_x-_pep_ppm_query_veto_reasons.md) | The PEP_PPM_QUERY_VETO_REASONS structure specifies the total number of veto reasons that the PEP uses in calls to the ProcessorIdleVeto and PlatformIdleVeto routines. |
| [_PEP_PPM_QUERY_VETO_REASONS structure](..\wmiguid\ns-pepfx-_pep_ppm_query_veto_reasons.md) | The PEP_PPM_QUERY_VETO_REASONS structure specifies the total number of veto reasons that the PEP uses in calls to the ProcessorIdleVeto and PlatformIdleVeto routines. |
| [_PEP_PPM_RESUME_FROM_SYSTEM_STATE structure](..\wmiguid\ns-pep_x-_pep_ppm_resume_from_system_state.md) | Used by the PEP_NOTIFY_PPM_RESUME_FROM_SYSTEM_STATE notification that notifies the PEP that the system has just resumed from a system power state. |
| [_PEP_PPM_RESUME_FROM_SYSTEM_STATE structure](..\wmiguid\ns-pepfx-_pep_ppm_resume_from_system_state.md) | Used by the PEP_NOTIFY_PPM_RESUME_FROM_SYSTEM_STATE notification that notifies the PEP that the system has just resumed from a system power state. |
| [_PEP_PPM_TEST_IDLE_STATE structure](..\wmiguid\ns-pep_x-_pep_ppm_test_idle_state.md) | The PEP_PPM_TEST_IDLE_STATE structure contains information about whether the processor can immediately enter a processor idle state. |
| [_PEP_PPM_TEST_IDLE_STATE structure](..\wmiguid\ns-pepfx-_pep_ppm_test_idle_state.md) | The PEP_PPM_TEST_IDLE_STATE structure contains information about whether the processor can immediately enter a processor idle state. |
| [_PEP_PREPARE_DEVICE structure](..\wmiguid\ns-pep_x-_pep_prepare_device.md) | The PEP_PREPARE_DEVICE structure identifies a device that must be started up in preparation for its use by the operating system. |
| [_PEP_PREPARE_DEVICE structure](..\wmiguid\ns-pepfx-_pep_prepare_device.md) | The PEP_PREPARE_DEVICE structure identifies a device that must be started up in preparation for its use by the operating system. |
| [_PEP_PROCESSOR_FEEDBACK_COUNTER structure](..\wmiguid\ns-pep_x-_pep_processor_feedback_counter.md) | The PEP_PROCESSOR_FEEDBACK_COUNTER structure describes a feedback counter to the operating system. |
| [_PEP_PROCESSOR_FEEDBACK_COUNTER structure](..\wmiguid\ns-pepfx-_pep_processor_feedback_counter.md) | The PEP_PROCESSOR_FEEDBACK_COUNTER structure describes a feedback counter to the operating system. |
| [_PEP_PROCESSOR_IDLE_CONSTRAINTS structure](..\wmiguid\ns-pep_x-_pep_processor_idle_constraints.md) | The PEP_PROCESSOR_IDLE_CONSTRAINTS structure specifies a set of constraints that the PEP uses to select a processor idle state. |
| [_PEP_PROCESSOR_IDLE_DEPENDENCY structure](..\wmiguid\ns-pep_x-_pep_processor_idle_dependency.md) | The PEP_PROCESSOR_IDLE_DEPENDENCY structure specifies the dependencies of a platform idle state on the specified processor. |
| [_PEP_PROCESSOR_IDLE_DEPENDENCY structure](..\wmiguid\ns-pepfx-_pep_processor_idle_dependency.md) | The PEP_PROCESSOR_IDLE_DEPENDENCY structure specifies the dependencies of a platform idle state on the specified processor. |
| [_PEP_PROCESSOR_IDLE_STATE structure](..\wmiguid\ns-pep_x-_pep_processor_idle_state.md) | The PEP_PROCESSOR_IDLE_STATE structure describes the capabilities of a processor idle state. |
| [_PEP_PROCESSOR_IDLE_STATE_UPDATE structure](..\wmiguid\ns-pep_x-_pep_processor_idle_state_update.md) | The PEP_PROCESSOR_IDLE_STATE_UPDATE structure contains the updated properties of a processor idle state. |
| [_PEP_PROCESSOR_IDLE_STATE_UPDATE structure](..\wmiguid\ns-pepfx-_pep_processor_idle_state_update.md) | The PEP_PROCESSOR_IDLE_STATE_UPDATE structure contains the updated properties of a processor idle state. |
| [_PEP_PROCESSOR_IDLE_STATE_V2 structure](..\wmiguid\ns-pep_x-_pep_processor_idle_state_v2.md) | The PEP_PROCESSOR_IDLE_STATE_V2 structure describes a processor idle state that the platform extension plug-in (PEP) supports. |
| [_PEP_PROCESSOR_IDLE_STATE_V2 structure](..\wmiguid\ns-pepfx-_pep_processor_idle_state_v2.md) | The PEP_PROCESSOR_IDLE_STATE_V2 structure describes a processor idle state that the platform extension plug-in (PEP) supports. |
| [_PEP_PROCESSOR_PARK_PREFERENCE structure](..\wmiguid\ns-pep_x-_pep_processor_park_preference.md) | The PEP_PROCESSOR_PARK_PREFERENCE structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding whether the specified processor should be parked to reduce power consumption. |
| [_PEP_PROCESSOR_PARK_PREFERENCE structure](..\wmiguid\ns-pepfx-_pep_processor_park_preference.md) | The PEP_PROCESSOR_PARK_PREFERENCE structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding whether the specified processor should be parked to reduce power consumption. |
| [_PEP_PROCESSOR_PARK_STATE structure](..\wmiguid\ns-pep_x-_pep_processor_park_state.md) | The PEP_PROCESSOR_PARK_STATE structure describes the parking state for a single processor. |
| [_PEP_PROCESSOR_PARK_STATE structure](..\wmiguid\ns-pepfx-_pep_processor_park_state.md) | The PEP_PROCESSOR_PARK_STATE structure describes the parking state for a single processor. |
| [_PEP_PROCESSOR_PERF_STATE structure](..\wmiguid\ns-pep_x-_pep_processor_perf_state.md) | Use in the PEP_NOTIFY_PPM_QUERY_DISCRETE_PERF_STATES  notification. This structure describes the properties of a single performance state.  . |
| [_PEP_PROCESSOR_PERF_STATE structure](..\wmiguid\ns-pepfx-_pep_processor_perf_state.md) | Use in the PEP_NOTIFY_PPM_QUERY_DISCRETE_PERF_STATES  notification. This structure describes the properties of a single performance state.  . |
| [_PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure](..\wmiguid\ns-pep_x-_pep_query_component_perf_capabilities.md) | The PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure specifies the number of performance state (P-state) sets that are defined for a component. |
| [_PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure](..\wmiguid\ns-pepfx-_pep_query_component_perf_capabilities.md) | The PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure specifies the number of performance state (P-state) sets that are defined for a component. |
| [_PEP_QUERY_COMPONENT_PERF_SET structure](..\wmiguid\ns-pep_x-_pep_query_component_perf_set.md) | The PEP_QUERY_COMPONENT_PERF_SET structure contains query information about a set of performance state values (P-state set) for a component. |
| [_PEP_QUERY_COMPONENT_PERF_SET structure](..\wmiguid\ns-pepfx-_pep_query_component_perf_set.md) | The PEP_QUERY_COMPONENT_PERF_SET structure contains query information about a set of performance state values (P-state set) for a component. |
| [_PEP_QUERY_COMPONENT_PERF_SET_NAME structure](..\wmiguid\ns-pep_x-_pep_query_component_perf_set_name.md) | The PEP_QUERY_COMPONENT_PERF_SET_NAME structure contains query information about a set of performance state values (P-state set) for a component. |
| [_PEP_QUERY_COMPONENT_PERF_SET_NAME structure](..\wmiguid\ns-pepfx-_pep_query_component_perf_set_name.md) | The PEP_QUERY_COMPONENT_PERF_SET_NAME structure contains query information about a set of performance state values (P-state set) for a component. |
| [_PEP_QUERY_COMPONENT_PERF_STATES structure](..\wmiguid\ns-pep_x-_pep_query_component_perf_states.md) | The PEP_QUERY_COMPONENT_PERF_STATES structure contains a list of discrete performance state (P-state) values for the specified P-state set. |
| [_PEP_QUERY_COMPONENT_PERF_STATES structure](..\wmiguid\ns-pepfx-_pep_query_component_perf_states.md) | The PEP_QUERY_COMPONENT_PERF_STATES structure contains a list of discrete performance state (P-state) values for the specified P-state set. |
| [_PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure](..\wmiguid\ns-pep_x-_pep_query_current_component_perf_state.md) | The PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure contains information about the current P-state in the specified P-state set. |
| [_PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure](..\wmiguid\ns-pepfx-_pep_query_current_component_perf_state.md) | The PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure contains information about the current P-state in the specified P-state set. |
| [_PEP_QUERY_SOC_SUBSYSTEM structure](..\wmiguid\ns-pep_x-_pep_query_soc_subsystem.md) | The PEP_QUERY_SOC_SUBSYSTEM structure is used by the PEP_DPM_QUERY_SOC_SUBSYSTEM notification to gather basic information about a particular system on a chip (SoC) subsystem. |
| [_PEP_QUERY_SOC_SUBSYSTEM structure](..\wmiguid\ns-pepfx-_pep_query_soc_subsystem.md) | The PEP_QUERY_SOC_SUBSYSTEM structure is used by the PEP_DPM_QUERY_SOC_SUBSYSTEM notification to gather basic information about a particular system on a chip (SoC) subsystem. |
| [_PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME structure](..\wmiguid\ns-pep_x-_pep_query_soc_subsystem_blocking_time.md) | The PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME structure is used by the PEP_DPM_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME notification to collect details about the blocking duration for a particular system on a chip (SoC) subsystem. |
| [_PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME structure](..\wmiguid\ns-pepfx-_pep_query_soc_subsystem_blocking_time.md) | The PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME structure is used by the PEP_DPM_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME notification to collect details about the blocking duration for a particular system on a chip (SoC) subsystem. |
| [_PEP_QUERY_SOC_SUBSYSTEM_COUNT structure](..\wmiguid\ns-pep_x-_pep_query_soc_subsystem_count.md) | The PEP_QUERY_SOC_SUBSYSTEM_COUNT structure is used to tell the OS whether the PEP supports system on a chip (SoC) subsystem accounting for a given platform idle state. |
| [_PEP_QUERY_SOC_SUBSYSTEM_COUNT structure](..\wmiguid\ns-pepfx-_pep_query_soc_subsystem_count.md) | The PEP_QUERY_SOC_SUBSYSTEM_COUNT structure is used to tell the OS whether the PEP supports system on a chip (SoC) subsystem accounting for a given platform idle state. |
| [_PEP_QUERY_SOC_SUBSYSTEM_METADATA structure](..\wmiguid\ns-pep_x-_pep_query_soc_subsystem_metadata.md) | The PEP_QUERY_SOC_SUBSYSTEM_METADATA structure is used with the PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA notification to collect optional metadata about the system on a chip (SoC) subsystem whose blocking time has just been queried. |
| [_PEP_QUERY_SOC_SUBSYSTEM_METADATA structure](..\wmiguid\ns-pepfx-_pep_query_soc_subsystem_metadata.md) | The PEP_QUERY_SOC_SUBSYSTEM_METADATA structure is used with the PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA notification to collect optional metadata about the system on a chip (SoC) subsystem whose blocking time has just been queried. |
| [_PEP_REGISTER_COMPONENT_PERF_STATES structure](..\wmiguid\ns-pep_x-_pep_register_component_perf_states.md) | The PEP_REGISTER_COMPONENT_PERF_STATES structure describes the performance states (P-states) of the specified component. |
| [_PEP_REGISTER_COMPONENT_PERF_STATES structure](..\wmiguid\ns-pepfx-_pep_register_component_perf_states.md) | The PEP_REGISTER_COMPONENT_PERF_STATES structure describes the performance states (P-states) of the specified component. |
| [_PEP_REGISTER_CRASHDUMP_DEVICE structure](..\wmiguid\ns-pep_x-_pep_register_crashdump_device.md) | The PEP_REGISTER_CRASHDUMP_DEVICE structure provides a callback routine to turn on a crash-dump device. |
| [_PEP_REGISTER_CRASHDUMP_DEVICE structure](..\wmiguid\ns-pepfx-_pep_register_crashdump_device.md) | The PEP_REGISTER_CRASHDUMP_DEVICE structure provides a callback routine to turn on a crash-dump device. |
| [_PEP_REGISTER_DEBUGGER structure](..\wmiguid\ns-pep_x-_pep_register_debugger.md) | The PEP_REGISTER_DEBUGGER structure identifies a registered device that is a core system resource that provides debugger transport. |
| [_PEP_REGISTER_DEBUGGER structure](..\wmiguid\ns-pepfx-_pep_register_debugger.md) | The PEP_REGISTER_DEBUGGER structure identifies a registered device that is a core system resource that provides debugger transport. |
| [_PEP_REGISTER_DEVICE_V2 structure](..\wmiguid\ns-pep_x-_pep_register_device_v2.md) | The PEP_REGISTER_DEVICE_V2 structure describes a device whose driver stack has just registered with the Windows power management framework (PoFx). |
| [_PEP_REGISTER_DEVICE_V2 structure](..\wmiguid\ns-pepfx-_pep_register_device_v2.md) | The PEP_REGISTER_DEVICE_V2 structure describes a device whose driver stack has just registered with the Windows power management framework (PoFx). |
| [_PEP_REQUEST_COMPONENT_PERF_STATE structure](..\wmiguid\ns-pep_x-_pep_request_component_perf_state.md) | The PEP_REQUEST_COMPONENT_PERF_STATE structure contains a list of performance state (P-state) changes requested by the Windows power management framework (PoFx), plus status information about the handling of these requests by the platform extension plug-in (PEP). |
| [_PEP_REQUEST_COMPONENT_PERF_STATE structure](..\wmiguid\ns-pepfx-_pep_request_component_perf_state.md) | The PEP_REQUEST_COMPONENT_PERF_STATE structure contains a list of performance state (P-state) changes requested by the Windows power management framework (PoFx), plus status information about the handling of these requests by the platform extension plug-in (PEP). |
| [_PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure](..\wmiguid\ns-pep_x-_pep_reset_soc_subsystem_accounting.md) | The PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure is provided to the platform extension plug-in (PEP) as part of a PEP_DPM_RESET_SOC_SUBSYSTEM_ACCOUNTING notification. |
| [_PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure](..\wmiguid\ns-pepfx-_pep_reset_soc_subsystem_accounting.md) | The PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure is provided to the platform extension plug-in (PEP) as part of a PEP_DPM_RESET_SOC_SUBSYSTEM_ACCOUNTING notification. |
| [_PEP_SOC_SUBSYSTEM_METADATA structure](..\wmiguid\ns-pep_x-_pep_soc_subsystem_metadata.md) | The PEP_SOC_SUBSYSTEM_METADATA structure contains key-value pairs that contain metadata for a system on a chip (SoC) subsystem. It is used in the context of a PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA notification sent to a platform extension plug-in (PEP). |
| [_PEP_SOC_SUBSYSTEM_METADATA structure](..\wmiguid\ns-pepfx-_pep_soc_subsystem_metadata.md) | The PEP_SOC_SUBSYSTEM_METADATA structure contains key-value pairs that contain metadata for a system on a chip (SoC) subsystem. It is used in the context of a PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA notification sent to a platform extension plug-in (PEP). |
| [_PEP_SYSTEM_LATENCY structure](..\wmiguid\ns-pep_x-_pep_system_latency.md) | The PEP_SYSTEM_LATENCY structure specifies the new value for the system latency tolerance. |
| [_PEP_SYSTEM_LATENCY structure](..\wmiguid\ns-pepfx-_pep_system_latency.md) | The PEP_SYSTEM_LATENCY structure specifies the new value for the system latency tolerance. |
| [_PEP_UNMASKED_INTERRUPT_FLAGS structure](..\wmiguid\ns-pep_x-_pep_unmasked_interrupt_flags.md) | The PEP_UNMASKED_INTERRUPT_FLAGS union indicates whether an unmasked interrupt source is a primary interrupt or a secondary interrupt. |
| [_PEP_UNMASKED_INTERRUPT_FLAGS structure](..\wmiguid\ns-pepfx-_pep_unmasked_interrupt_flags.md) | The PEP_UNMASKED_INTERRUPT_FLAGS union indicates whether an unmasked interrupt source is a primary interrupt or a secondary interrupt. |
| [_PEP_UNMASKED_INTERRUPT_INFORMATION structure](..\wmiguid\ns-pep_x-_pep_unmasked_interrupt_information.md) | The PEP_UNMASKED_INTERRUPT_INFORMATION structure contains information about an interrupt source. |
| [_PEP_UNMASKED_INTERRUPT_INFORMATION structure](..\wmiguid\ns-pepfx-_pep_unmasked_interrupt_information.md) | The PEP_UNMASKED_INTERRUPT_INFORMATION structure contains information about an interrupt source. |
| [_PEP_UNREGISTER_DEVICE structure](..\wmiguid\ns-pep_x-_pep_unregister_device.md) | The PEP_UNREGISTER_DEVICE structure identifies a device whose registration is being removed from the Windows power management framework (PoFx). |
| [_PEP_UNREGISTER_DEVICE structure](..\wmiguid\ns-pepfx-_pep_unregister_device.md) | The PEP_UNREGISTER_DEVICE structure identifies a device whose registration is being removed from the Windows power management framework (PoFx). |
| [_PEP_WORK structure](..\wmiguid\ns-pep_x-_pep_work.md) | The PEP_WORK structure indicates whether the PEP has a work request to submit to the Windows power management framework (PoFx). |
| [_PEP_WORK structure](..\wmiguid\ns-pepfx-_pep_work.md) | The PEP_WORK structure indicates whether the PEP has a work request to submit to the Windows power management framework (PoFx). |
| [_PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE structure](..\wmiguid\ns-pep_x-_pep_work_acpi_evaluate_control_method_complete.md) | The PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE structure contains the results of an ACPI control method that was asynchronously evaluated by the platform extension plug-in (PEP). |
| [_PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE structure](..\wmiguid\ns-pepfx-_pep_work_acpi_evaluate_control_method_complete.md) | The PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE structure contains the results of an ACPI control method that was asynchronously evaluated by the platform extension plug-in (PEP). |
| [_PEP_WORK_ACPI_NOTIFY structure](..\wmiguid\ns-pep_x-_pep_work_acpi_notify.md) | The PEP_WORK_ACPI_NOTIFY structure contains the ACPI Notify code for a device that has generated a hardware event. |
| [_PEP_WORK_ACPI_NOTIFY structure](..\wmiguid\ns-pepfx-_pep_work_acpi_notify.md) | The PEP_WORK_ACPI_NOTIFY structure contains the ACPI Notify code for a device that has generated a hardware event. |
| [_PEP_WORK_ACTIVE_COMPLETE structure](..\wmiguid\ns-pep_x-_pep_work_active_complete.md) | The PEP_WORK_ACTIVE_COMPLETE structure identifies a component that is now in the active condition. |
| [_PEP_WORK_COMPLETE_IDLE_STATE structure](..\wmiguid\ns-pep_x-_pep_work_complete_idle_state.md) | The PEP_WORK_COMPLETE_IDLE_STATE structure identifies a component that the platform extension plug-in (PEP) has prepared for a transition to a new Fx power state. |
| [_PEP_WORK_COMPLETE_IDLE_STATE structure](..\wmiguid\ns-pepfx-_pep_work_complete_idle_state.md) | The PEP_WORK_COMPLETE_IDLE_STATE structure identifies a component that the platform extension plug-in (PEP) has prepared for a transition to a new Fx power state. |
| [_PEP_WORK_COMPLETE_PERF_STATE structure](..\wmiguid\ns-pep_x-_pep_work_complete_perf_state.md) | The PEP_WORK_COMPLETE_PERF_STATE structure describes the completion status of a previously requested update to the performance values assigned to a list of performance state (P-state) sets. |
| [_PEP_WORK_COMPLETE_PERF_STATE structure](..\wmiguid\ns-pepfx-_pep_work_complete_perf_state.md) | The PEP_WORK_COMPLETE_PERF_STATE structure describes the completion status of a previously requested update to the performance values assigned to a list of performance state (P-state) sets. |
| [_PEP_WORK_DEVICE_IDLE structure](..\wmiguid\ns-pep_x-_pep_work_device_idle.md) | The PEP_WORK_DEVICE_IDLE structure indicates whether to ignore the idle time-out for the specified device. |
| [_PEP_WORK_DEVICE_POWER structure](..\wmiguid\ns-pep_x-_pep_work_device_power.md) | The PEP_WORK_DEVICE_POWER structure describes the new power requirements for the specified device. |
| [_PEP_WORK_IDLE_STATE structure](..\wmiguid\ns-pep_x-_pep_work_idle_state.md) | The PEP_WORK_IDLE_STATE structure contains a request to transition a component to an Fx power state. |
| [_PEP_WORK_INFORMATION structure](..\wmiguid\ns-pep_x-_pep_work_information.md) | The PEP_WORK_INFORMATION structure describes a work item that the PEP is submitting to the Windows power management framework (PoFx). |
| [_PEP_WORK_INFORMATION structure](..\wmiguid\ns-pepfx-_pep_work_information.md) | The PEP_WORK_INFORMATION structure describes a work item that the PEP is submitting to the Windows power management framework (PoFx). |
| [_PEP_WORK_POWER_CONTROL structure](..\wmiguid\ns-pep_x-_pep_work_power_control.md) | The PEP_WORK_POWER_CONTROL structure contains the parameters for a power control request that the platform extension plug-in (PEP) sends directly to a processor driver. |
| [_PEP_WORK_POWER_CONTROL structure](..\wmiguid\ns-pepfx-_pep_work_power_control.md) | The PEP_WORK_POWER_CONTROL structure contains the parameters for a power control request that the platform extension plug-in (PEP) sends directly to a processor driver. |
| [_PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structure](..\wmiguid\ns-ntddk-_physical_counter_resource_descriptor.md) | The PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structure describes the counter resources available on the platform. |
| [_PHYSICAL_COUNTER_RESOURCE_LIST structure](..\wmiguid\ns-ntddk-_physical_counter_resource_list.md) | The PHYSICAL_COUNTER_RESOURCE_LIST structure describes an array of PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structures. |
| [_PLUGPLAY_NOTIFICATION_HEADER structure](..\wmiguid\ns-wdm-_plugplay_notification_header.md) | A PLUGPLAY_NOTIFICATION_HEADER structure is included at the beginning of each PnP notification structure, such as a DEVICE_INTERFACE_CHANGE_NOTIFICATION structure. |
| [_PNP_BUS_INFORMATION structure](..\wmiguid\ns-wdm-_pnp_bus_information.md) | The PNP_BUS_INFORMATION structure describes a bus. |
| [_PNP_LOCATION_INTERFACE structure](..\wmiguid\ns-ntddk-_pnp_location_interface.md) | The PNP_LOCATION_INTERFACE structure describes the GUID_PNP_LOCATION_INTERFACE interface. |
| [_POWER_PLATFORM_INFORMATION structure](..\wmiguid\ns-ntpoapi-_power_platform_information.md) | The POWER_PLATFORM_INFORMATION structure contains information about the power capabilities of the system. |
| [_POWER_PLATFORM_INFORMATION structure](..\wmiguid\ns-wdm-_power_platform_information.md) | The POWER_PLATFORM_INFORMATION structure contains information about the power capabilities of the system. |
| [_POWER_STATE structure](..\wmiguid\ns-ntpoapi-_power_state.md) | The POWER_STATE union specifies a system power state value or a device power state value. |
| [_POWER_STATE structure](..\wmiguid\ns-wdm-_power_state.md) | The POWER_STATE union specifies a system power state value or a device power state value. |
| [_POWER_THROTTLING_PROCESS_STATE structure](..\wmiguid\ns-ntddk-_power_throttling_process_state.md) | Stores the throttling policies and how to apply them to a target process when that process is subject to power management. |
| [_POWER_THROTTLING_THREAD_STATE structure](..\wmiguid\ns-ntddk-_power_throttling_thread_state.md) | Stores the throttling policies and how to apply them to a target thread when that thread is subject to power management. |
| [_PO_FX_COMPONENT_IDLE_STATE structure](..\wmiguid\ns-wdm-_po_fx_component_idle_state.md) | The PO_FX_COMPONENT_IDLE_STATE structure specifies the attributes of an Fx power state of a component in a device. |
| [_PO_FX_COMPONENT_PERF_INFO structure](..\wmiguid\ns-wdm-_po_fx_component_perf_info.md) | The PO_FX_COMPONENT_PERF_INFO structure describes all the sets of performance states for a single component within a device. |
| [_PO_FX_COMPONENT_PERF_SET structure](..\wmiguid\ns-wdm-_po_fx_component_perf_set.md) | The PO_FX_COMPONENT_PERF_SET structure represents a set of performance states for a single component within a device. |
| [_PO_FX_COMPONENT_V1 structure](..\wmiguid\ns-wdm-_po_fx_component_v1.md) | The PO_FX_COMPONENT structure describes the power state attributes of a component in a device. |
| [_PO_FX_COMPONENT_V2 structure](..\wmiguid\ns-wdm-_po_fx_component_v2.md) | The PO_FX_COMPONENT structure describes the power state attributes of a component in a device. |
| [_PO_FX_CORE_DEVICE structure](..\wmiguid\ns-pep_x-_po_fx_core_device.md) | The PO_FX_CORE_DEVICE structure contains information about the power-state attributes of the components in a core system resource, and provides a software interface for power-managing these components. |
| [_PO_FX_CORE_DEVICE structure](..\wmiguid\ns-pepfx-_po_fx_core_device.md) | The PO_FX_CORE_DEVICE structure contains information about the power-state attributes of the components in a core system resource, and provides a software interface for power-managing these components. |
| [_PO_FX_DEVICE_V1 structure](..\wmiguid\ns-wdm-_po_fx_device_v1.md) | The PO_FX_DEVICE structure describes the power attributes of a device to the power management framework (PoFx). |
| [_PO_FX_DEVICE_V2 structure](..\wmiguid\ns-wdm-_po_fx_device_v2.md) | The PO_FX_DEVICE structure describes the power attributes of a device to the power management framework (PoFx). |
| [_PO_FX_PERF_STATE structure](..\wmiguid\ns-wdm-_po_fx_perf_state.md) | The PO_FX_PERF_STATE structure represents a performance state for a single component within a device. |
| [_PO_FX_PERF_STATE_CHANGE structure](..\wmiguid\ns-wdm-_po_fx_perf_state_change.md) | The PO_FX_PERF_STATE_CHANGE structure contains information about a change to a performance state that is being requested by calling the PoFxIssueComponentPerfStateChange or PoFxIssueComponentPerfStateChangeMultiple routine. |
| [_PRIVILEGE_SET structure](..\wmiguid\ns-wdm-_privilege_set.md) | The PRIVILEGE_SET structure specifies a set of security privileges. For more information, see the reference page for PRIVILEGE_SET in the Microsoft Windows SDK documentation. |
| [_PROCESS_MITIGATION_CHILD_PROCESS_POLICY structure](..\wmiguid\ns-ntddk-_process_mitigation_child_process_policy.md) | Stores policy information about creating child processes. |
| [_PROCESS_MITIGATION_PAYLOAD_RESTRICTION_POLICY structure](..\wmiguid\ns-ntddk-_process_mitigation_payload_restriction_policy.md) | Stores information about process mitigation policy. |
| [_PROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY structure](..\wmiguid\ns-ntddk-_process_mitigation_system_call_filter_policy.md) | This structure is not supported. |
| [_PROCESS_READWRITEVM_LOGGING_INFORMATION structure](..\wmiguid\ns-ntddk-_process_readwritevm_logging_information.md) | Stores options for read/write access for telemetry per process. |
| [_PS_CREATE_NOTIFY_INFO structure](..\wmiguid\ns-ntddk-_ps_create_notify_info.md) | The PS_CREATE_NOTIFY_INFO structure provides information about a newly created process. |
| [_REENUMERATE_SELF_INTERFACE_STANDARD structure](..\wmiguid\ns-wdm-_reenumerate_self_interface_standard.md) | The REENUMERATE_SELF_INTERFACE_STANDARD interface structure enables a driver to request that its parent bus driver reenumerate the driver's device. This structure defines the GUID_REENUMERATE_SELF_INTERFACE_STANDARD interface. |
| [_REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure](..\wmiguid\ns-wdm-_reg_callback_context_cleanup_information.md) | The REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure contains information that a driver's RegistryCallback routine can use to free resources that the driver previously allocated for the context that is associated with a registry object. |
| [_REG_CREATE_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_create_key_information.md) | The REG_CREATE_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry key that is being created. |
| [_REG_CREATE_KEY_INFORMATION_V1 structure](..\wmiguid\ns-wdm-_reg_create_key_information_v1.md) | The REG_CREATE_KEY_INFORMATION_V1 structure contains information that a filter driver's RegistryCallback routine can use when a registry key is being created. |
| [_REG_DELETE_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_delete_key_information.md) | The REG_DELETE_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry key is being deleted. |
| [_REG_DELETE_VALUE_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_delete_value_key_information.md) | The REG_DELETE_VALUE_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry key's value is being deleted. |
| [_REG_ENUMERATE_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_enumerate_key_information.md) | The REG_ENUMERATE_KEY_INFORMATION structure describes one subkey of a key whose subkeys are being enumerated. |
| [_REG_ENUMERATE_VALUE_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_enumerate_value_key_information.md) | The REG_ENUMERATE_VALUE_KEY_INFORMATION structure describes one value entry of a key whose value entries are being enumerated. |
| [_REG_KEY_HANDLE_CLOSE_INFORMATION structure](..\wmiguid\ns-wdm-_reg_key_handle_close_information.md) | The REG_KEY_HANDLE_CLOSE_INFORMATION structure contains information about a registry key whose handle is about to be closed. |
| [_REG_LOAD_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_load_key_information.md) | The REG_LOAD_KEY_INFORMATION structure contains information about a registry hive that is being loaded. |
| [_REG_POST_CREATE_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_post_create_key_information.md) | The REG_POST_CREATE_KEY_INFORMATION structure contains the result of an attempt to create a registry key. |
| [_REG_POST_OPERATION_INFORMATION structure](..\wmiguid\ns-wdm-_reg_post_operation_information.md) | The REG_POST_OPERATION_INFORMATION structure contains information about a completed registry operation that a RegistryCallback routine can use. |
| [_REG_PRE_CREATE_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_pre_create_key_information.md) | The REG_PRE_OPEN_KEY_INFORMATION structure contains the name of a registry key that is about to be opened. |
| [_REG_QUERY_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_query_key_information.md) | The REG_QUERY_KEY_INFORMATION structure describes the metadata that is about to be queried for a key. |
| [_REG_QUERY_KEY_NAME structure](..\wmiguid\ns-wdm-_reg_query_key_name.md) | The REG_QUERY_KEY_NAME structure describes the full registry key name of an object being queried. |
| [_REG_QUERY_KEY_SECURITY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_query_key_security_information.md) | The REG_QUERY_KEY_SECURITY_INFORMATION structure receives security information for a registry key object. |
| [_REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_query_multiple_value_key_information.md) | The REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION structure describes the multiple value entries that are being retrieved for a key. |
| [_REG_QUERY_VALUE_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_query_value_key_information.md) | The REG_QUERY_VALUE_KEY_INFORMATION structure contains information about a registry key's value entry that is being queried. |
| [_REG_RENAME_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_rename_key_information.md) | The REG_RENAME_KEY_INFORMATION structure contains the new name for a registry key whose name is about to be changed. |
| [_REG_REPLACE_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_replace_key_information.md) | The REG_REPLACE_KEY_INFORMATION structure describes the metadata that is about to be replaced for a key. |
| [_REG_RESTORE_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_restore_key_information.md) | The REG_RESTORE_KEY_INFORMATION structure contains the information for a registry key that is about to be restored. |
| [_REG_SAVE_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_save_key_information.md) | The REG_SAVE_KEY_INFORMATION structure contains the information for a registry key that is about to be saved. |
| [_REG_SET_INFORMATION_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_set_information_key_information.md) | The REG_SET_INFORMATION_KEY_INFORMATION structure describes a new setting for a key's metadata. |
| [_REG_SET_KEY_SECURITY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_set_key_security_information.md) | The REG_SET_KEY_SECURITY_INFORMATION structure specifies security information for a registry key object. |
| [_REG_SET_VALUE_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_set_value_key_information.md) | The REG_SET_VALUE_INFORMATION structure describes a new setting for a registry key's value entry. |
| [_REG_UNLOAD_KEY_INFORMATION structure](..\wmiguid\ns-wdm-_reg_unload_key_information.md) | The REG_UNLOAD_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry hive is unloaded. |
| [_RESOURCEMANAGER_BASIC_INFORMATION structure](..\wmiguid\ns-wdm-_resourcemanager_basic_information.md) | The RESOURCEMANAGER_BASIC INFORMATION structure contains information about a resource manager object. |
| [_RESOURCEMANAGER_COMPLETION_INFORMATION structure](..\wmiguid\ns-wdm-_resourcemanager_completion_information.md) | The RESOURCEMANAGER_COMPLETION_INFORMATION structure is not used. |
| [_SCATTER_GATHER_LIST structure](..\wmiguid\ns-wdm-_scatter_gather_list.md) | The SCATTER_GATHER_LIST structure describes the scatter/gather list for a DMA operation. |
| [_SDEV_IDENTIFIER_INTERFACE structure](..\wmiguid\ns-wdm-_sdev_identifier_interface.md) | This material is not yet available. This placeholder topic is provided as an example of documentation that may be included in a later release. |
| [_SECTION_OBJECT_POINTERS structure](..\wmiguid\ns-wdm-_section_object_pointers.md) | The SECTION_OBJECT_POINTERS structure, allocated by a file system or a redirector driver, is used by the memory manager and cache manager to store file-mapping and cache-related information for a file stream. |
| [_SILO_MONITOR_REGISTRATION structure](..\wmiguid\ns-ntddk-_silo_monitor_registration.md) | This structure specifies a server silo monitor that can receive notifications about server silo events. |
| [_SLIST_ENTRY structure](..\wmiguid\ns-wdm-_slist_entry.md) | An SLIST_ENTRY structure describes an entry in a sequenced singly linked list. |
| [_SYSENV_VALUE structure](..\wmiguid\ns-ntddsysenv-_sysenv_value.md) | Stores the value of a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_GET_VARIABLE request. |
| [_SYSENV_VARIABLE structure](..\wmiguid\ns-ntddsysenv-_sysenv_variable.md) | Stores the name a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_GET_VARIABLE request. |
| [_SYSENV_VARIABLE_INFO structure](..\wmiguid\ns-ntddsysenv-_sysenv_variable_info.md) | Stores the information about a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_QUERY_VARIABLE_INFO request. |
| [_SYSTEM_POWER_STATE_CONTEXT structure](..\wmiguid\ns-ntpoapi-_system_power_state_context.md) | The SYSTEM_POWER_STATE_CONTEXT structure is a partially opaque system structure that contains information about the previous system power states of a computer. |
| [_SYSTEM_POWER_STATE_CONTEXT structure](..\wmiguid\ns-wdm-_system_power_state_context.md) | The SYSTEM_POWER_STATE_CONTEXT structure is a partially opaque system structure that contains information about the previous system power states of a computer. |
| [_TARGET_DEVICE_CUSTOM_NOTIFICATION structure](..\wmiguid\ns-wdm-_target_device_custom_notification.md) | The TARGET_DEVICE_CUSTOM_NOTIFICATION structure describes a custom device event. |
| [_TARGET_DEVICE_REMOVAL_NOTIFICATION structure](..\wmiguid\ns-wdm-_target_device_removal_notification.md) | The TARGET_DEVICE_REMOVAL_NOTIFICATION structure describes a device-removal event. The PnP manager sends this structure to a driver that registered a callback routine for notification of EventCategoryTargetDeviceChange events. |
| [_THERMAL_COOLING_INTERFACE structure](..\wmiguid\ns-poclass-_thermal_cooling_interface.md) | The THERMAL_COOLING_INTERFACE structure enables the operating system to control the thermal management settings of a device. |
| [_TRANSACTIONMANAGER_BASIC_INFORMATION structure](..\wmiguid\ns-wdm-_transactionmanager_basic_information.md) | The TRANSACTIONMANAGER_BASIC_INFORMATION structure contains information about a transaction manager object. |
| [_TRANSACTIONMANAGER_LOGPATH_INFORMATION structure](..\wmiguid\ns-wdm-_transactionmanager_logpath_information.md) | The TRANSACTIONMANAGER_LOGPATH_INFORMATION structure contains information about a transaction manager object. |
| [_TRANSACTIONMANAGER_LOG_INFORMATION structure](..\wmiguid\ns-wdm-_transactionmanager_log_information.md) | The TRANSACTIONMANAGER_LOG_INFORMATION structure contains information about a transaction manager object. |
| [_TRANSACTIONMANAGER_RECOVERY_INFORMATION structure](..\wmiguid\ns-wdm-_transactionmanager_recovery_information.md) | The TRANSACTIONMANAGER_RECOVERY_INFORMATION structure contains information about a transaction manager object. |
| [_TRANSACTION_BASIC_INFORMATION structure](..\wmiguid\ns-wdm-_transaction_basic_information.md) | The TRANSACTION_BASIC_INFORMATION structure contains information about a transaction object. |
| [_TRANSACTION_ENLISTMENTS_INFORMATION structure](..\wmiguid\ns-wdm-_transaction_enlistments_information.md) | The TRANSACTION_ENLISTMENTS_INFORMATION structure contains information about the enlistments that are associated with a transaction object. |
| [_TRANSACTION_ENLISTMENT_PAIR structure](..\wmiguid\ns-wdm-_transaction_enlistment_pair.md) | The TRANSACTION_ENLISTMENT_PAIR structure contains information about an enlistment that is associated with a transaction object. |
| [_TRANSACTION_PROPERTIES_INFORMATION structure](..\wmiguid\ns-wdm-_transaction_properties_information.md) | The TRANSACTION_PROPERTIES_INFORMATION structure contains a transaction object's properties. |
| [_VPCI_INVALIDATE_BLOCK_OUTPUT structure](..\wmiguid\ns-vpci-_vpci_invalidate_block_output.md) | The VPCI_INVALIDATE_BLOCK_OUTPUT structure is used in an IOCTL_VPCI_INVALIDATE_BLOCK IOCTL request. |
| [_VPCI_READ_BLOCK_INPUT structure](..\wmiguid\ns-vpci-_vpci_read_block_input.md) | The VPCI_READ_BLOCK_INPUT structure is used in an IOCTL_VPCI_READ_BLOCK IOCTL request to read data from a specified configuration block of data for a PCI Express (PCIe) virtual function (VF). |
| [_VPCI_WRITE_BLOCK_INPUT structure](..\wmiguid\ns-vpci-_vpci_write_block_input.md) | The VPCI_WRITE_BLOCK_INPUT structure is used in an IOCTL_VPCI_WRITE_BLOCK IOCTL request to write data to a specified configuration block for a PCI Express (PCIe) virtual function (VF). |
| [_WMIGUIDREGINFO structure](..\wmiguid\ns-wmilib-_wmiguidreginfo.md) | The WMIGUIDREGINFO structure contains registration information for a given data block or event block exposed by a driver that uses the WMI library support routines. |
| [_WMILIB_CONTEXT structure](..\wmiguid\ns-wmilib-_wmilib_context.md) | The WMILIB_CONTEXT structure provides registration information for a driver's data blocks and event blocks and defines entry points for the driver's WMI library callback routines. |
| [_WNODE_HEADER structure](..\wmiguid\ns-wmistr-_wnode_header.md) | The WNODE_HEADER structure is the first member of all other WNODE_XXX structures. It contains information common to all such structures. |
| [_XVARIABLE_NAME structure](..\wmiguid\ns-ntddsysenv-_xvariable_name.md) | Stores the name of a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_ENUM_VARIABLES request. |
| [_XVARIABLE_NAME_AND_VALUE structure](..\wmiguid\ns-ntddsysenv-_xvariable_name_and_value.md) | Stores the name and value of a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_ENUM_VARIABLES and IOCTL_SYSENV_SET_VARIABLE requests. |
| [tagWNODE_ALL_DATA structure](..\wmiguid\ns-wmistr-tagwnode_all_data.md) | The WNODE_ALL_DATA structure contains data for all instances of a data block or event block. |
| [tagWNODE_EVENT_ITEM structure](..\wmiguid\ns-wmistr-tagwnode_event_item.md) | The WNODE_EVENT_ITEM structure contains data generated by a driver for an event. |
| [tagWNODE_EVENT_REFERENCE structure](..\wmiguid\ns-wmistr-tagwnode_event_reference.md) | The WNODE_EVENT_REFERENCE structure contains information that WMI can use to query for an event that exceeds the event size limit set in the registry. |
| [tagWNODE_METHOD_ITEM structure](..\wmiguid\ns-wmistr-tagwnode_method_item.md) | The WNODE_METHOD_ITEM structure indicates a method associated with an instance of a data block and contains any input data for the method. |
| [tagWNODE_SINGLE_INSTANCE structure](..\wmiguid\ns-wmistr-tagwnode_single_instance.md) | The WNODE_SINGLE_INSTANCE structure contains values for all data items in one instance of a data block. |
| [tagWNODE_SINGLE_ITEM structure](..\wmiguid\ns-wmistr-tagwnode_single_item.md) | The WNODE_SINGLE_ITEM structure contains the value of a single data item in an instance of a data block. |
| [tagWNODE_TOO_SMALL structure](..\wmiguid\ns-wmistr-tagwnode_too_small.md) | The WNODE_TOO_SMALL structure indicates the size of the buffer needed to receive output from a request. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [*PPEP_PROCESSOR_IDLE_CANCEL_CODE enumeration](..\wmiguid\ne-pep_x-ppep_processor_idle_cancel_code.md) | The PEP_PROCESSOR_IDLE_CANCEL_CODE enumeration values indicate reasons why a processor cannot enter an idle state that was previously selected by the platform extension plug-in (PEP). |
| [*PPEP_PROCESSOR_IDLE_TYPE enumeration](..\wmiguid\ne-pep_x-ppep_processor_idle_type.md) | The PEP_PROCESSOR_IDLE_TYPE enumeration indicates whether idle constraints apply to just the current processor or to all processors in the hardware platform. |
| [DEVICE_REGISTRY_PROPERTY enumeration](..\wmiguid\ne-wdm-device_registry_property.md) | The DEVICE_REGISTRY_PROPERTY enumeration identifies device properties that are stored in the registry. |
| [DMA_COMPLETION_STATUS enumeration](..\wmiguid\ne-wdm-dma_completion_status.md) | The DMA_COMPLETION_STATUS enumeration describes the completion status of a DMA transfer. |
| [POWER_INFORMATION_LEVEL enumeration](..\wmiguid\ne-ntpoapi-power_information_level.md) | Indicates power level information. |
| [POWER_INFORMATION_LEVEL enumeration](..\wmiguid\ne-wdm-power_information_level.md) | Indicates power level information. |
| [_BDCB_CALLBACK_TYPE enumeration](..\wmiguid\ne-ntddk-_bdcb_callback_type.md) | The BDCB_CALLBACK_TYPE enumeration specifies whether the callback being passed to a BOOT_DRIVER_CALLBACK_FUNCTION routine is a status update or a boot-start driver initialization notification. |
| [_BDCB_CLASSIFICATION enumeration](..\wmiguid\ne-ntddk-_bdcb_classification.md) | The BDCB_CLASSIFICATION enumeration lists different classifications of boot start images. |
| [_BDCB_STATUS_UPDATE_TYPE enumeration](..\wmiguid\ne-ntddk-_bdcb_status_update_type.md) | The BDCB_STATUS_UPDATE_TYPE enumeration lists the types of boot-driver callback status updates. |
| [_BOUND_CALLBACK_STATUS enumeration](..\wmiguid\ne-wdm-_bound_callback_status.md) | The BOUND_CALLBACK_STATUS enumeration indicates how a user-mode bounds exception was processed by the BoundCallback function. |
| [_BUS_DATA_TYPE enumeration](..\wmiguid\ne-ntddk-_bus_data_type.md) | The BUS_DATA_TYPE enumeration indicates the type of bus configuration space. |
| [_CLFS_CONTEXT_MODE enumeration](..\wmiguid\ne-wdm-_clfs_context_mode.md) | The CLFS_CONTEXT_MODE enumeration indicates the type of sequence that the Common Log File System (CLFS) driver follows when it reads a set of records from a stream. |
| [_CLFS_MGMT_POLICY_TYPE enumeration](..\wmiguid\ne-wdm-_clfs_mgmt_policy_type.md) | The CLFS_MGMT_POLICY_TYPE enumeration type identifies the type of a CLFS management policy. |
| [_CLS_LOG_INFORMATION_CLASS enumeration](..\wmiguid\ne-wdm-_cls_log_information_class.md) | The CLFS_LOG_INFORMATION_CLASS enumeration indicates the type of information that is requested by a call to ClfsQueryLogFileInformation. |
| [_D3COLD_LAST_TRANSITION_STATUS enumeration](..\wmiguid\ne-wdm-_d3cold_last_transition_status.md) | The D3COLD_LAST_TRANSITION_STATUS enumeration indicates whether the most recent transition to the D3hot device power state was followed by a transition to the D3cold device power state. |
| [_DEVICE_INSTALL_STATE enumeration](..\wmiguid\ne-wdm-_device_install_state.md) | The DEVICE_INSTALL_STATE enumeration describes a device's installation state. |
| [_DEVICE_POWER_STATE enumeration](..\wmiguid\ne-ntpoapi-_device_power_state.md) | The DEVICE_POWER_STATE enumeration type indicates a device power state. |
| [_DEVICE_POWER_STATE enumeration](..\wmiguid\ne-wdm-_device_power_state.md) | The DEVICE_POWER_STATE enumeration type indicates a device power state. |
| [_DEVICE_REMOVAL_POLICY enumeration](..\wmiguid\ne-wdm-_device_removal_policy.md) | The DEVICE_REMOVAL_POLICY enumeration describes a device's removal policy. |
| [_DEVICE_RESET_TYPE enumeration](..\wmiguid\ne-wdm-_device_reset_type.md) | The DEVICE_RESET_TYPE enumeration specifies the type of device reset that is being requested by a call to the DeviceReset routine of the GUID_DEVICE_RESET_INTERFACE_STANDARD interface. |
| [_DEVICE_WAKE_DEPTH enumeration](..\wmiguid\ne-wdm-_device_wake_depth.md) | The DEVICE_WAKE_DEPTH enumeration specifies the deepest device power state from which a device can trigger a wake signal. |
| [_ENLISTMENT_INFORMATION_CLASS enumeration](..\wmiguid\ne-wdm-_enlistment_information_class.md) | The ENLISTMENT_INFORMATION_CLASS enumeration identifies the type of information that the ZwSetInformationEnlistment routine can set and that the ZwQueryInformationEnlistment routine can retrieve for an enlistment object. |
| [_GPIO_PIN_CONFIG_TYPE enumeration](..\wmiguid\ne-pep_x-_gpio_pin_config_type.md) | The GPIO_PIN_CONFIG_TYPE enumeration describes a connection IO resource. |
| [_GPIO_PIN_CONFIG_TYPE enumeration](..\wmiguid\ne-pepfx-_gpio_pin_config_type.md) | The GPIO_PIN_CONFIG_TYPE enumeration describes a connection IO resource. |
| [_GPIO_PIN_IORESTRICTION_TYPE enumeration](..\wmiguid\ne-pep_x-_gpio_pin_iorestriction_type.md) | The GPIO_PIN_IORESTRICTION_TYPE enumeration describes the functions that a GPIO pin is limited to performing. |
| [_GPIO_PIN_IORESTRICTION_TYPE enumeration](..\wmiguid\ne-pepfx-_gpio_pin_iorestriction_type.md) | The GPIO_PIN_IORESTRICTION_TYPE enumeration describes the functions that a GPIO pin is limited to performing. |
| [_HARDWARE_COUNTER_TYPE enumeration](..\wmiguid\ne-ntddk-_hardware_counter_type.md) | The HARDWARE_COUNTER_TYPE enumeration specifies the type of a hardware counter. |
| [_IMAGE_POLICY_ENTRY_TYPE enumeration](..\wmiguid\ne-wdm-_image_policy_entry_type.md) | This enumeration is not supported. |
| [_IMAGE_POLICY_ID enumeration](..\wmiguid\ne-wdm-_image_policy_id.md) | This enumeration is not supported. |
| [_INTERFACE_TYPE enumeration](..\wmiguid\ne-wdm-_interface_type.md) | The INTERFACE_TYPE enumeration indicates the bus type. |
| [_IO_ACCESS_MODE enumeration](..\wmiguid\ne-ntddsfio-_io_access_mode.md) | Defines the types of access mode for Scheduled File I/O (SFIO). |
| [_IO_ACCESS_MODE enumeration](..\wmiguid\ne-wdm-_io_access_mode.md) | Defines the types of access mode for Scheduled File I/O (SFIO). |
| [_IO_ACCESS_TYPE enumeration](..\wmiguid\ne-ntddsfio-_io_access_type.md) | Defines the access rights for Scheduled File I/O (SFIO). |
| [_IO_ACCESS_TYPE enumeration](..\wmiguid\ne-wdm-_io_access_type.md) | Defines the access rights for Scheduled File I/O (SFIO). |
| [_IO_ALLOCATION_ACTION enumeration](..\wmiguid\ne-wdm-_io_allocation_action.md) | The IO_ALLOCATION_ACTION enumerated type is used to specify return values for AdapterControl and ControllerControl routines. |
| [_IO_CONTAINER_INFORMATION_CLASS enumeration](..\wmiguid\ne-wdm-_io_container_information_class.md) | The IO_CONTAINER_INFORMATION_CLASS enumeration contains constants that indicate the classes of system information that a kernel-mode driver can request. |
| [_IO_CONTAINER_NOTIFICATION_CLASS enumeration](..\wmiguid\ne-wdm-_io_container_notification_class.md) | The IO_CONTAINER_NOTIFICATION_CLASS enumeration contains constants that indicate the classes of events for which a kernel-mode driver can register to receive notifications. |
| [_IO_PAGING_PRIORITY enumeration](..\wmiguid\ne-wdm-_io_paging_priority.md) | The IO_PAGING_PRIORITY enumeration describes the priority value for a paging I/O IRP. |
| [_IO_PRIORITY_HINT enumeration](..\wmiguid\ne-wdm-_io_priority_hint.md) | The IO_PRIORITY_HINT enumeration type specifies the priority hint for an IRP. |
| [_IO_SESSION_EVENT enumeration](..\wmiguid\ne-wdm-_io_session_event.md) | The IO_SESSION_EVENT enumeration indicates the type of session event for which a driver is receiving notification. |
| [_IO_SESSION_STATE enumeration](..\wmiguid\ne-wdm-_io_session_state.md) | The IO_SESSION_STATE enumeration contains constants that indicate the current state of a user session. |
| [_IRQ_DEVICE_POLICY enumeration](..\wmiguid\ne-wdm-_irq_device_policy.md) | The IRQ_DEVICE_POLICY enumeration type indicates the policy the operating system can use to assign the interrupts from a device to different processors. |
| [_IRQ_PRIORITY enumeration](..\wmiguid\ne-wdm-_irq_priority.md) | The IRQ_PRIORITY enumeration type indicates the priority the system should give to servicing a device's interrupts. |
| [_KBUGCHECK_CALLBACK_REASON enumeration](..\wmiguid\ne-wdm-_kbugcheck_callback_reason.md) | The KBUGCHECK_CALLBACK_REASON enumeration type specifies the situations in which a bug-check callback executes. |
| [_KBUGCHECK_DUMP_IO_TYPE enumeration](..\wmiguid\ne-wdm-_kbugcheck_dump_io_type.md) | The KBUGCHECK_DUMP_IO_TYPE enumeration type identifies the type of a section of data within a crash dump file. |
| [_KEY_INFORMATION_CLASS enumeration](..\wmiguid\ne-wdm-_key_information_class.md) | The KEY_INFORMATION_CLASS enumeration type represents the type of information to supply about a registry key. |
| [_KEY_SET_INFORMATION_CLASS enumeration](..\wmiguid\ne-wdm-_key_set_information_class.md) | The KEY_SET_INFORMATION_CLASS enumeration type represents the type of information to set for a registry key. |
| [_KEY_VALUE_INFORMATION_CLASS enumeration](..\wmiguid\ne-wdm-_key_value_information_class.md) | The KEY_VALUE_INFORMATION_CLASS enumeration type specifies the type of information to supply about the value of a registry key. |
| [_KINTERRUPT_MODE enumeration](..\wmiguid\ne-wdm-_kinterrupt_mode.md) | The KINTERRUPT_MODE enumeration type indicates whether an interrupt is level-triggered or edge-triggered. |
| [_KINTERRUPT_POLARITY enumeration](..\wmiguid\ne-wdm-_kinterrupt_polarity.md) | The KINTERRUPT_POLARITY enumeration indicates how a device signals an interrupt request on an interrupt line. |
| [_KTMOBJECT_TYPE enumeration](..\wmiguid\ne-wdm-_ktmobject_type.md) | The KTMOBJECT_TYPE enumeration identifies the types of objects that KTM supports. |
| [_MEMORY_CACHING_TYPE enumeration](..\wmiguid\ne-wdm-_memory_caching_type.md) | The MEMORY_CACHING_TYPE enumeration type specifies the permitted caching behavior when allocating or mapping memory. |
| [_MONITOR_DISPLAY_STATE enumeration](..\wmiguid\ne-ntpoapi-_monitor_display_state.md) | Indicates the power state of the monitor being displayed on. |
| [_MONITOR_DISPLAY_STATE enumeration](..\wmiguid\ne-wdm-_monitor_display_state.md) | Indicates the power state of the monitor being displayed on. |
| [_PEP_ACPI_OBJECT_TYPE enumeration](..\wmiguid\ne-pep_x-_pep_acpi_object_type.md) | The PEP_ACPI_OBJECT_TYPE enumeration indicates the type of ACPI object. |
| [_PEP_ACPI_OBJECT_TYPE enumeration](..\wmiguid\ne-pepfx-_pep_acpi_object_type.md) | The PEP_ACPI_OBJECT_TYPE enumeration indicates the type of ACPI object. |
| [_PEP_ACPI_RESOURCE_TYPE enumeration](..\wmiguid\ne-pep_x-_pep_acpi_resource_type.md) | The PEP_ACPI_RESOURCE_TYPE enumeration is used to identify the type of ACPI resource that is contained in the PEP_ACPI_RESOURCE union. |
| [_PEP_ACPI_RESOURCE_TYPE enumeration](..\wmiguid\ne-pepfx-_pep_acpi_resource_type.md) | The PEP_ACPI_RESOURCE_TYPE enumeration is used to identify the type of ACPI resource that is contained in the PEP_ACPI_RESOURCE union. |
| [_PEP_DEVICE_ACCEPTANCE_TYPE enumeration](..\wmiguid\ne-pep_x-_pep_device_acceptance_type.md) | The PEP_DEVICE_ACCEPTANCE_TYPE enumeration indicates whether a PEP accepts ownership of a device. |
| [_PEP_DEVICE_ACCEPTANCE_TYPE enumeration](..\wmiguid\ne-pepfx-_pep_device_acceptance_type.md) | The PEP_DEVICE_ACCEPTANCE_TYPE enumeration indicates whether a PEP accepts ownership of a device. |
| [_PEP_PERF_STATE_TYPE enumeration](..\wmiguid\ne-pep_x-_pep_perf_state_type.md) | The PEP_PERF_STATE_TYPE enumeration indicates the type of performance information that is specified for a performance state (P-state) of a component. |
| [_PEP_PERF_STATE_TYPE enumeration](..\wmiguid\ne-pepfx-_pep_perf_state_type.md) | The PEP_PERF_STATE_TYPE enumeration indicates the type of performance information that is specified for a performance state (P-state) of a component. |
| [_PEP_PERF_STATE_UNIT enumeration](..\wmiguid\ne-pep_x-_pep_perf_state_unit.md) | The PEP_PERF_STATE_UNIT enumeration indicates the measurement units in which the performance state (P-state) of a component is specified. |
| [_PEP_PERF_STATE_UNIT enumeration](..\wmiguid\ne-pepfx-_pep_perf_state_unit.md) | The PEP_PERF_STATE_UNIT enumeration indicates the measurement units in which the performance state (P-state) of a component is specified. |
| [_PEP_WORK_TYPE enumeration](..\wmiguid\ne-pep_x-_pep_work_type.md) | The PEP_WORK_TYPE enumeration describes the type of work that the platform extension plug-in (PEP) is requesting. |
| [_PEP_WORK_TYPE enumeration](..\wmiguid\ne-pepfx-_pep_work_type.md) | The PEP_WORK_TYPE enumeration describes the type of work that the platform extension plug-in (PEP) is requesting. |
| [_PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE enumeration](..\wmiguid\ne-ntddk-_physical_counter_resource_descriptor_type.md) | The PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE enumeration contains constants that indicate the type of hardware performance counter resource that is described by a PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structure. |
| [_POOL_TYPE enumeration](..\wmiguid\ne-wdm-_pool_type.md) | The POOL_TYPE enumeration type specifies the type of system memory to allocate. |
| [_POWER_REQUEST_TYPE enumeration](..\wmiguid\ne-ntpoapi-_power_request_type.md) | The POWER_REQUEST_TYPE enumeration indicates the power request type. |
| [_POWER_REQUEST_TYPE enumeration](..\wmiguid\ne-wdm-_power_request_type.md) | The POWER_REQUEST_TYPE enumeration indicates the power request type. |
| [_POWER_STATE_TYPE enumeration](..\wmiguid\ne-ntpoapi-_power_state_type.md) | The POWER_STATE_TYPE enumeration type indicates that a power state value is a system power state or a device power state. |
| [_POWER_STATE_TYPE enumeration](..\wmiguid\ne-wdm-_power_state_type.md) | The POWER_STATE_TYPE enumeration type indicates that a power state value is a system power state or a device power state. |
| [_PO_FX_PERF_STATE_TYPE enumeration](..\wmiguid\ne-wdm-_po_fx_perf_state_type.md) | The PO_FX_PERF_STATE_TYPE enumeration contains values that describe the type of performance states in a PO_FX_COMPONENT_PERF_SET. |
| [_PO_FX_PERF_STATE_UNIT enumeration](..\wmiguid\ne-wdm-_po_fx_perf_state_unit.md) | The PO_FX_PERF_STATE_UNIT enumeration contains values that describe the type of unit that is controlled by the performance states in a PO_FX_COMPONENT_PERF_SET. |
| [_PSCREATEPROCESSNOTIFYTYPE enumeration](..\wmiguid\ne-ntddk-_pscreateprocessnotifytype.md) | Indicates the type of process notification. This enumeration is used in PsSetCreateProcessNotifyRoutineEx2 to register callback notifications. |
| [_PSCREATETHREADNOTIFYTYPE enumeration](..\wmiguid\ne-ntddk-_pscreatethreadnotifytype.md) | Indicates the type of thread notification. This enumeration is used in PsSetCreateThreadNotifyRoutineEx to register callback notifications associated with thread creation or deletion. |
| [_REG_NOTIFY_CLASS enumeration](..\wmiguid\ne-wdm-_reg_notify_class.md) | The REG_NOTIFY_CLASS enumeration type specifies the type of registry operation that the configuration manager is passing to a RegistryCallback routine. |
| [_RESOURCEMANAGER_INFORMATION_CLASS enumeration](..\wmiguid\ne-wdm-_resourcemanager_information_class.md) | The RESOURCEMANAGER_INFORMATION_CLASS enumeration identifies the type of information that the ZwQueryInformationResourceManager routine can retrieve for a resource manager object. |
| [_SUBSYSTEM_INFORMATION_TYPE enumeration](..\wmiguid\ne-ntddk-_subsystem_information_type.md) | Indicates the type of subsystem for a process or thread. This enumeration is used in NtQueryInformationProcess and NtQueryInformationThread calls. |
| [_SYSTEM_POWER_STATE enumeration](..\wmiguid\ne-ntpoapi-_system_power_state.md) | The SYSTEM_POWER_STATE enumeration type is used to indicate a system power state. |
| [_SYSTEM_POWER_STATE enumeration](..\wmiguid\ne-wdm-_system_power_state.md) | The SYSTEM_POWER_STATE enumeration type is used to indicate a system power state. |
| [_TRACE_INFORMATION_CLASS enumeration](..\wmiguid\ne-wdm-_trace_information_class.md) | The TRACE_INFORMATION_CLASS enumeration type is used to indicate types of information associated with a WMI event tracing session. |
| [_TRANSACTIONMANAGER_INFORMATION_CLASS enumeration](..\wmiguid\ne-wdm-_transactionmanager_information_class.md) | The TRANSACTIONMANAGER_INFORMATION_CLASS enumeration specifies the type of information that the ZwQueryInformationTransactionManager routine can retrieve for a transaction manager object. |
| [_TRANSACTION_INFORMATION_CLASS enumeration](..\wmiguid\ne-wdm-_transaction_information_class.md) | The TRANSACTION_INFORMATION_CLASS enumeration specifies the type of information that ZwSetInformationTransaction can set and ZwQueryInformationTransaction can retrieve for a transaction manager object. |
| [_TRANSACTION_OUTCOME enumeration](..\wmiguid\ne-wdm-_transaction_outcome.md) | The TRANSACTION_OUTCOME enumeration defines the outcomes (results) that KTM can assign to a transaction. |
| [_TRANSACTION_STATE enumeration](..\wmiguid\ne-wdm-_transaction_state.md) | The TRANSACTION_STATE enumeration defines the states that KTM can assign to a transaction. |
| [_WORK_QUEUE_TYPE enumeration](..\wmiguid\ne-wdm-_work_queue_type.md) | The WORK_QUEUE_TYPE enumeration type indicates the type of system worker thread that handles a work item. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [ALLOCATE_FUNCTION_EX callback](..\wmiguid\nc-wdm-allocate_function_ex.md) | The LookasideListAllocateEx routine allocates the storage for a new lookaside-list entry when a client requests an entry from a lookaside list that is empty. |
| [BOUND_CALLBACK callback](..\wmiguid\nc-wdm-bound_callback.md) | The BoundCallback routine is executed whenever the system issues a bounds exception for a user-mode thread. |
| [DEVICE_ACTIVE_COOLING callback](..\wmiguid\nc-poclass-device_active_cooling.md) | The ActiveCooling callback routine engages or disengages a device's active-cooling function. |
| [DEVICE_PASSIVE_COOLING callback](..\wmiguid\nc-poclass-device_passive_cooling.md) | The PassiveCooling callback routine controls the degree to which the device must throttle its performance to meet cooling requirements. |
| [DRIVER_CONTROL callback](..\wmiguid\nc-wdm-driver_control.md) | This routine starts a DMA data-transfer or a data transfer operation. |
| [DRIVER_INITIALIZE callback](..\wmiguid\nc-wdm-driver_initialize.md) | DriverEntry is the first routine called after a driver is loaded, and is responsible for initializing the driver. |
| [DRIVER_LIST_CONTROL callback](..\wmiguid\nc-wdm-driver_list_control.md) | The AdapterListControl routine starts a direct memory access (DMA) scatter/gather operation. |
| [DRIVER_REINITIALIZE callback](..\wmiguid\nc-ntddk-driver_reinitialize.md) | The Reinitialize routine continues driver and device initialization after the driver's DriverEntry routine returns. |
| [EXPAND_STACK_CALLOUT callback](..\wmiguid\nc-ntddk-expand_stack_callout.md) | The ExpandedStackCall routine executes with a guaranteed stack size. |
| [EX_CALLBACK_FUNCTION callback](..\wmiguid\nc-wdm-ex_callback_function.md) | A filter driver's RegistryCallback routine can monitor, block, or modify a registry operation. |
| [FREE_FUNCTION_EX callback](..\wmiguid\nc-wdm-free_function_ex.md) | The LookasideListFreeEx routine frees the storage for a lookaside-list entry when a client tries to insert the entry into a lookaside list that is full. |
| [GET_D3COLD_CAPABILITY callback](..\wmiguid\nc-wdm-get_d3cold_capability.md) | The GetBusDriverD3ColdSupport routine enables the driver for a device to query whether the enumerating bus driver supports the D3cold device power state. |
| [GET_D3COLD_LAST_TRANSITION_STATUS callback](..\wmiguid\nc-wdm-get_d3cold_last_transition_status.md) | The GetLastTransitionStatus routine enables the driver for a device to query whether the most recent transition to the D3hot substate was followed by a transition to the D3cold substate. |
| [GET_DMA_ADAPTER callback](..\wmiguid\nc-wdm-get_dma_adapter.md) | The GetDmaAdapter routine returns a DMA_ADAPTER structure for the target device. |
| [GET_IDLE_WAKE_INFO callback](..\wmiguid\nc-wdm-get_idle_wake_info.md) | The GetIdleWakeInfo routine enables the driver for a device to discover the device power states from which the device can signal a wake event. |
| [GET_SDEV_IDENTIFIER callback](..\wmiguid\nc-wdm-get_sdev_identifier.md) | This material is not yet available. This placeholder topic is provided as an example of documentation that may be included in a later release. |
| [GET_SET_DEVICE_DATA callback](..\wmiguid\nc-wdm-get_set_device_data.md) | The GetBusData routine reads data from the device's configuration space. |
| [IO_COMPLETION_ROUTINE callback](..\wmiguid\nc-wdm-io_completion_routine.md) | The IoCompletion routine completes the processing of I/O operations. |
| [IO_CSQ_ACQUIRE_LOCK callback](..\wmiguid\nc-wdm-io_csq_acquire_lock.md) | The CsqAcquireLock routine is used by the system to acquire the lock for a driver-implemented, cancel-safe IRP queue. |
| [IO_CSQ_COMPLETE_CANCELED_IRP callback](..\wmiguid\nc-wdm-io_csq_complete_canceled_irp.md) | The CsqCompleteCanceledIrp routine is used by the system to signal to the driver that it can complete a canceled IRP. |
| [IO_CSQ_INSERT_IRP callback](..\wmiguid\nc-wdm-io_csq_insert_irp.md) | The CsqInsertIrp routine is used by the system to insert an IRP into a driver-implemented, cancel-safe IRP queue. |
| [IO_CSQ_INSERT_IRP_EX callback](..\wmiguid\nc-wdm-io_csq_insert_irp_ex.md) | The CsqInsertIrpEx routine is used by the system to insert an IRP into a driver-implemented, cancel-safe IRP queue. |
| [IO_CSQ_PEEK_NEXT_IRP callback](..\wmiguid\nc-wdm-io_csq_peek_next_irp.md) | The CsqPeekNextIrp routine is used by the system to find the next matching IRP in a driver-implemented, cancel-safe IRP queue. |
| [IO_CSQ_RELEASE_LOCK callback](..\wmiguid\nc-wdm-io_csq_release_lock.md) | The CsqReleaseLock routine is used by the system to release the lock that was acquired using CsqAcquireLock. |
| [IO_CSQ_REMOVE_IRP callback](..\wmiguid\nc-wdm-io_csq_remove_irp.md) | The CsqRemoveIrp routine is used by the system to remove the specified IRP from a driver-implemented, cancel-safe IRP queue. |
| [IO_SESSION_NOTIFICATION_FUNCTION callback](..\wmiguid\nc-wdm-io_session_notification_function.md) | The IO_SESSION_NOTIFICATION_FUNCTION function type defines a callback routine through which a driver receives notifications of changes in the state of user sessions that the driver is interested in. |
| [IO_TIMER_ROUTINE callback](..\wmiguid\nc-wdm-io_timer_routine.md) | The IoTimer routine is a DPC that, if registered, is called once per second. |
| [KBUGCHECK_CALLBACK_ROUTINE callback](..\wmiguid\nc-wdm-kbugcheck_callback_routine.md) | The BugCheckCallback routine is executed whenever the system issues a bug check. |
| [KBUGCHECK_REASON_CALLBACK_ROUTINE callback](..\wmiguid\nc-wdm-kbugcheck_reason_callback_routine.md) | Driver-implemented callback functions that the system executes when it issues a bug check. |
| [KIPI_BROADCAST_WORKER callback](..\wmiguid\nc-wdm-kipi_broadcast_worker.md) | The IpiGenericCall routine runs simultaneously on all processors. |
| [KMESSAGE_SERVICE_ROUTINE callback](..\wmiguid\nc-wdm-kmessage_service_routine.md) | An InterruptMessageService routine services a message-signaled interrupt. |
| [KSERVICE_ROUTINE callback](..\wmiguid\nc-wdm-kservice_routine.md) | The InterruptService routine (ISR) quickly services a device interrupt and schedules post-interrupt processing of received data, if necessary. |
| [KSTART_ROUTINE callback](..\wmiguid\nc-wdm-kstart_routine.md) | The ThreadStart routine provides an entry point for a driver-created system thread. |
| [KSYNCHRONIZE_ROUTINE callback](..\wmiguid\nc-wdm-ksynchronize_routine.md) | The SynchCritSection routine is used to access hardware resources or driver data that are shared with a driver's InterruptService routine. |
| [MM_MDL_ROUTINE callback](..\wmiguid\nc-wdm-mm_mdl_routine.md) | A driver-supplied callback routine that is invoked after a memory descriptor list (MDL) is mapped by calling the MmMapMdl function. |
| [PALLOCATE_ADAPTER_CHANNEL callback](..\wmiguid\nc-wdm-pallocate_adapter_channel.md) | The AllocateAdapterChannel routine prepares the system for a DMA operation on behalf of the target device object, and then calls the driver-supplied AdapterControl routine to carry out the DMA operation. |
| [PALLOCATE_ADAPTER_CHANNEL_EX callback](..\wmiguid\nc-wdm-pallocate_adapter_channel_ex.md) | The AllocateAdapterChannelEx routine allocates the resources that are needed to perform a DMA transfer, and then calls the driver-supplied AdapterControl routine to initiate the DMA transfer. |
| [PALLOCATE_COMMON_BUFFER callback](..\wmiguid\nc-wdm-pallocate_common_buffer.md) | The AllocateCommonBuffer routine allocates memory and maps it so that it is simultaneously accessible from both the processor and a device for DMA operations. |
| [PALLOCATE_COMMON_BUFFER_EX callback](..\wmiguid\nc-wdm-pallocate_common_buffer_ex.md) | The AllocateCommonBufferEx routine allocates memory for a common buffer and maps this memory so that it can be accessed both by the processor and by a device that performs DMA operations. |
| [PBUILD_MDL_FROM_SCATTER_GATHER_LIST callback](..\wmiguid\nc-wdm-pbuild_mdl_from_scatter_gather_list.md) | The BuildMdlFromScatterGatherList routine builds an MDL from a scatter/gather list allocated by the system.Note  This routine is reserved for system use. |
| [PBUILD_SCATTER_GATHER_LIST callback](..\wmiguid\nc-wdm-pbuild_scatter_gather_list.md) | The BuildScatterGatherList routine prepares the system for a DMA operation, using a driver-supplied buffer to build the scatter/gather list. |
| [PBUILD_SCATTER_GATHER_LIST_EX callback](..\wmiguid\nc-wdm-pbuild_scatter_gather_list_ex.md) | The BuildScatterGatherListEx routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls the driver-supplied AdapterListControl routine to initiate the DMA transfer. |
| [PCALCULATE_SCATTER_GATHER_LIST_SIZE callback](..\wmiguid\nc-wdm-pcalculate_scatter_gather_list_size.md) | The CalculateScatterGatherList routine calculates the size, in bytes, of scatter/gather list necessary to hold a given buffer. |
| [PCANCEL_ADAPTER_CHANNEL callback](..\wmiguid\nc-wdm-pcancel_adapter_channel.md) | The CancelAdapterChannel routine tries to cancel a pending request to allocate a DMA channel. |
| [PCANCEL_MAPPED_TRANSFER callback](..\wmiguid\nc-wdm-pcancel_mapped_transfer.md) | The CancelMappedTransfer routine cancels a system DMA transfer that is currently mapped to an adapter. |
| [PCI_MSIX_MASKUNMASK_ENTRY callback](..\wmiguid\nc-wdm-pci_msix_maskunmask_entry.md) | The MaskTableEntry routine masks an interrupt in the MSI-X hardware interrupt table. |
| [PCI_MSIX_SET_ENTRY callback](..\wmiguid\nc-wdm-pci_msix_set_entry.md) | The SetTableEntry routine sets the message ID for a table entry in the MSI-X hardware interrupt table. |
| [PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK callback](..\wmiguid\nc-wdm-pclfs_client_advance_tail_callback.md) | The ClfsAdvanceTailCallback function advances the base log sequence number (LSN) of the client's log. |
| [PCLFS_CLIENT_LFF_HANDLER_COMPLETE_CALLBACK callback](..\wmiguid\nc-wdm-pclfs_client_lff_handler_complete_callback.md) | The ClfsLogGrowthCompleteCallback function implements the actions that the client will take when space is freed in a log that had previously been full. |
| [PCLFS_CLIENT_LOG_UNPINNED_CALLBACK callback](..\wmiguid\nc-wdm-pclfs_client_log_unpinned_callback.md) | The ClfsLogUnpinnedCallback function implements any actions that the client will take when a log that had previously been pinned becomes unpinned. |
| [PCONFIGURE_ADAPTER_CHANNEL callback](..\wmiguid\nc-wdm-pconfigure_adapter_channel.md) | The ConfigureAdapterChannel routine invokes a custom function that is implemented by the DMA controller represented by an adapter object. |
| [PCREATE_PROCESS_NOTIFY_ROUTINE callback](..\wmiguid\nc-ntddk-pcreate_process_notify_routine.md) | Process-creation callback implemented by a driver to track the system-wide creation and deletion of processes against the driver's internal state. |
| [PCREATE_PROCESS_NOTIFY_ROUTINE_EX callback](..\wmiguid\nc-ntddk-pcreate_process_notify_routine_ex.md) | A callback routine implemented by a driver to notify the caller when a process is created or exits. |
| [PCREATE_THREAD_NOTIFY_ROUTINE callback](..\wmiguid\nc-ntddk-pcreate_thread_notify_routine.md) | A callback routine implemented by a driver to notify the caller when a thread is created or deleted. |
| [PDEVICE_RESET_HANDLER callback](..\wmiguid\nc-wdm-pdevice_reset_handler.md) | The DeviceReset routine is used to reset and recover a malfunctioning device. |
| [PEPCALLBACKNOTIFYACPI callback](..\wmiguid\nc-pep_x-pepcallbacknotifyacpi.md) | An AcceptAcpiNotification event callback routine handles ACPI notifications from the Windows power management framework (PoFx). |
| [PEPCALLBACKNOTIFYACPI callback](..\wmiguid\nc-pepfx-pepcallbacknotifyacpi.md) | An AcceptAcpiNotification event callback routine handles ACPI notifications from the Windows power management framework (PoFx). |
| [PEPCALLBACKNOTIFYDPM callback](..\wmiguid\nc-pep_x-pepcallbacknotifydpm.md) | An AcceptDeviceNotification event callback routine handles device power management (DPM) notifications from the Windows power management framework (PoFx). |
| [PEPCALLBACKNOTIFYDPM callback](..\wmiguid\nc-pepfx-pepcallbacknotifydpm.md) | An AcceptDeviceNotification event callback routine handles device power management (DPM) notifications from the Windows power management framework (PoFx). |
| [PEPCALLBACKNOTIFYPPM callback](..\wmiguid\nc-pep_x-pepcallbacknotifyppm.md) | An AcceptProcessorNotification event callback routine handles processor power management (PPM) notifications from the Windows power management framework (PoFx). |
| [PEPCALLBACKNOTIFYPPM callback](..\wmiguid\nc-pepfx-pepcallbacknotifyppm.md) | An AcceptProcessorNotification event callback routine handles processor power management (PPM) notifications from the Windows power management framework (PoFx). |
| [PEPCALLBACKPOWERONCRASHDUMPDEVICE callback](..\wmiguid\nc-pep_x-pepcallbackpoweroncrashdumpdevice.md) | The PowerOnDumpDeviceCallback callback routine turns on the crash-dump device. |
| [PEPCALLBACKPOWERONCRASHDUMPDEVICE callback](..\wmiguid\nc-pepfx-pepcallbackpoweroncrashdumpdevice.md) | The PowerOnDumpDeviceCallback callback routine turns on the crash-dump device. |
| [PFLUSH_ADAPTER_BUFFERS callback](..\wmiguid\nc-wdm-pflush_adapter_buffers.md) | The FlushAdapterBuffers routine flushes any data remaining in the system DMA controller's internal cache or in a bus-master adapter's internal cache at the end of a DMA transfer operation. |
| [PFLUSH_ADAPTER_BUFFERS_EX callback](..\wmiguid\nc-wdm-pflush_adapter_buffers_ex.md) | The FlushAdapterBuffersEx routine flushes any data that remains in the data cache at the end of a DMA transfer operation performed by a system DMA controller or bus-master device. |
| [PFREE_ADAPTER_CHANNEL callback](..\wmiguid\nc-wdm-pfree_adapter_channel.md) | The FreeAdapterChannel routine releases the system DMA controller when a driver has completed all DMA operations necessary to satisfy the current IRP. |
| [PFREE_ADAPTER_OBJECT callback](..\wmiguid\nc-wdm-pfree_adapter_object.md) | The FreeAdapterObject routine releases the specified adapter object after a driver has completed all DMA operations. |
| [PFREE_COMMON_BUFFER callback](..\wmiguid\nc-wdm-pfree_common_buffer.md) | The FreeCommonBuffer routine frees a common buffer allocated by AllocateCommonBuffer, along with all resources the buffer uses. |
| [PFREE_MAP_REGISTERS callback](..\wmiguid\nc-wdm-pfree_map_registers.md) | The FreeMapRegisters routine releases a set of map registers that were saved from a call to AllocateAdapterChannel. |
| [PGET_DMA_ADAPTER_INFO callback](..\wmiguid\nc-wdm-pget_dma_adapter_info.md) | The GetDmaAdapterInfo routine retrieves information about the hardware capabilities of a system DMA channel. |
| [PGET_DMA_ALIGNMENT callback](..\wmiguid\nc-wdm-pget_dma_alignment.md) | The GetDmaAlignment routine returns the alignment requirements of the DMA system. |
| [PGET_DMA_TRANSFER_INFO callback](..\wmiguid\nc-wdm-pget_dma_transfer_info.md) | The GetDmaTransferInfo routine calculates the allocation requirements for a scatter/gather DMA transfer. |
| [PGET_LOCATION_STRING callback](..\wmiguid\nc-ntddk-pget_location_string.md) | The PnpGetLocationString routine provides the device-specific part of the device's SPDRP_LOCATION_PATHS property. |
| [PGET_SCATTER_GATHER_LIST callback](..\wmiguid\nc-wdm-pget_scatter_gather_list.md) | The GetScatterGatherList routine prepares the system for a DMA scatter/gather operation on behalf of the target device object, through either the system DMA controller or a bus-master adapter. |
| [PGET_SCATTER_GATHER_LIST_EX callback](..\wmiguid\nc-wdm-pget_scatter_gather_list_ex.md) | The GetScatterGatherListEx routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls the driver-supplied AdapterListControl routine to initiate the DMA transfer. |
| [PINITIALIZE_DMA_TRANSFER_CONTEXT callback](..\wmiguid\nc-wdm-pinitialize_dma_transfer_context.md) | The InitializeDmaTransferContext routine initializes an opaque DMA transfer context that is used to track pending allocations of DMA resources. |
| [PINTERFACE_DEREFERENCE callback](..\wmiguid\nc-wdm-pinterface_dereference.md) | The InterfaceDereference routine decrements the reference count on a driver-defined interface. |
| [PINTERFACE_REFERENCE callback](..\wmiguid\nc-wdm-pinterface_reference.md) | The InterfaceReference routine increments the reference count on a driver-defined interface. |
| [PLOAD_IMAGE_NOTIFY_ROUTINE callback](..\wmiguid\nc-ntddk-pload_image_notify_routine.md) | Called by the operating system to notify the driver when a driver image or a user image (for example, a DLL or EXE) is mapped into virtual memory. |
| [PMAP_TRANSFER callback](..\wmiguid\nc-wdm-pmap_transfer.md) | The MapTransfer routine sets up map registers for an adapter object to map a DMA transfer from a locked-down buffer. |
| [PMAP_TRANSFER_EX callback](..\wmiguid\nc-wdm-pmap_transfer_ex.md) | The MapTransferEx routine sets up map registers to map the physical addresses in a scatter/gather list to the logical addresses that are required to do a DMA transfer. |
| [POB_POST_OPERATION_CALLBACK callback](..\wmiguid\nc-wdm-pob_post_operation_callback.md) | The ObjectPostCallback routine is called by the operating system after a process or thread handle operation occurs. |
| [POB_PRE_OPERATION_CALLBACK callback](..\wmiguid\nc-wdm-pob_pre_operation_callback.md) | The ObjectPreCallback routine is called by the operating system when a process or thread handle operation occurs. |
| [POFXCALLBACKCRITICALRESOURCE callback](..\wmiguid\nc-pep_x-pofxcallbackcriticalresource.md) | The TransitionCriticalResource routine changes the active/inactive state of a core system component. |
| [POFXCALLBACKCRITICALRESOURCE callback](..\wmiguid\nc-pepfx-pofxcallbackcriticalresource.md) | The TransitionCriticalResource routine changes the active/inactive state of a core system component. |
| [POFXCALLBACKENUMERATEUNMASKEDINTERRUPTS callback](..\wmiguid\nc-pep_x-pofxcallbackenumerateunmaskedinterrupts.md) | The EnumerateUnmaskedInterrupts routine enumerates interrupt sources whose interrupts are unmasked and enabled. |
| [POFXCALLBACKENUMERATEUNMASKEDINTERRUPTS callback](..\wmiguid\nc-pepfx-pofxcallbackenumerateunmaskedinterrupts.md) | The EnumerateUnmaskedInterrupts routine enumerates interrupt sources whose interrupts are unmasked and enabled. |
| [POFXCALLBACKPLATFORMIDLEVETO callback](..\wmiguid\nc-pep_x-pofxcallbackplatformidleveto.md) | The PlatformIdleVeto routine increments or decrements the veto count for a veto code for a platform idle state. |
| [POFXCALLBACKPLATFORMIDLEVETO callback](..\wmiguid\nc-pepfx-pofxcallbackplatformidleveto.md) | The PlatformIdleVeto routine increments or decrements the veto count for a veto code for a platform idle state. |
| [POFXCALLBACKPROCESSORHALT callback](..\wmiguid\nc-pep_x-pofxcallbackprocessorhalt.md) | The ProcessorHalt routine prepares the processor to be halted. |
| [POFXCALLBACKPROCESSORHALT callback](..\wmiguid\nc-pepfx-pofxcallbackprocessorhalt.md) | The ProcessorHalt routine prepares the processor to be halted. |
| [POFXCALLBACKPROCESSORIDLEVETO callback](..\wmiguid\nc-pep_x-pofxcallbackprocessoridleveto.md) | The ProcessorIdleVeto routine increments or decrements the veto count for a veto code for a processor idle state. |
| [POFXCALLBACKPROCESSORIDLEVETO callback](..\wmiguid\nc-pepfx-pofxcallbackprocessoridleveto.md) | The ProcessorIdleVeto routine increments or decrements the veto count for a veto code for a processor idle state. |
| [POFXCALLBACKREQUESTCOMMON callback](..\wmiguid\nc-pep_x-pofxcallbackrequestcommon.md) | The RequestCommon routine is a generic request handler. |
| [POFXCALLBACKREQUESTCOMMON callback](..\wmiguid\nc-pepfx-pofxcallbackrequestcommon.md) | The RequestCommon routine is a generic request handler. |
| [POFXCALLBACKREQUESTINTERRUPT callback](..\wmiguid\nc-pep_x-pofxcallbackrequestinterrupt.md) | The RequestInterrupt routine requests that the operating system replay an edge-triggered interrupt that might have been lost while the hardware platform was in a low-power state. |
| [POFXCALLBACKREQUESTINTERRUPT callback](..\wmiguid\nc-pepfx-pofxcallbackrequestinterrupt.md) | The RequestInterrupt routine requests that the operating system replay an edge-triggered interrupt that might have been lost while the hardware platform was in a low-power state. |
| [POFXCALLBACKREQUESTWORKER callback](..\wmiguid\nc-pep_x-pofxcallbackrequestworker.md) | The RequestWorker routine is called by a platform extension plug-in (PEP) to inform the Windows power management framework (PoFx) that the platform extension plug-in (PEP) has a work request to submit on behalf of the specified device. |
| [POFXCALLBACKREQUESTWORKER callback](..\wmiguid\nc-pepfx-pofxcallbackrequestworker.md) | The RequestWorker routine is called by a platform extension plug-in (PEP) to inform the Windows power management framework (PoFx) that the platform extension plug-in (PEP) has a work request to submit on behalf of the specified device. |
| [POFXCALLBACKUPDATEPLATFORMIDLESTATE callback](..\wmiguid\nc-pep_x-pofxcallbackupdateplatformidlestate.md) | The UpdatePlatformIdleState routine is called by the platform extension plug-in (PEP) to update the properties of the specified platform idle state. |
| [POFXCALLBACKUPDATEPLATFORMIDLESTATE callback](..\wmiguid\nc-pepfx-pofxcallbackupdateplatformidlestate.md) | The UpdatePlatformIdleState routine is called by the platform extension plug-in (PEP) to update the properties of the specified platform idle state. |
| [POFXCALLBACKUPDATEPROCESSORIDLESTATE callback](..\wmiguid\nc-pep_x-pofxcallbackupdateprocessoridlestate.md) | The UpdateProcessorIdleState routine is called by the platform extension plug-in (PEP) to update the properties of the specified processor idle state. |
| [POFXCALLBACKUPDATEPROCESSORIDLESTATE callback](..\wmiguid\nc-pepfx-pofxcallbackupdateprocessoridlestate.md) | The UpdateProcessorIdleState routine is called by the platform extension plug-in (PEP) to update the properties of the specified processor idle state. |
| [PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK callback](..\wmiguid\nc-wdm-po_fx_component_active_condition_callback.md) | The ComponentActiveConditionCallback callback routine notifies the driver that the specified component completed a transition from the idle condition to the active condition. |
| [PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK callback](..\wmiguid\nc-wdm-po_fx_component_critical_transition_callback.md) | The ComponentCriticalTransitionCallback callback routine handles a transition of the specified component between the F0 (fully on) and low-power Fx component power states. |
| [PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK callback](..\wmiguid\nc-wdm-po_fx_component_idle_condition_callback.md) | The ComponentIdleConditionCallback callback routine notifies the driver that the specified component completed a transition from the active condition to the idle condition. |
| [PO_FX_COMPONENT_IDLE_STATE_CALLBACK callback](..\wmiguid\nc-wdm-po_fx_component_idle_state_callback.md) | The ComponentIdleStateCallback callback routine notifies the driver of a pending change to the Fx power state of the specified component. |
| [PO_FX_COMPONENT_PERF_STATE_CALLBACK callback](..\wmiguid\nc-wdm-po_fx_component_perf_state_callback.md) | The ComponentPerfStateCallback callback routine notifies the driver that its request to change the performance state of a component is complete. |
| [PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK callback](..\wmiguid\nc-wdm-po_fx_device_power_not_required_callback.md) | The DevicePowerNotRequiredCallback callback routine notifies the device driver that the device is not required to stay in the D0 power state. |
| [PO_FX_DEVICE_POWER_REQUIRED_CALLBACK callback](..\wmiguid\nc-wdm-po_fx_device_power_required_callback.md) | The DevicePowerRequiredCallback callback routine notifies the device driver that the device must enter and remain in the D0 power state. |
| [PO_FX_POWER_CONTROL_CALLBACK callback](..\wmiguid\nc-wdm-po_fx_power_control_callback.md) | The PowerControlCallback callback routine performs a power control operation that is requested by the power management framework (PoFx). |
| [PPO_ENUMERATE_INTERRUPT_SOURCE_CALLBACK callback](..\wmiguid\nc-pep_x-ppo_enumerate_interrupt_source_callback.md) | An EnumerateInterruptSource callback routine supplies a platform extension plug-in (PEP) with information about an interrupt source. |
| [PPO_ENUMERATE_INTERRUPT_SOURCE_CALLBACK callback](..\wmiguid\nc-pepfx-ppo_enumerate_interrupt_source_callback.md) | An EnumerateInterruptSource callback routine supplies a platform extension plug-in (PEP) with information about an interrupt source. |
| [PPUT_DMA_ADAPTER callback](..\wmiguid\nc-wdm-pput_dma_adapter.md) | The PutDmaAdapter routine frees a DMA_ADAPTER structure previously allocated by IoGetDmaAdapter. |
| [PPUT_SCATTER_GATHER_LIST callback](..\wmiguid\nc-wdm-pput_scatter_gather_list.md) | The PutScatterGatherList routine frees the previously allocated map registers and scatter/gather list used in scatter/gather DMA. |
| [PREAD_DMA_COUNTER callback](..\wmiguid\nc-wdm-pread_dma_counter.md) | The ReadDmaCounter routine returns the number of bytes remaining to be transferred during the current subordinate DMA operation. |
| [PREENUMERATE_SELF callback](..\wmiguid\nc-wdm-preenumerate_self.md) | A ReenumerateSelf routine requests that a bus driver reenumerate a child device. |
| [PROCESSOR_HALT_ROUTINE callback](..\wmiguid\nc-wdm-processor_halt_routine.md) | A Halt callback routine transitions the processor to an idle state. |
| [PTM_RM_NOTIFICATION callback](..\wmiguid\nc-wdm-ptm_rm_notification.md) | A resource manager's ResourceManagerNotification callback routine receives and handles transaction notifications. |
| [REQUEST_POWER_COMPLETE callback](..\wmiguid\nc-wdm-request_power_complete.md) | The PowerCompletion callback routine completes the processing of a power IRP. |
| [RTL_QUERY_REGISTRY_ROUTINE callback](..\wmiguid\nc-wdm-rtl_query_registry_routine.md) | The QueryRoutine routine provides information about a registry value that was requested in a preceding call to the RtlQueryRegistryValues routine. |
| [RTL_RUN_ONCE_INIT_FN callback](..\wmiguid\nc-ntddk-rtl_run_once_init_fn.md) | The RunOnceInitialization routine performs a one-time initialization operation. |
| [SET_D3COLD_SUPPORT callback](..\wmiguid\nc-wdm-set_d3cold_support.md) | The SetD3ColdSupport routine enables or disables transitions to the D3cold device power state. |
| [SILO_CONTEXT_CLEANUP_CALLBACK callback](..\wmiguid\nc-ntddk-silo_context_cleanup_callback.md) | This callback is invoked when the context object reaches a reference count of zero. |
| [SILO_MONITOR_CREATE_CALLBACK callback](..\wmiguid\nc-ntddk-silo_monitor_create_callback.md) | This is callback is invoked when a new silo is created. |
| [SILO_MONITOR_TERMINATE_CALLBACK callback](..\wmiguid\nc-ntddk-silo_monitor_terminate_callback.md) | This callback is invoked when a silo is terminated. |
| [TRANSLATE_BUS_ADDRESS callback](..\wmiguid\nc-wdm-translate_bus_address.md) | The TranslateBusAddress routine translates addresses on the parent bus to logical addresses. |
| [WMI_EXECUTE_METHOD_CALLBACK callback](..\wmiguid\nc-wmilib-wmi_execute_method_callback.md) | The DpWmiExecuteMethod routine executes a method associated with a data block. This routine is optional. |
| [WMI_FUNCTION_CONTROL_CALLBACK callback](..\wmiguid\nc-wmilib-wmi_function_control_callback.md) | The DpWmiFunctionControl routine enables or disables notification of events, and enables or disables data collection for data blocks that the driver registered as expensive to collect. This routine is optional. |
| [WMI_QUERY_DATABLOCK_CALLBACK callback](..\wmiguid\nc-wmilib-wmi_query_datablock_callback.md) | The DpWmiQueryDataBlock routine returns either a single instance or all instances of a data block. This routine is required. |
| [WMI_QUERY_REGINFO_CALLBACK callback](..\wmiguid\nc-wmilib-wmi_query_reginfo_callback.md) | The DpWmiQueryReginfo routine provides information about the data blocks and event blocks to be registered by a driver. This routine is required. |
| [WMI_SET_DATABLOCK_CALLBACK callback](..\wmiguid\nc-wmilib-wmi_set_datablock_callback.md) | The DpWmiSetDataBlock routine changes all data items in a single instance of a data block. This routine is optional. |
| [WMI_SET_DATAITEM_CALLBACK callback](..\wmiguid\nc-wmilib-wmi_set_dataitem_callback.md) | The DpWmiSetDataItem routine changes a single data item in an instance of a data block. This routine is optional. |
| [pHalExamineMBR callback](..\wmiguid\nc-ntddk-phalexaminembr.md) | The HalExamineMBR routine reads the master boot record (MBR) of a disk and returns data from the MBR if the MBR is of the type specified by the caller. |

## Functions

| Title   | Description   |
| ---- |:---- |
| [AppendTailList function](..\wmiguid\nf-wdm-appendtaillist.md) | The AppendTailList routine appends a doubly linked list of LIST_ENTRY structures to the tail of another doubly linked list of LIST_ENTRY structures. |
| [AuxKlibEnumerateSystemFirmwareTables function](..\wmiguid\nf-aux_klib-auxklibenumeratesystemfirmwaretables.md) | The AuxKlibEnumerateSystemFirmwareTables routine enumerates all system firmware tables of the specified type. |
| [AuxKlibGetBugCheckData function](..\wmiguid\nf-aux_klib-auxklibgetbugcheckdata.md) | The AuxKlibGetBugCheckData routine retrieves information about a bug check that has just occurred. |
| [AuxKlibGetImageExportDirectory function](..\wmiguid\nf-aux_klib-auxklibgetimageexportdirectory.md) | The AuxKlibGetImageExportDirectory routine returns an image module's export directory. |
| [AuxKlibGetSystemFirmwareTable function](..\wmiguid\nf-aux_klib-auxklibgetsystemfirmwaretable.md) | The AuxKlibGetSystemFirmwareTable routine retrieves the specified firmware table from the firmware table provider. |
| [AuxKlibInitialize function](..\wmiguid\nf-aux_klib-auxklibinitialize.md) | The AuxKlibInitialize routine initializes the Auxiliary Kernel-Mode Library. |
| [AuxKlibQueryModuleInformation function](..\wmiguid\nf-aux_klib-auxklibquerymoduleinformation.md) | The AuxKlibQueryModuleInformation routine retrieves information about the image modules that the operating system has loaded. |
| [ClfsAddLogContainer function](..\wmiguid\nf-wdm-clfsaddlogcontainer.md) | The ClfsAddLogContainer routine adds a container to a CLFS log. |
| [ClfsAddLogContainerSet function](..\wmiguid\nf-wdm-clfsaddlogcontainerset.md) | The ClfsAddLogContainerSet routine atomically adds a set of containers to a CLFS log. |
| [ClfsAdvanceLogBase function](..\wmiguid\nf-wdm-clfsadvancelogbase.md) | The ClfsAdvanceLogBase routine sets the base LSN of a CLFS stream. |
| [ClfsAlignReservedLog function](..\wmiguid\nf-wdm-clfsalignreservedlog.md) | The ClfsAlignReservedLog routine calculates the size of the space that must be reserved for a specified set of records. The size calculation includes the space required for headers and the space required for sector alignment. |
| [ClfsAllocReservedLog function](..\wmiguid\nf-wdm-clfsallocreservedlog.md) | The ClfsAllocReservedLog routine reserves space in a marshalling area for a set of records. |
| [ClfsCloseAndResetLogFile function](..\wmiguid\nf-wdm-clfscloseandresetlogfile.md) | The ClfsCloseAndResetLogFile routine releases all references to a specified log file object and marks its associated stream for reset. |
| [ClfsCloseLogFileObject function](..\wmiguid\nf-wdm-clfscloselogfileobject.md) | The ClfsCloseLogFileObject routine releases all references to a log file object. |
| [ClfsCreateLogFile function](..\wmiguid\nf-wdm-clfscreatelogfile.md) | The ClfsCreateLogFile routine creates or opens a CLFS stream. If necessary, ClfsCreateLogFile also creates the underlying physical log that holds the stream's records. |
| [ClfsCreateMarshallingArea function](..\wmiguid\nf-wdm-clfscreatemarshallingarea.md) | The ClfsCreateMarshallingArea routine creates a marshalling area for a CLFS stream and returns a pointer to an opaque context that represents the new marshalling area. |
| [ClfsCreateScanContext function](..\wmiguid\nf-wdm-clfscreatescancontext.md) | The ClfsCreateScanContext routine creates a scan context that can be used to iterate over the containers of a specified CLFS log. |
| [ClfsDeleteLogByPointer function](..\wmiguid\nf-wdm-clfsdeletelogbypointer.md) | The ClfsDeleteLogByPointer routine marks a CLFS stream for deletion. |
| [ClfsDeleteLogFile function](..\wmiguid\nf-wdm-clfsdeletelogfile.md) | The ClfsDeleteLogFile routine marks a CLFS stream for deletion. |
| [ClfsDeleteMarshallingArea function](..\wmiguid\nf-wdm-clfsdeletemarshallingarea.md) | The ClfsDeleteMarshallingArea routine deletes a marshalling area. |
| [ClfsFlushBuffers function](..\wmiguid\nf-wdm-clfsflushbuffers.md) | The ClfsFlushBuffers routine forces all log I/O blocks in a specified marshalling area to stable storage. |
| [ClfsFlushToLsn function](..\wmiguid\nf-wdm-clfsflushtolsn.md) | The ClfsFlushToLsn routine forces, to stable storage, all records that have an LSN less than or equal to a specified LSN. |
| [ClfsGetContainerName function](..\wmiguid\nf-wdm-clfsgetcontainername.md) | The ClfsGetContainerName routine returns the path name of a specified container. |
| [ClfsGetIoStatistics function](..\wmiguid\nf-wdm-clfsgetiostatistics.md) | The ClfsGetIoStatistics routine returns I/O statistics for a specified CLFS log. |
| [ClfsLsnBlockOffset function](..\wmiguid\nf-wdm-clfslsnblockoffset.md) | The ClfsLsnBlockOffset routine returns the sector-aligned block offset contained in a specified LSN. |
| [ClfsLsnContainer function](..\wmiguid\nf-wdm-clfslsncontainer.md) | The ClfsLsnContainer routine returns the logical container identifier contained in a specified LSN. |
| [ClfsLsnCreate function](..\wmiguid\nf-wdm-clfslsncreate.md) | The ClfsLsnCreate routine creates a log sequence number (LSN), given a container identifier, a block offset, and a record sequence number. |
| [ClfsLsnEqual function](..\wmiguid\nf-wdm-clfslsnequal.md) | The ClfsLsnEqual routine determines whether two LSNs from the same stream are equal. |
| [ClfsLsnGreater function](..\wmiguid\nf-wdm-clfslsngreater.md) | The ClfsLsnGreater routine determines whether one LSN is greater than another LSN. The two LSNs must be from the same stream. |
| [ClfsLsnLess function](..\wmiguid\nf-wdm-clfslsnless.md) | The ClfsLsnLess routine determines whether one LSN is less than another LSN. The two LSNs must be from the same stream. |
| [ClfsLsnNull function](..\wmiguid\nf-wdm-clfslsnnull.md) | The ClfsLsnNull routine determines whether a specified LSN is equal to the smallest possible LSN, CLFS_LSN_NULL. |
| [ClfsLsnRecordSequence function](..\wmiguid\nf-wdm-clfslsnrecordsequence.md) | The ClfsLsnRecordSequence routine returns the record sequence number contained in a specified LSN. |
| [ClfsMgmtDeregisterManagedClient function](..\wmiguid\nf-wdm-clfsmgmtderegistermanagedclient.md) | The ClfsMgmtDeregisterManagedClient routine removes the connection between a client and a log, so that the client no longer manages the log. |
| [ClfsMgmtHandleLogFileFull function](..\wmiguid\nf-wdm-clfsmgmthandlelogfilefull.md) | The ClfsMgmtHandleLogFileFull routine attempts to make more space available in a log. It might make more space available by adding containers to the log, or it might ask clients to move their log tails. |
| [ClfsMgmtInstallPolicy function](..\wmiguid\nf-wdm-clfsmgmtinstallpolicy.md) | The ClfsMgmtInstallPolicy routine adds a CLFS_MGMT_POLICY structure to a physical log. |
| [ClfsMgmtQueryPolicy function](..\wmiguid\nf-wdm-clfsmgmtquerypolicy.md) | The ClfsMgmtQueryPolicy routine retrieves a specific CLFS_MGMT_POLICY structure for a log. |
| [ClfsMgmtRegisterManagedClient function](..\wmiguid\nf-wdm-clfsmgmtregistermanagedclient.md) | The ClfsMgmtRegisterManagedClient routine creates a client that will manage a CLFS log. |
| [ClfsMgmtRemovePolicy function](..\wmiguid\nf-wdm-clfsmgmtremovepolicy.md) | The ClfsMgmtRemovePolicy routine resets a log's CLFS_MGMT_POLICY structure to its default value. |
| [ClfsMgmtSetLogFileSize function](..\wmiguid\nf-wdm-clfsmgmtsetlogfilesize.md) | The ClfsMgmtSetLogFileSize routine adds containers to a log or deletes containers from a log. |
| [ClfsMgmtSetLogFileSizeAsClient function](..\wmiguid\nf-wdm-clfsmgmtsetlogfilesizeasclient.md) | The ClfsMgmtSetLogFileSizeAsClient routine sets the log file size by adding containers to a client log or deleting containers from a client log. |
| [ClfsMgmtTailAdvanceFailure function](..\wmiguid\nf-wdm-clfsmgmttailadvancefailure.md) | The ClfsMgmtTailAdvanceFailure routine notifies CLFS management that the client could not advance the log's tail. |
| [ClfsQueryLogFileInformation function](..\wmiguid\nf-wdm-clfsquerylogfileinformation.md) | The ClfsQueryLogFileInformation routine returns metadata and state information for a specified CLFS stream or its underlying physical log or both. |
| [ClfsReadLogRecord function](..\wmiguid\nf-wdm-clfsreadlogrecord.md) | The ClfsReadLogRecord routine reads a target record in a CLFS stream and returns a read context that the caller can use to read the records preceding or following it in the stream. |
| [ClfsReadNextLogRecord function](..\wmiguid\nf-wdm-clfsreadnextlogrecord.md) | The ClfsReadNextLogRecord routine reads the next record in a sequence, relative to the current record in a read context. |
| [ClfsReadPreviousRestartArea function](..\wmiguid\nf-wdm-clfsreadpreviousrestartarea.md) | The ClfsReadPreviousRestartArea routine reads the previous restart record relative to the current record in a read context. |
| [ClfsReadRestartArea function](..\wmiguid\nf-wdm-clfsreadrestartarea.md) | The ClfsReadRestartArea routine reads the restart record that was most recently written to a specified CLFS stream. |
| [ClfsRemoveLogContainer function](..\wmiguid\nf-wdm-clfsremovelogcontainer.md) | The ClfsRemoveLogContainer routine removes a container from a CLFS log. |
| [ClfsRemoveLogContainerSet function](..\wmiguid\nf-wdm-clfsremovelogcontainerset.md) | The ClfsRemoveLogContainerSet routine atomically removes a set of containers from a CLFS log. |
| [ClfsReserveAndAppendLog function](..\wmiguid\nf-wdm-clfsreserveandappendlog.md) | The ClfsReserveAndAppendLog routine reserves space in a marshalling area or appends a record to a marshalling area or does both atomically. |
| [ClfsReserveAndAppendLogAligned function](..\wmiguid\nf-wdm-clfsreserveandappendlogaligned.md) | The ClfsReserveAndAppendLogAligned routine reserves space in a marshalling area or appends a record to a marshalling area or does both atomically. The record's data is aligned on specified boundaries. |
| [ClfsScanLogContainers function](..\wmiguid\nf-wdm-clfsscanlogcontainers.md) | The ClfsScanLogContainers routine retrieves descriptive information for a sequence of containers that belong to a particular CLFS log. |
| [ClfsSetArchiveTail function](..\wmiguid\nf-wdm-clfssetarchivetail.md) | The ClfsSetArchiveTail routine sets the archive tail of a CLFS log to a specified LSN. |
| [ClfsSetEndOfLog function](..\wmiguid\nf-wdm-clfssetendoflog.md) | The ClfsSetEndOfLog routine truncates a CLFS stream. |
| [ClfsSetLogFileInformation function](..\wmiguid\nf-wdm-clfssetlogfileinformation.md) | The ClfsSetLogFileInformation routine sets metadata and state information for a specified stream and its underlying physical log. |
| [ClfsTerminateReadLog function](..\wmiguid\nf-wdm-clfsterminatereadlog.md) | The ClfsTerminateReadLog routine invalidates a specified read context after freeing resources associated with the context. |
| [ClfsWriteRestartArea function](..\wmiguid\nf-wdm-clfswriterestartarea.md) | The ClfsWriteRestartArea routine atomically appends a new restart record to a CLFS stream, flushes the restart record to stable storage, and optionally updates the base LSN of the stream. |
| [CmCallbackGetKeyObjectID function](..\wmiguid\nf-wdm-cmcallbackgetkeyobjectid.md) | The CmCallbackGetKeyObjectID routine retrieves the unique identifier and object name that are associated with a specified registry key object. |
| [CmCallbackGetKeyObjectIDEx function](..\wmiguid\nf-wdm-cmcallbackgetkeyobjectidex.md) | The CmCallbackGetKeyObjectIDEx routine retrieves the unique identifier and object name that are associated with a specified registry key object. |
| [CmCallbackReleaseKeyObjectIDEx function](..\wmiguid\nf-wdm-cmcallbackreleasekeyobjectidex.md) | The CmCallbackReleaseKeyObjectIDEx routine frees an object name string obtained from the CmCallbackGetKeyObjectIDEx routine. |
| [CmGetBoundTransaction function](..\wmiguid\nf-wdm-cmgetboundtransaction.md) | The CmGetBoundTransaction routine returns a pointer to the transaction object that represents the transaction, if any, that is associated with a specified registry key object. |
| [CmGetCallbackVersion function](..\wmiguid\nf-wdm-cmgetcallbackversion.md) | The CmGetCallbackVersion routine retrieves the major and minor version numbers for the current version of the configuration manager's registry callback feature. |
| [CmRegisterCallback function](..\wmiguid\nf-wdm-cmregistercallback.md) | The CmRegisterCallback routine is obsolete for Windows Vista and later operating system versions. Use CmRegisterCallbackEx instead.The CmRegisterCallback routine registers a RegistryCallback routine. |
| [CmRegisterCallbackEx function](..\wmiguid\nf-wdm-cmregistercallbackex.md) | The CmRegisterCallbackEx routine registers a RegistryCallback routine. |
| [CmSetCallbackObjectContext function](..\wmiguid\nf-wdm-cmsetcallbackobjectcontext.md) | The CmSetCallbackObjectContext routine associates specified context information with a specified registry object. |
| [CmUnRegisterCallback function](..\wmiguid\nf-wdm-cmunregistercallback.md) | The CmUnRegisterCallback routine unregisters a RegistryCallback routine that a CmRegisterCallback or CmRegisterCallbackEx routine previously registered. |
| [ExAcquireResourceExclusiveLite function](..\wmiguid\nf-wdm-exacquireresourceexclusivelite.md) | The ExAcquireResourceExclusiveLite routine acquires the given resource for exclusive access by the calling thread. |
| [ExAcquireResourceSharedLite function](..\wmiguid\nf-wdm-exacquireresourcesharedlite.md) | The ExAcquireResourceSharedLite routine acquires the given resource for shared access by the calling thread. |
| [ExAcquireRundownProtection function](..\wmiguid\nf-wdm-exacquirerundownprotection.md) | The ExAcquireRundownProtection routine tries to acquire run-down protection on a shared object so the caller can safely access the object. |
| [ExAcquireRundownProtectionEx function](..\wmiguid\nf-wdm-exacquirerundownprotectionex.md) | The ExAcquireRundownProtectionEx routine tries to acquire run-down protection on a shared object so the caller can safely access the object. |
| [ExAcquireSharedStarveExclusive function](..\wmiguid\nf-wdm-exacquiresharedstarveexclusive.md) | The ExAcquireSharedStarveExclusive routine acquires a given resource for shared access without waiting for any pending attempts to acquire exclusive access to the same resource. |
| [ExAcquireSharedWaitForExclusive function](..\wmiguid\nf-wdm-exacquiresharedwaitforexclusive.md) | The ExAcquireSharedWaitForExclusive routine acquires the given resource for shared access if shared access can be granted and there are no exclusive waiters. |
| [ExAllocateFromLookasideListEx function](..\wmiguid\nf-wdm-exallocatefromlookasidelistex.md) | The ExAllocateFromLookasideListEx routine removes the first entry from the specified lookaside list, or, if the list is empty, dynamically allocates the storage for a new entry. |
| [ExAllocateFromNPagedLookasideList function](..\wmiguid\nf-wdm-exallocatefromnpagedlookasidelist.md) | The ExAllocateFromNPagedLookasideList routine returns a pointer to a nonpaged entry from the given lookaside list, or it returns a pointer to a newly allocated nonpaged entry. |
| [ExAllocateFromPagedLookasideList function](..\wmiguid\nf-wdm-exallocatefrompagedlookasidelist.md) | The ExAllocateFromPagedLookasideList routine returns a pointer to a paged entry from the given lookaside list, or it returns a pointer to a newly allocated paged entry. |
| [ExAllocatePool function](..\wmiguid\nf-wdm-exallocatepool.md) | The ExAllocatePool routine is obsolete, and is exported only for existing binaries. Use ExAllocatePoolWithTag instead.ExAllocatePool allocates pool memory of the specified type and returns a pointer to the allocated block. |
| [ExAllocatePoolWithQuota function](..\wmiguid\nf-wdm-exallocatepoolwithquota.md) | The ExAllocatePoolWithQuota routine is obsolete, and is exported only for existing driver binaries. Use ExAllocatePoolWithQuotaTag instead.ExAllocatePoolWithQuota allocates pool memory, charging quota against the current process. |
| [ExAllocatePoolWithQuotaTag function](..\wmiguid\nf-wdm-exallocatepoolwithquotatag.md) | The ExAllocatePoolWithQuotaTag routine allocates pool memory, charging the quota against the current process. |
| [ExAllocatePoolWithTag function](..\wmiguid\nf-wdm-exallocatepoolwithtag.md) | The ExAllocatePoolWithTag routine allocates pool memory of the specified type and returns a pointer to the allocated block. |
| [ExAllocatePoolWithTagPriority function](..\wmiguid\nf-wdm-exallocatepoolwithtagpriority.md) | The ExAllocatePoolWithTagPriority routine allocates pool memory of the specified type. |
| [ExAllocateTimer function](..\wmiguid\nf-wdm-exallocatetimer.md) | The ExAllocateTimer routine allocates and initializes a timer object. |
| [ExCancelTimer function](..\wmiguid\nf-wdm-excanceltimer.md) | The ExCancelTimer routine cancels a timer that was set by a previous call to the ExSetTimer routine. |
| [ExConvertExclusiveToSharedLite function](..\wmiguid\nf-wdm-exconvertexclusivetosharedlite.md) | The ExConvertExclusiveToSharedLite routine converts a given resource from acquired for exclusive access to acquired for shared access. |
| [ExCreateCallback function](..\wmiguid\nf-wdm-excreatecallback.md) | The ExCreateCallback routine either creates a new callback object or opens an existing callback object on behalf of the caller. |
| [ExDeleteLookasideListEx function](..\wmiguid\nf-wdm-exdeletelookasidelistex.md) | The ExDeleteLookasideListEx routine deletes a lookaside list. |
| [ExDeleteNPagedLookasideList function](..\wmiguid\nf-wdm-exdeletenpagedlookasidelist.md) | The ExDeleteNPagedLookasideList routine destroys a nonpaged lookaside list. |
| [ExDeletePagedLookasideList function](..\wmiguid\nf-wdm-exdeletepagedlookasidelist.md) | The ExDeletePagedLookasideList routine destroys a paged lookaside list. |
| [ExDeleteResourceLite function](..\wmiguid\nf-wdm-exdeleteresourcelite.md) | The ExDeleteResourceLite routine deletes a given resource from the system's resource list. |
| [ExDeleteTimer function](..\wmiguid\nf-wdm-exdeletetimer.md) | The ExDeleteTimer routine deletes a timer object that was previously allocated by the ExAllocateTimer routine. |
| [ExFlushLookasideListEx function](..\wmiguid\nf-wdm-exflushlookasidelistex.md) | The ExFlushLookasideListEx routine flushes all entries from the specified lookaside list and frees the allocated storage for each entry. |
| [ExFreePool function](..\wmiguid\nf-wdm-exfreepool.md) | The ExFreePool routine deallocates a block of pool memory. |
| [ExFreePoolWithTag function](..\wmiguid\nf-wdm-exfreepoolwithtag.md) | The ExFreePoolWithTag routine deallocates a block of pool memory allocated with the specified tag. |
| [ExFreeToLookasideListEx function](..\wmiguid\nf-wdm-exfreetolookasidelistex.md) | The ExFreeToLookasideListEx routine inserts an entry into a lookaside list, or, if the list is full, frees the allocated storage for the entry. |
| [ExFreeToNPagedLookasideList function](..\wmiguid\nf-wdm-exfreetonpagedlookasidelist.md) | The ExFreeToNPagedLookasideList routine returns a nonpaged entry to the given lookaside list or to nonpaged pool. |
| [ExFreeToPagedLookasideList function](..\wmiguid\nf-wdm-exfreetopagedlookasidelist.md) | The ExFreeToPagedLookasideList routine returns a pageable entry to the given lookaside list or to paged pool. |
| [ExGetExclusiveWaiterCount function](..\wmiguid\nf-wdm-exgetexclusivewaitercount.md) | The ExGetExclusiveWaiterCount routine returns the number of waiters on exclusive access to a given resource. |
| [ExGetFirmwareEnvironmentVariable function](..\wmiguid\nf-wdm-exgetfirmwareenvironmentvariable.md) | The ExGetFirmwareEnvironmentVariable routine gets the value of the specified system firmware environment variable. |
| [ExGetFirmwareType function](..\wmiguid\nf-wdm-exgetfirmwaretype.md) | Returns the system firmware type. |
| [ExGetPreviousMode function](..\wmiguid\nf-wdm-exgetpreviousmode.md) | The ExGetPreviousMode routine returns the previous processor mode for the current thread. |
| [ExGetSharedWaiterCount function](..\wmiguid\nf-wdm-exgetsharedwaitercount.md) | The ExGetSharedWaiterCount routine returns the number of waiters on shared access to a given resource. |
| [ExInitializeDeleteTimerParameters function](..\wmiguid\nf-wdm-exinitializedeletetimerparameters.md) | The ExInitializeDeleteTimerParameters routine initializes an EXT_DELETE_PARAMETERS structure. |
| [ExInitializeFastMutex function](..\wmiguid\nf-wdm-exinitializefastmutex.md) | The ExInitializeFastMutex routine initializes a fast mutex variable, used to synchronize mutually exclusive access by a set of threads to a shared resource. |
| [ExInitializeLookasideListEx function](..\wmiguid\nf-wdm-exinitializelookasidelistex.md) | The ExInitializeLookasideListEx routine initializes a lookaside list. |
| [ExInitializeNPagedLookasideList function](..\wmiguid\nf-wdm-exinitializenpagedlookasidelist.md) | The ExInitializeNPagedLookasideList routine initializes a lookaside list for nonpaged entries of the specified size. |
| [ExInitializePagedLookasideList function](..\wmiguid\nf-wdm-exinitializepagedlookasidelist.md) | The ExInitializePagedLookasideList routine initializes a lookaside list for pageable entries of the specified size. |
| [ExInitializeResourceLite function](..\wmiguid\nf-wdm-exinitializeresourcelite.md) | The ExInitializeResourceLite routine initializes a resource variable. |
| [ExInitializeRundownProtection function](..\wmiguid\nf-wdm-exinitializerundownprotection.md) | The ExInitializeRundownProtection routine initializes run-down protection on a shared object. |
| [ExInitializeSetTimerParameters function](..\wmiguid\nf-wdm-exinitializesettimerparameters.md) | The ExInitializeSetTimerParameters routine initializes an EXT_SET_PARAMETERS structure. |
| [ExInterlockedAddLargeInteger function](..\wmiguid\nf-wdm-exinterlockedaddlargeinteger.md) | The ExInterlockedAddLargeInteger routine adds a large integer value to the specified variable as an atomic operation. |
| [ExInterlockedAddUlong function](..\wmiguid\nf-wdm-exinterlockedaddulong.md) | The ExInterlockedAddUlong routine adds an unsigned long value to a given unsigned integer as an atomic operation. |
| [ExInterlockedInsertHeadList function](..\wmiguid\nf-wdm-exinterlockedinsertheadlist.md) | The ExInterlockedInsertHeadList routine atomically inserts an entry at the beginning of a doubly linked list of LIST_ENTRY structures. |
| [ExInterlockedInsertTailList function](..\wmiguid\nf-wdm-exinterlockedinserttaillist.md) | The ExInterlockedInsertTailList routine atomically inserts an entry at the end of a doubly linked list of LIST_ENTRY structures. |
| [ExInterlockedPopEntryList function](..\wmiguid\nf-wdm-exinterlockedpopentrylist.md) | The ExInterlockedPopEntryList routine atomically removes an entry from the beginning of a singly linked list of SINGLE_LIST_ENTRY structures. |
| [ExInterlockedPushEntryList function](..\wmiguid\nf-wdm-exinterlockedpushentrylist.md) | The ExInterlockedPushEntryList routine atomically inserts an entry at the beginning of a singly linked list of SINGLE_LIST_ENTRY structures. |
| [ExInterlockedRemoveHeadList function](..\wmiguid\nf-wdm-exinterlockedremoveheadlist.md) | The ExInterlockedRemoveHeadList routine removes an entry from the beginning of a doubly linked list of LIST_ENTRY structures. |
| [ExIsProcessorFeaturePresent function](..\wmiguid\nf-wdm-exisprocessorfeaturepresent.md) | The ExIsProcessorFeaturePresent routine queries for the existence of a specified processor feature. |
| [ExIsResourceAcquiredExclusiveLite function](..\wmiguid\nf-wdm-exisresourceacquiredexclusivelite.md) | The ExIsResourceAcquiredExclusiveLite routine returns whether the current thread has exclusive access to a given resource. |
| [ExIsResourceAcquiredSharedLite function](..\wmiguid\nf-wdm-exisresourceacquiredsharedlite.md) | The ExIsResourceAcquiredSharedLite routine returns whether the current thread has access (either shared or exclusive) to a given resource. |
| [ExIsSoftBoot function](..\wmiguid\nf-wdm-exissoftboot.md) | Determines whether the system has gone through a soft restart. |
| [ExLocalTimeToSystemTime function](..\wmiguid\nf-wdm-exlocaltimetosystemtime.md) | The ExLocalTimeToSystemTime routine converts a system time value for the current time zone to an unbiased, GreenGMT value. |
| [ExNotifyCallback function](..\wmiguid\nf-wdm-exnotifycallback.md) | The ExNotifyCallback routine causes all callback routines registered for the given object to be called. |
| [ExQueryDepthSList function](..\wmiguid\nf-wdm-exquerydepthslist.md) | The ExQueryDepthSList routine returns the number of entries currently in a given sequenced singly linked list. |
| [ExQueryTimerResolution function](..\wmiguid\nf-wdm-exquerytimerresolution.md) | The ExQueryTimerResolution routine reports the range of timer resolutions that are supported by the system clock. |
| [ExRaiseAccessViolation function](..\wmiguid\nf-ntddk-exraiseaccessviolation.md) | The ExRaiseAccessViolation routine can be used with structured exception handling to throw a driver-determined exception for a memory access violation that occurs when a driver processes I/O requests. |
| [ExRaiseDatatypeMisalignment function](..\wmiguid\nf-ntddk-exraisedatatypemisalignment.md) | The ExRaiseDatatypeMisalignment routine can be used with structured exception handling to throw a driver-determined exception for a misaligned data type that occurs when a driver processes I/O requests. |
| [ExRaiseStatus function](..\wmiguid\nf-wdm-exraisestatus.md) | The ExRaiseStatus routine is called by drivers that supply structured exception handlers to handle particular errors that occur while they are processing I/O requests. |
| [ExReInitializeRundownProtection function](..\wmiguid\nf-wdm-exreinitializerundownprotection.md) | The ExReInitializeRundownProtection routine reinitializes an EX_RUNDOWN_REF structure after the associated object is run down. |
| [ExRegisterCallback function](..\wmiguid\nf-wdm-exregistercallback.md) | The ExRegisterCallback routine registers a given callback routine with a given callback object. |
| [ExReinitializeResourceLite function](..\wmiguid\nf-wdm-exreinitializeresourcelite.md) | The ExReinitializeResourceLite routine reinitializes an existing resource variable. |
| [ExReleaseResourceForThreadLite function](..\wmiguid\nf-wdm-exreleaseresourceforthreadlite.md) | The ExReleaseResourceForThreadLite routine releases the input resource of the indicated thread. |
| [ExReleaseRundownProtection function](..\wmiguid\nf-wdm-exreleaserundownprotection.md) | The ExReleaseRundownProtection routine releases run-down protection that the caller previously acquired by calling the ExAcquireRundownProtection routine. |
| [ExReleaseRundownProtectionEx function](..\wmiguid\nf-wdm-exreleaserundownprotectionex.md) | The ExReleaseRundownProtectionEx routine releases run-down protection that the caller previously acquired by calling the ExAcquireRundownProtectionEx routine. |
| [ExReleaseSpinLockExclusive function](..\wmiguid\nf-wdm-exreleasespinlockexclusive.md) | The ExReleaseSpinLockExclusive routine releases a spin lock that the caller previously acquired for exclusive access, and restores the IRQL to its original value. |
| [ExReleaseSpinLockShared function](..\wmiguid\nf-wdm-exreleasespinlockshared.md) | The ExReleaseSpinLockShared routine releases ownership of a spin lock that the caller previously acquired for shared access, and restores the IRQL to its original value. |
| [ExRundownCompleted function](..\wmiguid\nf-wdm-exrundowncompleted.md) | The ExRundownCompleted routine updates the run-down status of a shared object to indicate that the run down of the object has completed. |
| [ExSetFirmwareEnvironmentVariable function](..\wmiguid\nf-wdm-exsetfirmwareenvironmentvariable.md) | The ExSetFirmwareEnvironmentVariable routine sets the value of the specified system firmware environment variable. |
| [ExSetResourceOwnerPointer function](..\wmiguid\nf-wdm-exsetresourceownerpointer.md) | The ExSetResourceOwnerPointer routine sets the owner thread pointer for an executive resource. |
| [ExSetResourceOwnerPointerEx function](..\wmiguid\nf-wdm-exsetresourceownerpointerex.md) | The ExSetResourceOwnerPointerEx routine transfers the ownership of an executive resource from the calling thread to an owner pointer, which is a system address that identifies the resource owner. |
| [ExSetTimer function](..\wmiguid\nf-wdm-exsettimer.md) | The ExSetTimer routine starts a timer operation and sets the timer to expire at the specified due time. |
| [ExSetTimerResolution function](..\wmiguid\nf-wdm-exsettimerresolution.md) | The ExSetTimerResolution routine modifies the frequency at which the system clock interrupts. Use this routine with extreme caution (see the following Remarks section). |
| [ExSystemTimeToLocalTime function](..\wmiguid\nf-wdm-exsystemtimetolocaltime.md) | The ExSystemTimeToLocalTime routine converts a GMT system time value to the local system time for the current time zone. |
| [ExTryConvertSharedSpinLockExclusive function](..\wmiguid\nf-wdm-extryconvertsharedspinlockexclusive.md) | The ExTryConvertSharedSpinLockExclusive routine attempts to convert the access state of a spin lock from acquired for shared access to exclusive access. |
| [ExUnregisterCallback function](..\wmiguid\nf-wdm-exunregistercallback.md) | The ExUnregisterCallback routine removes a callback routine previously registered with a callback object from the list of routines to be called during the notification process. |
| [ExUuidCreate function](..\wmiguid\nf-ntddk-exuuidcreate.md) | The ExUuidCreate routine initializes a UUID (GUID) structure to a newly generated value. |
| [ExWaitForRundownProtectionRelease function](..\wmiguid\nf-wdm-exwaitforrundownprotectionrelease.md) | The ExWaitForRundownProtectionRelease routine waits until all drivers that have already been granted run-down protection complete their accesses of the shared object. |
| [FirstEntrySList function](..\wmiguid\nf-wdm-firstentryslist.md) | The FirstEntrySList routine returns the first entry in a sequenced singly linked list. |
| [HalAllocateHardwareCounters function](..\wmiguid\nf-ntddk-halallocatehardwarecounters.md) | The HalAllocateHardwareCounters routine allocates a set of hardware performance counters. |
| [HalExamineMBR function](..\wmiguid\nf-ntddk-halexaminembr.md) | The HalExamineMBR routine reads the master boot record (MBR) of a disk and returns data from the MBR if the MBR is of the type specified by the caller. |
| [HalFreeHardwareCounters function](..\wmiguid\nf-ntddk-halfreehardwarecounters.md) | The HalFreeHardwareCounters routine frees a set of hardware performance counters that was acquired in a previous call to HalAllocateHardwareCounters routine. |
| [InitializeListHead function](..\wmiguid\nf-wdm-initializelisthead.md) | The InitializeListHead routine initializes a LIST_ENTRY structure that represents the head of a doubly linked list. |
| [InitializeSListHead function](..\wmiguid\nf-wdm-initializeslisthead.md) | The InitializeSListHead routine (or ExInitializeSListHead) initializes an SLIST_HEADER structure that represents the head of a sequenced singly linked list. |
| [InsertHeadList function](..\wmiguid\nf-wdm-insertheadlist.md) | The InsertHeadList routine inserts an entry at the head of a doubly linked list of LIST_ENTRY structures. |
| [InsertTailList function](..\wmiguid\nf-wdm-inserttaillist.md) | The InsertTailList routine inserts an entry at the tail of a doubly linked list of LIST_ENTRY structures. |
| [InterlockedAnd function](..\wmiguid\nf-wdm-interlockedand.md) | The InterlockedAnd macro atomically computes a bitwise AND operation. |
| [InterlockedCompareExchange function](..\wmiguid\nf-wdm-interlockedcompareexchange.md) | The InterlockedCompareExchange routine performs an atomic operation that compares the input value pointed to by Destination with the value of Comparand. |
| [InterlockedCompareExchangePointer function](..\wmiguid\nf-wdm-interlockedcompareexchangepointer.md) | The InterlockedCompareExchangePointer routine performs an atomic operation that compares the input pointer value pointed to by Destination with the pointer value Comparand. |
| [InterlockedDecrement function](..\wmiguid\nf-wdm-interlockeddecrement.md) | The InterlockedDecrement routine decrements a caller-supplied variable of type LONG as an atomic operation. |
| [InterlockedExchange function](..\wmiguid\nf-wdm-interlockedexchange.md) | The InterlockedExchange routine sets an integer variable to a given value as an atomic operation. |
| [InterlockedExchangeAdd function](..\wmiguid\nf-wdm-interlockedexchangeadd.md) | The InterlockedExchangeAdd routine adds a value to a given integer as an atomic operation and returns the original value of the given integer. |
| [InterlockedExchangePointer function](..\wmiguid\nf-wdm-interlockedexchangepointer.md) | The InterlockedExchangePointer routine performs an atomic operation that sets a pointer to a new value. |
| [InterlockedIncrement function](..\wmiguid\nf-wdm-interlockedincrement.md) | The InterlockedIncrement routine increments a caller-supplied variable as an atomic operation. |
| [InterlockedOr function](..\wmiguid\nf-wdm-interlockedor.md) | The InterlockedOr routine atomically computes a bitwise OR operation. |
| [InterlockedXor function](..\wmiguid\nf-wdm-interlockedxor.md) | The InterlockedOr routine atomically computes a bitwise exclusive OR operation. |
| [IoAllocateController function](..\wmiguid\nf-ntddk-ioallocatecontroller.md) | The IoAllocateController routine sets up the call to a driver-supplied ControllerControl routine as soon as the device controller, represented by the given controller object, is available to carry out an I/O operation for the target device, represented by the given device object. |
| [IoAllocateDriverObjectExtension function](..\wmiguid\nf-wdm-ioallocatedriverobjectextension.md) | The IoAllocateDriverObjectExtension routine allocates a per-driver context area, called a driver object extension, and assigns a unique identifier to it. |
| [IoAllocateErrorLogEntry function](..\wmiguid\nf-wdm-ioallocateerrorlogentry.md) | The IoAllocateErrorLogEntry routine allocates an error log entry, and returns a pointer to the packet that the caller uses to supply information about an I/O error. |
| [IoAllocateIrp function](..\wmiguid\nf-wdm-ioallocateirp.md) | The IoAllocateIrp routine allocates an IRP, given the number of I/O stack locations for each driver layered under the caller, and, optionally, for the caller. |
| [IoAllocateMdl function](..\wmiguid\nf-wdm-ioallocatemdl.md) | The IoAllocateMdl routine allocates a memory descriptor list (MDL) large enough to map a buffer, given the buffer's starting address and length. Optionally, this routine associates the MDL with an IRP. |
| [IoAllocateWorkItem function](..\wmiguid\nf-wdm-ioallocateworkitem.md) | The IoAllocateWorkItem routine allocates a work item. |
| [IoAttachDevice function](..\wmiguid\nf-wdm-ioattachdevice.md) | The IoAttachDevice routine attaches the caller's device object to a named target device object, so that I/O requests bound for the target device are routed first to the caller. |
| [IoAttachDeviceToDeviceStack function](..\wmiguid\nf-wdm-ioattachdevicetodevicestack.md) | The IoAttachDeviceToDeviceStack routine attaches the caller's device object to the highest device object in the chain and returns a pointer to the previously highest device object. |
| [IoBuildAsynchronousFsdRequest function](..\wmiguid\nf-wdm-iobuildasynchronousfsdrequest.md) | The IoBuildAsynchronousFsdRequest routine allocates and sets up an IRP to be sent to lower-level drivers. |
| [IoBuildDeviceIoControlRequest function](..\wmiguid\nf-wdm-iobuilddeviceiocontrolrequest.md) | The IoBuildDeviceIoControlRequest routine allocates and sets up an IRP for a synchronously processed device control request. |
| [IoBuildPartialMdl function](..\wmiguid\nf-wdm-iobuildpartialmdl.md) | The IoBuildPartialMdl routine builds a new memory descriptor list (MDL) that represents part of a buffer that is described by an existing MDL. |
| [IoBuildSynchronousFsdRequest function](..\wmiguid\nf-wdm-iobuildsynchronousfsdrequest.md) | The IoBuildSynchronousFsdRequest routine allocates and sets up an IRP for a synchronously processed I/O request. |
| [IoCancelIrp function](..\wmiguid\nf-wdm-iocancelirp.md) | The IoCancelIrp routine sets the cancel bit in a given IRP and calls the cancel routine for the IRP if there is one. |
| [IoCheckLinkShareAccess function](..\wmiguid\nf-wdm-iochecklinkshareaccess.md) | The IoCheckLinkShareAccess routine is called by file system drivers (FSDs) or other highest-level drivers to check whether link shared access to a file object is permitted. |
| [IoCheckShareAccess function](..\wmiguid\nf-wdm-iocheckshareaccess.md) | The IoCheckShareAccess routine is called by file system drivers (FSDs) or other highest-level drivers to check whether shared access to a file object is permitted. |
| [IoCheckShareAccessEx function](..\wmiguid\nf-wdm-iocheckshareaccessex.md) | The IoCheckShareAccessEx routine is called by file system drivers (FSDs) or other highest-level drivers to check whether shared access to a file object is permitted. |
| [IoClearActivityIdThread function](..\wmiguid\nf-ntddk-ioclearactivityidthread.md) | The IoClearActivityIdThread routine clears the activity ID of the current thread. |
| [IoConnectInterrupt function](..\wmiguid\nf-wdm-ioconnectinterrupt.md) | The IoConnectInterrupt routine registers a device driver's InterruptService routine (ISR), so that it will be called when a device interrupts on any of a specified set of processors. |
| [IoConnectInterruptEx function](..\wmiguid\nf-wdm-ioconnectinterruptex.md) | For more information, see the WdmlibIoConnectInterruptEx function.#define IoConnectInterruptEx WdmlibIoConnectInterruptEx |
| [IoCopyCurrentIrpStackLocationToNext function](..\wmiguid\nf-wdm-iocopycurrentirpstacklocationtonext.md) | The IoCopyCurrentIrpStackLocationToNext routine copies the IRP stack parameters from the current I/O stack location to the stack location of the next-lower driver. |
| [IoCreateController function](..\wmiguid\nf-ntddk-iocreatecontroller.md) | The IoCreateController routine allocates memory for and initializes a controller object with a controller extension of a driver-determined size. |
| [IoCreateDevice function](..\wmiguid\nf-wdm-iocreatedevice.md) | The IoCreateDevice routine creates a device object for use by a driver. |
| [IoCreateFile function](..\wmiguid\nf-wdm-iocreatefile.md) | The IoCreateFile routine either causes a new file or directory to be created, or it opens an existing file, device, directory, or volume, giving the caller a handle for the file object. |
| [IoCreateNotificationEvent function](..\wmiguid\nf-wdm-iocreatenotificationevent.md) | The IoCreateNotificationEvent routine creates or opens a named notification event used to notify one or more threads of execution that an event has occurred. |
| [IoCreateSymbolicLink function](..\wmiguid\nf-wdm-iocreatesymboliclink.md) | The IoCreateSymbolicLink routine sets up a symbolic link between a device object name and a user-visible name for the device. |
| [IoCreateSynchronizationEvent function](..\wmiguid\nf-wdm-iocreatesynchronizationevent.md) | The IoCreateSynchronizationEvent routine creates or opens a named synchronization event for use in serialization of access to hardware between two otherwise unrelated drivers. |
| [IoCreateSystemThread function](..\wmiguid\nf-wdm-iocreatesystemthread.md) | The IoCreateSystemThread routine creates a system thread that executes in kernel mode, and supplies a handle for the thread. |
| [IoCreateUnprotectedSymbolicLink function](..\wmiguid\nf-wdm-iocreateunprotectedsymboliclink.md) | The IoCreateUnprotectedSymbolicLink routine sets up an unprotected symbolic link between a device object name and a corresponding Win32-visible name. |
| [IoCsqInitialize function](..\wmiguid\nf-wdm-iocsqinitialize.md) | The IoCsqInitialize routine initializes the driver's cancel-safe IRP queue dispatch table. |
| [IoCsqInitializeEx function](..\wmiguid\nf-wdm-iocsqinitializeex.md) | The IoCsqInitializeEx routine initializes the dispatch table for a cancel-safe IRP queue. |
| [IoCsqInsertIrp function](..\wmiguid\nf-wdm-iocsqinsertirp.md) | The IoCsqInsertIrp routine inserts an IRP in the driver's cancel-safe IRP queue. |
| [IoCsqInsertIrpEx function](..\wmiguid\nf-wdm-iocsqinsertirpex.md) | The IoCsqInsertIrpEx routine inserts an IRP into the driver's cancel-safe IRP queue. |
| [IoCsqRemoveIrp function](..\wmiguid\nf-wdm-iocsqremoveirp.md) | The IoCsqRemoveIrp routine removes a particular IRP from the queue. |
| [IoCsqRemoveNextIrp function](..\wmiguid\nf-wdm-iocsqremovenextirp.md) | The IoCsqRemoveNextIrp routine removes the next matching IRP in the queue. |
| [IoDecrementKeepAliveCount function](..\wmiguid\nf-ntddk-iodecrementkeepalivecount.md) | The IoDecrementKeepAliveCount routine decrements a reference count associated with an Windows app on a specific device. |
| [IoDeleteController function](..\wmiguid\nf-ntddk-iodeletecontroller.md) | The IoDeleteController routine removes a given controller object from the system, for example, when the driver that created it is being unloaded. |
| [IoDeleteDevice function](..\wmiguid\nf-wdm-iodeletedevice.md) | The IoDeleteDevice routine removes a device object from the system, for example, when the underlying device is removed from the system. |
| [IoDeleteSymbolicLink function](..\wmiguid\nf-wdm-iodeletesymboliclink.md) | The IoDeleteSymbolicLink routine removes a symbolic link from the system. |
| [IoDetachDevice function](..\wmiguid\nf-wdm-iodetachdevice.md) | The IoDetachDevice routine releases an attachment between the caller's device object and a lower driver's device object. |
| [IoDisconnectInterrupt function](..\wmiguid\nf-wdm-iodisconnectinterrupt.md) | The IoDisconnectInterrupt routine releases a device driver's set of interrupt object(s) when the device is paused or removed, or when the driver is being unloaded. |
| [IoDisconnectInterruptEx function](..\wmiguid\nf-wdm-iodisconnectinterruptex.md) | For more information, see the WdmlibIoDisconnectInterruptEx function.#define IoDisconnectInterruptEx WdmlibIoDisconnectInterruptEx |
| [IoForwardIrpSynchronously function](..\wmiguid\nf-wdm-ioforwardirpsynchronously.md) | The IoForwardIrpSynchronously routine sends an IRP to a specified driver and waits for that driver to complete the IRP. |
| [IoFreeController function](..\wmiguid\nf-ntddk-iofreecontroller.md) | The IoFreeController routine releases a previously allocated controller object when the driver has completed an I/O request. |
| [IoFreeErrorLogEntry function](..\wmiguid\nf-wdm-iofreeerrorlogentry.md) | The IoFreeErrorLogEntry routine frees an unused error log entry. |
| [IoFreeIrp function](..\wmiguid\nf-wdm-iofreeirp.md) | The IoFreeIrp routine releases a caller-allocated IRP from the caller's IoCompletion routine. |
| [IoFreeMdl function](..\wmiguid\nf-wdm-iofreemdl.md) | The IoFreeMdl routine releases a caller-allocated memory descriptor list (MDL). |
| [IoFreeWorkItem function](..\wmiguid\nf-wdm-iofreeworkitem.md) | The IoFreeWorkItem routine frees a work item that was allocated by IoAllocateWorkItem. |
| [IoGetActivityIdIrp function](..\wmiguid\nf-ntddk-iogetactivityidirp.md) | The IoGetActivityIdIrp routine retrieves the current activity ID associated with an IRP. |
| [IoGetActivityIdThread function](..\wmiguid\nf-ntddk-iogetactivityidthread.md) | The IoGetActivityIdThread routine returns the activity ID associated with the current thread. |
| [IoGetAffinityInterrupt function](..\wmiguid\nf-wdm-iogetaffinityinterrupt.md) | For more information, see the WdmlibIoGetAffinityInterrupt function.#define IoGetAffinityInterrupt WdmlibIoGetAffinityInterrupt |
| [IoGetAttachedDeviceReference function](..\wmiguid\nf-wdm-iogetattacheddevicereference.md) | The IoGetAttachedDeviceReference routine returns a pointer to the highest level device object in a driver stack and increments the reference count on that object. |
| [IoGetBootDiskInformation function](..\wmiguid\nf-wdm-iogetbootdiskinformation.md) | The IoGetBootDiskInformation routine returns information describing the boot and system disks. |
| [IoGetConfigurationInformation function](..\wmiguid\nf-ntddk-iogetconfigurationinformation.md) | The IoGetConfigurationInformation routine returns a pointer to the I/O manager's global configuration information structure, which contains the current values for how many physical disk, floppy, CD-ROM, tape, SCSI HBA, serial, and parallel devices have device objects created to represent them by drivers as they are loaded. |
| [IoGetContainerInformation function](..\wmiguid\nf-wdm-iogetcontainerinformation.md) | The IoGetContainerInformation routine provides information about the current state of a user session. |
| [IoGetCurrentIrpStackLocation function](..\wmiguid\nf-wdm-iogetcurrentirpstacklocation.md) | The IoGetCurrentIrpStackLocation routine returns a pointer to the caller's I/O stack location in the specified IRP. |
| [IoGetCurrentProcess function](..\wmiguid\nf-wdm-iogetcurrentprocess.md) | The IoGetCurrentProcess routine returns a pointer to the current process. |
| [IoGetDeviceInterfaceAlias function](..\wmiguid\nf-wdm-iogetdeviceinterfacealias.md) | The IoGetDeviceInterfaceAlias routine returns the alias device interface of the specified device interface instance, if the alias exists. |
| [IoGetDeviceInterfacePropertyData function](..\wmiguid\nf-wdm-iogetdeviceinterfacepropertydata.md) | The IoGetDeviceInterfacePropertyData routine retrieves the current value of a device interface property. |
| [IoGetDeviceInterfaces function](..\wmiguid\nf-wdm-iogetdeviceinterfaces.md) | The IoGetDeviceInterfaces routine returns a list of device interface instances of a particular device interface class (such as all devices on the system that support a HID interface). |
| [IoGetDeviceNumaNode function](..\wmiguid\nf-wdm-iogetdevicenumanode.md) | The IoGetDeviceNumaNode routine gets the node number of a device. |
| [IoGetDeviceObjectPointer function](..\wmiguid\nf-wdm-iogetdeviceobjectpointer.md) | The IoGetDeviceObjectPointer routine returns a pointer to the top object in the named device object's stack and a pointer to the corresponding file object, if the requested access to the objects can be granted. |
| [IoGetDeviceProperty function](..\wmiguid\nf-wdm-iogetdeviceproperty.md) | The IoGetDeviceProperty routine retrieves information about a device such as configuration information and the name of its PDO. |
| [IoGetDevicePropertyData function](..\wmiguid\nf-wdm-iogetdevicepropertydata.md) | The IoGetDevicePropertyData routine retrieves the current setting for a device property. |
| [IoGetDmaAdapter function](..\wmiguid\nf-wdm-iogetdmaadapter.md) | The IoGetDmaAdapter routine returns a pointer to the DMA adapter structure for a physical device object. |
| [IoGetDriverObjectExtension function](..\wmiguid\nf-wdm-iogetdriverobjectextension.md) | The IoGetDriverObjectExtension routine retrieves a previously allocated per-driver context area. |
| [IoGetFileObjectGenericMapping function](..\wmiguid\nf-ntddk-iogetfileobjectgenericmapping.md) | The IoGetFileObjectGenericMapping routine returns information about the mapping between each generic access right and the set of specific access rights for file objects. |
| [IoGetInitialStack function](..\wmiguid\nf-wdm-iogetinitialstack.md) | The IoGetInitialStack routine returns the base address of the current thread's stack. |
| [IoGetInitiatorProcess function](..\wmiguid\nf-ntddk-iogetinitiatorprocess.md) | The IoGetInitiatorProcess routine retrieves the process which initiated the creation of a file object if different than the process which is issuing the create. |
| [IoGetIoPriorityHint function](..\wmiguid\nf-wdm-iogetiopriorityhint.md) | The IoGetIoPriorityHint routine gets the priority hint value from an IRP. |
| [IoGetNextIrpStackLocation function](..\wmiguid\nf-wdm-iogetnextirpstacklocation.md) | The IoGetNextIrpStackLocation routine gives a higher level driver access to the next-lower driver's I/O stack location in an IRP so the caller can set it up for the lower driver. |
| [IoGetPagingIoPriority function](..\wmiguid\nf-ntddk-iogetpagingiopriority.md) | The IoGetPagingIoPriority routine indicates the priority level of a paging I/O request. |
| [IoGetRelatedDeviceObject function](..\wmiguid\nf-wdm-iogetrelateddeviceobject.md) | Given a file object, the IoGetRelatedDeviceObject routine returns a pointer to the corresponding device object. |
| [IoGetRemainingStackSize function](..\wmiguid\nf-wdm-iogetremainingstacksize.md) | The IoGetRemainingStackSize routine returns the current amount of available kernel-mode stack space. |
| [IoGetStackLimits function](..\wmiguid\nf-wdm-iogetstacklimits.md) | The IoGetStackLimits routine returns the boundaries of the current thread's stack frame. |
| [IoIncrementKeepAliveCount function](..\wmiguid\nf-ntddk-ioincrementkeepalivecount.md) | The IoIncrementKeepAliveCount routine increments a reference count associated with an Windows app process on a specific device. |
| [IoInitializeDpcRequest function](..\wmiguid\nf-wdm-ioinitializedpcrequest.md) | The IoInitializeDpcRequest routine registers a driver-supplied DpcForIsr routine. |
| [IoInitializeIrp function](..\wmiguid\nf-wdm-ioinitializeirp.md) | The IoInitializeIrp routine initializes a given IRP that was allocated by the caller. |
| [IoInitializeTimer function](..\wmiguid\nf-wdm-ioinitializetimer.md) | The IoInitializeTimer routine sets up a driver-supplied IoTimer routine associated with a given device object. |
| [IoInitializeWorkItem function](..\wmiguid\nf-wdm-ioinitializeworkitem.md) | The IoInitializeWorkItem routine initializes a work item that the caller has already allocated. |
| [IoInvalidateDeviceRelations function](..\wmiguid\nf-wdm-ioinvalidatedevicerelations.md) | The IoInvalidateDeviceRelations routine notifies the PnP manager that the relations for a device (such as bus relations, ejection relations, removal relations, and the target device relation) have changed. |
| [IoInvalidateDeviceState function](..\wmiguid\nf-wdm-ioinvalidatedevicestate.md) | The IoInvalidateDeviceState routine notifies the PnP manager that some aspect of the PnP state of a device has changed. |
| [IoIs32bitProcess function](..\wmiguid\nf-wdm-iois32bitprocess.md) | The IoIs32bitProcess routine checks whether the originator of the current I/O request is a 32-bit user-mode application. |
| [IoIsValidIrpStatus function](..\wmiguid\nf-ntddk-ioisvalidirpstatus.md) | The IoIsValidIrpStatus routine validates the specified NTSTATUS status code value. |
| [IoIsWdmVersionAvailable function](..\wmiguid\nf-wdm-ioiswdmversionavailable.md) | The IoIsWdmVersionAvailable routine checks whether a given WDM version is supported by the operating system. |
| [IoMakeAssociatedIrp function](..\wmiguid\nf-ntddk-iomakeassociatedirp.md) | This routine is reserved for use by file systems and file system filter drivers. |
| [IoMarkIrpPending function](..\wmiguid\nf-wdm-iomarkirppending.md) | The IoMarkIrpPending routine marks the specified IRP, indicating that a driver's dispatch routine subsequently returned STATUS_PENDING because further processing is required by other driver routines. |
| [IoOpenDeviceInterfaceRegistryKey function](..\wmiguid\nf-wdm-ioopendeviceinterfaceregistrykey.md) | The IoOpenDeviceInterfaceRegistryKey routine returns a handle to a registry key for storing information about a particular device interface instance. |
| [IoOpenDeviceRegistryKey function](..\wmiguid\nf-wdm-ioopendeviceregistrykey.md) | The IoOpenDeviceRegistryKey routine returns a handle to a device-specific or a driver-specific registry key for a particular device instance. |
| [IoPropagateActivityIdToThread function](..\wmiguid\nf-ntddk-iopropagateactivityidtothread.md) | The IoPropagateActivityIdToThread routine associates the activity ID from an IRP with the current thread. |
| [IoQueryFullDriverPath function](..\wmiguid\nf-ntddk-ioqueryfulldriverpath.md) | The IoQueryFullDriverPath routine retrieves the full path name of the binary file that is loaded for the specified driver object. |
| [IoQueueWorkItem function](..\wmiguid\nf-wdm-ioqueueworkitem.md) | The IoQueueWorkItem routine associates a WorkItem routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread. |
| [IoQueueWorkItemEx function](..\wmiguid\nf-wdm-ioqueueworkitemex.md) | The IoQueueWorkItemEx routine associates a WorkItemEx routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread. |
| [IoRaiseHardError function](..\wmiguid\nf-ntddk-ioraiseharderror.md) | The IoRaiseHardError routine causes a dialog box to appears that warns the user that a device I/O error has occurred, which might indicate that a physical device is failing. |
| [IoRaiseInformationalHardError function](..\wmiguid\nf-ntddk-ioraiseinformationalharderror.md) | The IoRaiseInformationalHardError routine sends a dialog box to the user, warning about a device I/O error that indicates why a user I/O request failed. |
| [IoRegisterBootDriverCallback function](..\wmiguid\nf-ntddk-ioregisterbootdrivercallback.md) | The IoRegisterBootDriverCallback routine registers a BOOT_DRIVER_CALLBACK_FUNCTION routine to be called during the initialization of a boot-start driver and its dependent DLLs. |
| [IoRegisterBootDriverReinitialization function](..\wmiguid\nf-ntddk-ioregisterbootdriverreinitialization.md) | The IoRegisterBootDriverReinitialization routine is called by a boot driver to register the driver's reinitialization routine with the I/O manager to be called after all devices have been enumerated and started. |
| [IoRegisterContainerNotification function](..\wmiguid\nf-wdm-ioregistercontainernotification.md) | The IoRegisterContainerNotification routine registers a kernel-mode driver to receive notifications about a specified class of events. |
| [IoRegisterDeviceInterface function](..\wmiguid\nf-wdm-ioregisterdeviceinterface.md) | The IoRegisterDeviceInterface routine registers a device interface class, if it has not been previously registered, and creates a new instance of the interface class, which a driver can subsequently enable for use by applications or other system components. |
| [IoRegisterDriverReinitialization function](..\wmiguid\nf-ntddk-ioregisterdriverreinitialization.md) | The IoRegisterDriverReinitialization routine is called by a driver during its initialization or reinitialization to register its Reinitialize routine to be called again before the driver's and, possibly the system's, initialization is complete. |
| [IoRegisterLastChanceShutdownNotification function](..\wmiguid\nf-wdm-ioregisterlastchanceshutdownnotification.md) | The IoRegisterLastChanceShutdownNotification routine registers a driver to receive an IRP_MJ_SHUTDOWN IRP when the system is shut down, after all file systems have been flushed. |
| [IoRegisterPlugPlayNotification function](..\wmiguid\nf-wdm-ioregisterplugplaynotification.md) | The IoRegisterPlugPlayNotification routine registers a Plug and Play (PnP) notification callback routine to be called when a PnP event of the specified category occurs. |
| [IoRegisterShutdownNotification function](..\wmiguid\nf-wdm-ioregistershutdownnotification.md) | The IoRegisterShutdownNotification routine registers the driver to receive an IRP_MJ_SHUTDOWN IRP when the system is shut down. |
| [IoRemoveLinkShareAccess function](..\wmiguid\nf-wdm-ioremovelinkshareaccess.md) | The IoRemoveLinkShareAccess routine removes the access and link share-access information for a given open instance of a file object. |
| [IoRemoveShareAccess function](..\wmiguid\nf-wdm-ioremoveshareaccess.md) | The IoRemoveShareAccess routine removes the access and share-access information for a given open instance of a file object. |
| [IoReportDetectedDevice function](..\wmiguid\nf-ntddk-ioreportdetecteddevice.md) | The IoReportDetectedDevice routine reports a non-PnP device to the PnP manager. |
| [IoReportInterruptActive function](..\wmiguid\nf-wdm-ioreportinterruptactive.md) | The IoReportInterruptActive routine informs the operating system that a registered interrupt service routine (ISR) is active and ready to handle interrupt requests. |
| [IoReportInterruptInactive function](..\wmiguid\nf-wdm-ioreportinterruptinactive.md) | The IoReportInterruptInactive routine informs the operating system that a registered interrupt service routine (ISR) is inactive and is not expecting interrupt requests. |
| [IoReportResourceForDetection function](..\wmiguid\nf-ntddk-ioreportresourcefordetection.md) | The IoReportResourceForDetection routine claims hardware resources in the configuration registry for a legacy device. |
| [IoReportRootDevice function](..\wmiguid\nf-ntddk-ioreportrootdevice.md) | The IoReportRootDevice routine reports a device that cannot be detected by a PnP bus driver to the PnP Manager. IoReportRootDevice allows only one device per driver to be created. |
| [IoReportTargetDeviceChange function](..\wmiguid\nf-wdm-ioreporttargetdevicechange.md) | The IoReportTargetDeviceChange routine notifies the PnP manager that a custom event has occurred on a device. |
| [IoReportTargetDeviceChangeAsynchronous function](..\wmiguid\nf-wdm-ioreporttargetdevicechangeasynchronous.md) | The IoReportTargetDeviceChangeAsynchronous routine notifies the PnP manager that a custom event has occurred on a device. |
| [IoRequestDeviceEject function](..\wmiguid\nf-wdm-iorequestdeviceeject.md) | The IoRequestDeviceEject routine notifies the PnP manager that the device eject button was pressed. |
| [IoRequestDpc function](..\wmiguid\nf-wdm-iorequestdpc.md) | The IoRequestDpc routine queues a driver-supplied DpcForIsr routine to complete interrupt-driven I/O processing at a lower IRQL. |
| [IoReuseIrp function](..\wmiguid\nf-wdm-ioreuseirp.md) | The IoReuseIrp routine reinitializes an IRP so that it can be reused. |
| [IoSetActivityIdIrp function](..\wmiguid\nf-ntddk-iosetactivityidirp.md) | The IoSetActivityIdIrp routine associates an activity ID with an IRP. |
| [IoSetActivityIdThread function](..\wmiguid\nf-ntddk-iosetactivityidthread.md) | The IoSetActivityIdThread routine associates an activity ID with the current thread. Drivers should use this routine when they are tracing aware and are issuing I/O on a worker thread. |
| [IoSetCancelRoutine function](..\wmiguid\nf-wdm-iosetcancelroutine.md) | The IoSetCancelRoutine routine sets up a driver-supplied Cancel routine to be called if a given IRP is canceled. |
| [IoSetCompletionRoutine function](..\wmiguid\nf-wdm-iosetcompletionroutine.md) | The IoSetCompletionRoutine routine registers an IoCompletion routine, which will be called when the next-lower-level driver has completed the requested operation for the given IRP. |
| [IoSetCompletionRoutineEx function](..\wmiguid\nf-wdm-iosetcompletionroutineex.md) | The IoSetCompletionRoutineEx routine registers an IoCompletion routine, which is called when the next-lower-level driver has completed the requested operation for the given IRP. |
| [IoSetDeviceInterfacePropertyData function](..\wmiguid\nf-wdm-iosetdeviceinterfacepropertydata.md) | The IoSetDeviceInterfacePropertyData routine modifies the current value of a device interface property. |
| [IoSetDeviceInterfaceState function](..\wmiguid\nf-wdm-iosetdeviceinterfacestate.md) | The IoSetDeviceInterfaceState routine enables or disables an instance of a previously registered device interface class. |
| [IoSetDevicePropertyData function](..\wmiguid\nf-wdm-iosetdevicepropertydata.md) | The IoSetDevicePropertyData routine modifies the current setting for a device property. |
| [IoSetHardErrorOrVerifyDevice function](..\wmiguid\nf-ntddk-iosetharderrororverifydevice.md) | Lower-level drivers call the IoSetHardErrorOrVerifyDevice routine to identify a removable media device that has encountered an error, so that a file system driver can prompt the user to verify that the medium is valid. |
| [IoSetIoPriorityHint function](..\wmiguid\nf-wdm-iosetiopriorityhint.md) | The IoSetIoPriorityHint routine sets the priority hint value for an IRP. |
| [IoSetLinkShareAccess function](..\wmiguid\nf-wdm-iosetlinkshareaccess.md) | The IoSetLinkShareAccess routine sets the access rights for link sharing the specified file object. |
| [IoSetMasterIrpStatus function](..\wmiguid\nf-ntddk-iosetmasterirpstatus.md) | The IoSetMasterIrpStatus routine conditionally replaces the Status value in an IRP with the specified NTSTATUS value. |
| [IoSetNextIrpStackLocation function](..\wmiguid\nf-wdm-iosetnextirpstacklocation.md) | The IoSetNextIrpStackLocation routine sets the IRP stack location in a driver-allocated IRP to that of the caller. |
| [IoSetShareAccess function](..\wmiguid\nf-wdm-iosetshareaccess.md) | The IoSetShareAccess routine sets the access rights for sharing the given file object. |
| [IoSetShareAccessEx function](..\wmiguid\nf-wdm-iosetshareaccessex.md) | The IoSetShareAccessEx routine sets the access rights for sharing the specified file object. |
| [IoSetStartIoAttributes function](..\wmiguid\nf-wdm-iosetstartioattributes.md) | The IoSetStartIoAttributes routine sets attributes for the driver's StartIo routine. |
| [IoSetSystemPartition function](..\wmiguid\nf-ntddk-iosetsystempartition.md) | The IoSetSystemPartition routine sets the boot partition for the system. |
| [IoSetThreadHardErrorMode function](..\wmiguid\nf-ntddk-iosetthreadharderrormode.md) | The IoSetThreadHardErrorMode routine enables or disables hard error reporting for the current thread. |
| [IoSizeofWorkItem function](..\wmiguid\nf-wdm-iosizeofworkitem.md) | The IoSizeofWorkItem routine returns the size, in bytes, of an IO_WORKITEM structure. |
| [IoStartNextPacket function](..\wmiguid\nf-wdm-iostartnextpacket.md) | The IoStartNextPacket routine dequeues the next IRP, if any, from the given device object's associated device queue and calls the driver's StartIo routine. |
| [IoStartNextPacketByKey function](..\wmiguid\nf-wdm-iostartnextpacketbykey.md) | The IoStartNextPacketByKey routine dequeues the next I/O request packet from the specified device object's associated device queue according to a specified sort-key value and calls the driver's StartIo routine with that IRP. |
| [IoStartPacket function](..\wmiguid\nf-wdm-iostartpacket.md) | The IoStartPacket routine calls the driver's StartIo routine with the given IRP or inserts the IRP into the device queue associated with the given device object if the device is already busy. |
| [IoStartTimer function](..\wmiguid\nf-wdm-iostarttimer.md) | The IoStartTimer routine enables the timer associated with a given device object so the driver-supplied IoTimer routine is called once per second. |
| [IoStopTimer function](..\wmiguid\nf-wdm-iostoptimer.md) | The IoStopTimer routine disables the timer for a specified device object so the driver-supplied IoTimer routine is not called. |
| [IoTransferActivityId function](..\wmiguid\nf-ntddk-iotransferactivityid.md) | The IoTransferActivityId routine logs an ETW transfer event using the I/O tracing provider on behalf of the caller. This allows a driver to associate two related activity IDs without requiring a specific provider to be enabled. |
| [IoUninitializeWorkItem function](..\wmiguid\nf-wdm-iouninitializeworkitem.md) | The IoUninitializeWorkItem routine uninitializes a work item that was initialized by IoInitializeWorkItem. |
| [IoUnregisterBootDriverCallback function](..\wmiguid\nf-ntddk-iounregisterbootdrivercallback.md) | The IoUnRegisterBootDriverCallback routine unregisters a previously registered BOOT_DRIVER_CALLBACK_FUNCTION routine. |
| [IoUnregisterContainerNotification function](..\wmiguid\nf-wdm-iounregistercontainernotification.md) | The IoUnregisterContainerNotification routine cancels a container notification registration that was previously created by the IoRegisterContainerNotification routine. |
| [IoUnregisterPlugPlayNotification function](..\wmiguid\nf-wdm-iounregisterplugplaynotification.md) | This routine is obsolete in Windows 7 and later versions of Windows. For more information, see the following Remarks section.The IoUnregisterPlugPlayNotification routine removes the registration of a driver's callback routine for a PnP event. |
| [IoUnregisterPlugPlayNotificationEx function](..\wmiguid\nf-wdm-iounregisterplugplaynotificationex.md) | The IoUnregisterPlugPlayNotificationEx routine cancels the registration of a driver's callback routine for notifications of Plug and Play (PnP) events. |
| [IoUnregisterShutdownNotification function](..\wmiguid\nf-wdm-iounregistershutdownnotification.md) | The IoUnregisterShutdownNotification routine removes a registered driver from the shutdown notification queue. |
| [IoUpdateLinkShareAccess function](..\wmiguid\nf-wdm-ioupdatelinkshareaccess.md) | The IoUpdateLinkShareAccess routine updates the share access for the given file object, usually when the file is being opened. |
| [IoUpdateShareAccess function](..\wmiguid\nf-wdm-ioupdateshareaccess.md) | The IoUpdateShareAccess routine updates the share access for the given file object, usually when the file is being opened. |
| [IoValidateDeviceIoControlAccess function](..\wmiguid\nf-wdm-iovalidatedeviceiocontrolaccess.md) | For more information, see the WdmlibIoValidateDeviceIoControlAccess function. |
| [IoVerifyPartitionTable function](..\wmiguid\nf-ntddk-ioverifypartitiontable.md) | The IoVerifyPartitionTable routine checks the validity of the partition table for a disk. |
| [IoVolumeDeviceToDosName function](..\wmiguid\nf-ntddk-iovolumedevicetodosname.md) | The IoVolumeDeviceToDosName routine returns the MS-DOS path for a specified device object that represents a file system volume. |
| [IoWMIAllocateInstanceIds function](..\wmiguid\nf-wdm-iowmiallocateinstanceids.md) | The IoWMIAllocateInstanceIds routine allocates one or more instance IDs that are unique to the GUID. |
| [IoWMIDeviceObjectToInstanceName function](..\wmiguid\nf-wdm-iowmideviceobjecttoinstancename.md) | The IoWMIDeviceObjectToInstanceName routine determines the instance name for the WMI class instance implemented by the driver that is specified by a device object. |
| [IoWMIDeviceObjectToProviderId function](..\wmiguid\nf-wdm-iowmideviceobjecttoproviderid.md) | The IoWMIDeviceObjectToProviderId routine translates the specified device object into the corresponding WMI Provider ID. |
| [IoWMIExecuteMethod function](..\wmiguid\nf-wdm-iowmiexecutemethod.md) | The IoWMIExecuteMethod routine runs a WMI class method on the specified WMI data block instance. |
| [IoWMIHandleToInstanceName function](..\wmiguid\nf-wdm-iowmihandletoinstancename.md) | The IoWMIHandleToInstanceName routine determines the instance name for the WMI class instance implemented by the driver that is specified by a file handle. |
| [IoWMIOpenBlock function](..\wmiguid\nf-wdm-iowmiopenblock.md) | The IoWMIOpenBlock routine opens the WMI data block object for the specified WMI class. |
| [IoWMIQueryAllData function](..\wmiguid\nf-wdm-iowmiqueryalldata.md) | The IoWMIQueryAllData routine returns all WMI data blocks that implement a given WMI class. |
| [IoWMIQueryAllDataMultiple function](..\wmiguid\nf-wdm-iowmiqueryalldatamultiple.md) | The IoWMIQueryAllDataMultiple routine returns all WMI data blocks that implement one of a set of WMI classes. |
| [IoWMIQuerySingleInstance function](..\wmiguid\nf-wdm-iowmiquerysingleinstance.md) | The IoWMIQuerySingleInstance routine returns the specified instance of a WMI data block. |
| [IoWMIQuerySingleInstanceMultiple function](..\wmiguid\nf-wdm-iowmiquerysingleinstancemultiple.md) | The IoWMIQuerySingleInstanceMultiple routine returns all WMI data block instances that implement the specified WMI classes with the specified instance names. |
| [IoWMIRegistrationControl function](..\wmiguid\nf-wdm-iowmiregistrationcontrol.md) | The IoWMIRegistrationControl routine registers or unregisters the caller as a WMI data provider for a specified device object. |
| [IoWMISetNotificationCallback function](..\wmiguid\nf-wdm-iowmisetnotificationcallback.md) | The IoWMISetNotificationCallback routine registers a notification callback for a WMI event. |
| [IoWMISetSingleInstance function](..\wmiguid\nf-wdm-iowmisetsingleinstance.md) | The IoWMISetSingleInstance routine sets the values for properties within the data block instance that matches the specified WMI class and instance name. |
| [IoWMISetSingleItem function](..\wmiguid\nf-wdm-iowmisetsingleitem.md) | The IoWMISetSingleItem routine sets a single property in the data block instance that matches the specified WMI class and instance name. |
| [IoWMISuggestInstanceName function](..\wmiguid\nf-wdm-iowmisuggestinstancename.md) | The IoWMISuggestInstanceName routine is used to request that WMI suggest a base name which a driver can use to build WMI instance names for the device. |
| [IoWMIWriteEvent function](..\wmiguid\nf-wdm-iowmiwriteevent.md) | The IoWMIWriteEvent routine delivers a given event to the user-mode WMI components for notification. |
| [IoWithinStackLimits function](..\wmiguid\nf-wdm-iowithinstacklimits.md) | The IoWithinStackLimits routine determines whether a region of memory is within the stack limit of the current thread. |
| [IoWriteErrorLogEntry function](..\wmiguid\nf-wdm-iowriteerrorlogentry.md) | The IoWriteErrorLogEntry routine queues a given error log packet to the system error logging thread. |
| [IsListEmpty function](..\wmiguid\nf-wdm-islistempty.md) | The IsListEmpty routine indicates whether a doubly linked list of LIST_ENTRY structures is empty. |
| [KeAreAllApcsDisabled function](..\wmiguid\nf-wdm-keareallapcsdisabled.md) | The KeAreAllApcsDisabled routine indicates whether the calling thread is inside a guarded region or running at IRQL &gt;= APC_LEVEL, which disables all APC delivery. |
| [KeAreApcsDisabled function](..\wmiguid\nf-ntddk-keareapcsdisabled.md) | The KeAreApcsDisabled routine returns whether the calling thread is within a critical region or a guarded region, which disables normal kernel APC delivery. |
| [KeAreApcsDisabled function](..\wmiguid\nf-wdm-keareapcsdisabled.md) | The KeAreApcsDisabled routine returns whether the calling thread is within a critical region or a guarded region, which disables normal kernel APC delivery. |
| [KeBugCheck function](..\wmiguid\nf-ntddk-kebugcheck.md) | The KeBugCheck routine brings down the system in a controlled manner when the caller discovers an unrecoverable inconsistency that would corrupt the system if the caller continued to run. |
| [KeBugCheckEx function](..\wmiguid\nf-wdm-kebugcheckex.md) | The KeBugCheckEx routine brings down the system in a controlled manner when the caller discovers an unrecoverable inconsistency that would corrupt the system if the caller continued to run. |
| [KeCancelTimer function](..\wmiguid\nf-wdm-kecanceltimer.md) | The KeCancelTimer routine dequeues a timer object before the timer interval, if any was set, expires. |
| [KeClearEvent function](..\wmiguid\nf-wdm-keclearevent.md) | The KeClearEvent routine sets an event to a not-signaled state. |
| [KeConvertAuxiliaryCounterToPerformanceCounter function](..\wmiguid\nf-wdm-keconvertauxiliarycountertoperformancecounter.md) | The KeConvertAuxiliaryCounterToPerformanceCounter routine converts the specified auxiliary counter value into a performance counter value. |
| [KeConvertPerformanceCounterToAuxiliaryCounter function](..\wmiguid\nf-wdm-keconvertperformancecountertoauxiliarycounter.md) | The KeConvertPerformanceCounterToAuxiliaryCounter routine converts the specified performance counter value into an auxiliary counter value. |
| [KeDelayExecutionThread function](..\wmiguid\nf-wdm-kedelayexecutionthread.md) | The KeDelayExecutionThread routine puts the current thread into an alertable or nonalertable wait state for a specified interval. |
| [KeDeregisterBoundCallback function](..\wmiguid\nf-wdm-kederegisterboundcallback.md) | The KeDeregisterBoundCallback routine deregisters a user-mode bound exception callback registered by KeRegisterBoundCallback. |
| [KeDeregisterBugCheckCallback function](..\wmiguid\nf-wdm-kederegisterbugcheckcallback.md) | The KeDeregisterBugCheckCallback routine removes a callback routine that was registered by KeRegisterBugCheckCallback. |
| [KeDeregisterBugCheckReasonCallback function](..\wmiguid\nf-wdm-kederegisterbugcheckreasoncallback.md) | The KeDeregisterBugCheckReasonCallback routine removes a callback routine that was registered by KeRegisterBugCheckReasonCallback. |
| [KeDeregisterNmiCallback function](..\wmiguid\nf-wdm-kederegisternmicallback.md) | The KeDeregisterNmiCallback routine deregisters a nonmaskable interrupt (NMI) callback registered by KeRegisterNmiCallback. |
| [KeDeregisterProcessorChangeCallback function](..\wmiguid\nf-wdm-kederegisterprocessorchangecallback.md) | The KeDeregisterProcessorChangeCallback routine unregisters a callback function that was previously registered with the operating system by calling the KeRegisterProcessorChangeCallback routine. |
| [KeEnterCriticalRegion function](..\wmiguid\nf-ntddk-keentercriticalregion.md) | The KeEnterCriticalRegion routine temporarily disables the execution of normal kernel APCs, but does not prevent special kernel APCs from running. |
| [KeEnterCriticalRegion function](..\wmiguid\nf-wdm-keentercriticalregion.md) | The KeEnterCriticalRegion routine temporarily disables the execution of normal kernel APCs, but does not prevent special kernel APCs from running. |
| [KeEnterGuardedRegion function](..\wmiguid\nf-ntddk-keenterguardedregion.md) | The KeEnterGuardedRegion routine enters a guarded region, which disables all kernel-mode APC delivery to the current thread. |
| [KeEnterGuardedRegion function](..\wmiguid\nf-wdm-keenterguardedregion.md) | The KeEnterGuardedRegion routine enters a guarded region, which disables all kernel-mode APC delivery to the current thread. |
| [KeExpandKernelStackAndCallout function](..\wmiguid\nf-ntddk-keexpandkernelstackandcallout.md) | The KeExpandKernelStackAndCallout routine calls a routine with a guaranteed amount of stack space. |
| [KeFlushIoBuffers function](..\wmiguid\nf-wdm-keflushiobuffers.md) | The KeFlushIoBuffers routine flushes the memory region described by an MDL from caches of all processors. |
| [KeFlushQueuedDpcs function](..\wmiguid\nf-wdm-keflushqueueddpcs.md) | The KeFlushQueuedDpcs routine returns after all queued DPCs on all processors have executed. |
| [KeGetCurrentIrql function](..\wmiguid\nf-wdm-kegetcurrentirql.md) | The KeGetCurrentIrql routine returns the current IRQL. |
| [KeGetCurrentNodeNumber function](..\wmiguid\nf-ntddk-kegetcurrentnodenumber.md) | The KeGetCurrentNodeNumber routine gets the NUMA node number for the logical processor that the caller is running on. |
| [KeGetCurrentNodeNumber function](..\wmiguid\nf-wdm-kegetcurrentnodenumber.md) | The KeGetCurrentNodeNumber routine gets the NUMA node number for the logical processor that the caller is running on. |
| [KeGetCurrentProcessorNumber function](..\wmiguid\nf-ntddk-kegetcurrentprocessornumber.md) | The KeGetCurrentProcessorNumber routine returns the system-assigned number of the current processor on which the caller is running. |
| [KeGetCurrentProcessorNumberEx function](..\wmiguid\nf-ntddk-kegetcurrentprocessornumberex.md) | The KeGetCurrentProcessorNumberEx routine gets the processor number of the logical processor that the caller is running on. |
| [KeGetCurrentProcessorNumberEx function](..\wmiguid\nf-wdm-kegetcurrentprocessornumberex.md) | The KeGetCurrentProcessorNumberEx routine gets the processor number of the logical processor that the caller is running on. |
| [KeGetCurrentThread function](..\wmiguid\nf-wdm-kegetcurrentthread.md) | The KeGetCurrentThread routine identifies the current thread. |
| [KeGetProcessorIndexFromNumber function](..\wmiguid\nf-wdm-kegetprocessorindexfromnumber.md) | The KeGetProcessorIndexFromNumber routine converts a group number and a group-relative processor number to a systemwide processor index. |
| [KeGetProcessorNumberFromIndex function](..\wmiguid\nf-wdm-kegetprocessornumberfromindex.md) | The KeGetProcessorNumberFromIndex routine converts a systemwide processor index to a group number and a group-relative processor number. |
| [KeGetRecommendedSharedDataAlignment function](..\wmiguid\nf-wdm-kegetrecommendedshareddataalignment.md) | The KeGetRecommendedSharedDataAlignment routine returns the preferred alignment for memory structures that can be accessed by more than one processor. |
| [KeInitializeCrashDumpHeader function](..\wmiguid\nf-ntddk-keinitializecrashdumpheader.md) | The KeInitializeCrashDumpHeader routine supplies the header information the system requires for a crash dump file. |
| [KeInitializeCrashDumpHeader function](..\wmiguid\nf-wdm-keinitializecrashdumpheader.md) | The KeInitializeCrashDumpHeader routine supplies the header information the system requires for a crash dump file. |
| [KeInitializeDeviceQueue function](..\wmiguid\nf-wdm-keinitializedevicequeue.md) | The KeInitializeDeviceQueue routine initializes a device queue object to a not-busy state. |
| [KeInitializeDpc function](..\wmiguid\nf-wdm-keinitializedpc.md) | The KeInitializeDpc routine initializes a DPC object, and registers a CustomDpc routine for that object. |
| [KeInitializeEvent function](..\wmiguid\nf-wdm-keinitializeevent.md) | The KeInitializeEvent routine initializes an event object as a synchronization (single waiter) or notification type event and sets it to a signaled or not-signaled state. |
| [KeInitializeGuardedMutex function](..\wmiguid\nf-wdm-keinitializeguardedmutex.md) | The KeInitializeGuardedMutex routine initializes a guarded mutex. |
| [KeInitializeMutex function](..\wmiguid\nf-wdm-keinitializemutex.md) | The KeInitializeMutex routine initializes a mutex object, setting it to a signaled state. |
| [KeInitializeSemaphore function](..\wmiguid\nf-wdm-keinitializesemaphore.md) | The KeInitializeSemaphore routine initializes a semaphore object with a specified count and specifies an upper limit that the count can attain. |
| [KeInitializeSpinLock function](..\wmiguid\nf-wdm-keinitializespinlock.md) | The KeInitializeSpinLock routine initializes a variable of type KSPIN_LOCK. |
| [KeInitializeThreadedDpc function](..\wmiguid\nf-wdm-keinitializethreadeddpc.md) | The KeInitializeThreadedDpc routine initializes a threaded DPC object, and registers a CustomThreadedDpc routine for that object. |
| [KeInitializeTimer function](..\wmiguid\nf-wdm-keinitializetimer.md) | The KeInitializeTimer routine initializes a timer object. |
| [KeInitializeTimerEx function](..\wmiguid\nf-wdm-keinitializetimerex.md) | The KeInitializeTimerEx routine initializes an extended kernel timer object. |
| [KeInsertByKeyDeviceQueue function](..\wmiguid\nf-wdm-keinsertbykeydevicequeue.md) | The KeInsertByKeyDeviceQueue routine acquires the spin lock for the specified DeviceQueue and queues an entry according to the specified sort-key value if the device queue is set to a busy state. |
| [KeInsertDeviceQueue function](..\wmiguid\nf-wdm-keinsertdevicequeue.md) | The KeInsertDeviceQueue routine acquires the spin lock for the specified device queue object and, if the device queue is set to a busy state, queues the specified entry. |
| [KeInsertQueueDpc function](..\wmiguid\nf-wdm-keinsertqueuedpc.md) | The KeInsertQueueDpc routine queues a DPC for execution. |
| [KeInvalidateAllCaches function](..\wmiguid\nf-ntddk-keinvalidateallcaches.md) | The KeInvalidateAllCaches routine flushes all processor caches. |
| [KeIpiGenericCall function](..\wmiguid\nf-wdm-keipigenericcall.md) | The KeIpiGenericCall routine causes the specified routine to run on all processors simultaneously. |
| [KeLeaveCriticalRegion function](..\wmiguid\nf-ntddk-keleavecriticalregion.md) | The KeLeaveCriticalRegion routine reenables the delivery of normal kernel-mode APCs that were disabled by a preceding call to KeEnterCriticalRegion. |
| [KeLeaveCriticalRegion function](..\wmiguid\nf-wdm-keleavecriticalregion.md) | The KeLeaveCriticalRegion routine reenables the delivery of normal kernel-mode APCs that were disabled by a preceding call to KeEnterCriticalRegion. |
| [KeLeaveGuardedRegion function](..\wmiguid\nf-ntddk-keleaveguardedregion.md) | The KeLeaveGuardedRegion routine exits a guarded region entered by KeEnterGuardedRegion. |
| [KeLeaveGuardedRegion function](..\wmiguid\nf-wdm-keleaveguardedregion.md) | The KeLeaveGuardedRegion routine exits a guarded region entered by KeEnterGuardedRegion. |
| [KeMemoryBarrier function](..\wmiguid\nf-wdm-kememorybarrier.md) | The KeMemoryBarrier routine creates a barrier at its position in the code&#8212;across which the compiler and the processor cannot move any operations. |
| [KePulseEvent function](..\wmiguid\nf-ntddk-kepulseevent.md) | The KePulseEvent routine atomically sets an event object to a signaled state, attempts to satisfy as many waits as possible, and then resets the event object to a not-signaled state. |
| [KeQueryActiveGroupCount function](..\wmiguid\nf-ntddk-kequeryactivegroupcount.md) | The KeQueryActiveGroupCount routine returns the number of active processor groups in a multiprocessor system. |
| [KeQueryActiveGroupCount function](..\wmiguid\nf-wdm-kequeryactivegroupcount.md) | The KeQueryActiveGroupCount routine returns the number of active processor groups in a multiprocessor system. |
| [KeQueryActiveProcessorCount function](..\wmiguid\nf-ntddk-kequeryactiveprocessorcount.md) | The KeQueryActiveProcessorCount routine returns the number of currently active processors. |
| [KeQueryActiveProcessorCount function](..\wmiguid\nf-wdm-kequeryactiveprocessorcount.md) | The KeQueryActiveProcessorCount routine returns the number of currently active processors. |
| [KeQueryActiveProcessorCountEx function](..\wmiguid\nf-ntddk-kequeryactiveprocessorcountex.md) | The KeQueryActiveProcessorCountEx routine returns the number of active logical processors in a specified group in a multiprocessor system or in the entire system. |
| [KeQueryActiveProcessorCountEx function](..\wmiguid\nf-wdm-kequeryactiveprocessorcountex.md) | The KeQueryActiveProcessorCountEx routine returns the number of active logical processors in a specified group in a multiprocessor system or in the entire system. |
| [KeQueryActiveProcessors function](..\wmiguid\nf-ntddk-kequeryactiveprocessors.md) | The KeQueryActiveProcessors routine returns a bitmask of the currently active processors. |
| [KeQueryActiveProcessors function](..\wmiguid\nf-wdm-kequeryactiveprocessors.md) | The KeQueryActiveProcessors routine returns a bitmask of the currently active processors. |
| [KeQueryAuxiliaryCounterFrequency function](..\wmiguid\nf-wdm-kequeryauxiliarycounterfrequency.md) | The KeQueryAuxiliaryCounterFrequency routine returns frequency of the auxiliary counter in units of Hz. |
| [KeQueryDpcWatchdogInformation function](..\wmiguid\nf-wdm-kequerydpcwatchdoginformation.md) | The KeQueryDpcWatchdogInformation routine returns the deferred procedure call (DPC) watchdog timer values for the current processor. |
| [KeQueryGroupAffinity function](..\wmiguid\nf-ntddk-kequerygroupaffinity.md) | The KeQueryGroupAffinity routine returns an affinity mask that identifies the active logical processors in a specified group in a multiprocessor system. |
| [KeQueryGroupAffinity function](..\wmiguid\nf-wdm-kequerygroupaffinity.md) | The KeQueryGroupAffinity routine returns an affinity mask that identifies the active logical processors in a specified group in a multiprocessor system. |
| [KeQueryHardwareCounterConfiguration function](..\wmiguid\nf-ntddk-kequeryhardwarecounterconfiguration.md) | The KeQueryHardwareCounterConfiguration routine queries the operating system for the list of hardware counters to use for thread profiling. |
| [KeQueryHighestNodeNumber function](..\wmiguid\nf-ntddk-kequeryhighestnodenumber.md) | The KeQueryHighestNodeNumber routine returns the highest node number in a multiprocessor system that has a non-uniform memory access (NUMA) architecture. |
| [KeQueryHighestNodeNumber function](..\wmiguid\nf-wdm-kequeryhighestnodenumber.md) | The KeQueryHighestNodeNumber routine returns the highest node number in a multiprocessor system that has a non-uniform memory access (NUMA) architecture. |
| [KeQueryInterruptTime function](..\wmiguid\nf-wdm-kequeryinterrupttime.md) | The KeQueryInterruptTime routine returns the current value of the system interrupt time count, with accuracy to within system clock tick. |
| [KeQueryInterruptTimePrecise function](..\wmiguid\nf-wdm-kequeryinterrupttimeprecise.md) | The KeQueryInterruptTimePrecise routine returns the current value of the system interrupt time count, with accuracy to within a microsecond. |
| [KeQueryLogicalProcessorRelationship function](..\wmiguid\nf-ntddk-kequerylogicalprocessorrelationship.md) | The KeQueryLogicalProcessorRelationship routine gets information about the relationships of one or more processors to the other processors in a multiprocessor system. |
| [KeQueryLogicalProcessorRelationship function](..\wmiguid\nf-wdm-kequerylogicalprocessorrelationship.md) | The KeQueryLogicalProcessorRelationship routine gets information about the relationships of one or more processors to the other processors in a multiprocessor system. |
| [KeQueryMaximumGroupCount function](..\wmiguid\nf-ntddk-kequerymaximumgroupcount.md) | The KeQueryMaximumGroupCount routine returns the maximum number of groups in a multiprocessor system. |
| [KeQueryMaximumGroupCount function](..\wmiguid\nf-wdm-kequerymaximumgroupcount.md) | The KeQueryMaximumGroupCount routine returns the maximum number of groups in a multiprocessor system. |
| [KeQueryMaximumProcessorCount function](..\wmiguid\nf-ntddk-kequerymaximumprocessorcount.md) | The KeQueryMaximumProcessorCount routine returns the maximum number of processors. |
| [KeQueryMaximumProcessorCount function](..\wmiguid\nf-wdm-kequerymaximumprocessorcount.md) | The KeQueryMaximumProcessorCount routine returns the maximum number of processors. |
| [KeQueryMaximumProcessorCountEx function](..\wmiguid\nf-ntddk-kequerymaximumprocessorcountex.md) | The KeQueryMaximumProcessorCountEx routine returns the maximum number of logical processors in a specified group in a multiprocessor system. |
| [KeQueryMaximumProcessorCountEx function](..\wmiguid\nf-wdm-kequerymaximumprocessorcountex.md) | The KeQueryMaximumProcessorCountEx routine returns the maximum number of logical processors in a specified group in a multiprocessor system. |
| [KeQueryNodeActiveAffinity function](..\wmiguid\nf-ntddk-kequerynodeactiveaffinity.md) | The KeQueryNodeActiveAffinity routine gets the current processor affinity of a specified node in a multiprocessor system that has a non-uniform memory access (NUMA) architecture. |
| [KeQueryNodeActiveAffinity function](..\wmiguid\nf-wdm-kequerynodeactiveaffinity.md) | The KeQueryNodeActiveAffinity routine gets the current processor affinity of a specified node in a multiprocessor system that has a non-uniform memory access (NUMA) architecture. |
| [KeQueryNodeMaximumProcessorCount function](..\wmiguid\nf-ntddk-kequerynodemaximumprocessorcount.md) | The KeQueryNodeMaximumProcessorCount routine returns the maximum number of logical processors that a specified node in a non-uniform memory access (NUMA) multiprocessor system can contain. |
| [KeQueryNodeMaximumProcessorCount function](..\wmiguid\nf-wdm-kequerynodemaximumprocessorcount.md) | The KeQueryNodeMaximumProcessorCount routine returns the maximum number of logical processors that a specified node in a non-uniform memory access (NUMA) multiprocessor system can contain. |
| [KeQueryPerformanceCounter function](..\wmiguid\nf-wdm-kequeryperformancecounter.md) | The KeQueryPerformanceCounter routine retrieves the current value and frequency of the performance counter.Use KeQueryPerformanceCounter to acquire high resolution (&lt;1us) time stamps for time interval measurements. |
| [KeQueryPriorityThread function](..\wmiguid\nf-wdm-kequeryprioritythread.md) | The KeQueryPriorityThread routine returns the current priority of a particular thread. |
| [KeQueryRuntimeThread function](..\wmiguid\nf-wdm-kequeryruntimethread.md) | The KeQueryRuntimeThread routine reports the accumulated kernel-mode and user-mode run time of a thread, in clock ticks. |
| [KeQuerySystemTimePrecise function](..\wmiguid\nf-wdm-kequerysystemtimeprecise.md) | The KeQuerySystemTimePrecise routine retrieves the current system time, and is more precise than the KeQuerySystemTime routine. |
| [KeQueryTimeIncrement function](..\wmiguid\nf-wdm-kequerytimeincrement.md) | The KeQueryTimeIncrement routine returns the number of 100-nanosecond units that are added to the system time each time the interval clock interrupts. |
| [KeQueryTotalCycleTimeThread function](..\wmiguid\nf-wdm-kequerytotalcycletimethread.md) | The KeQueryTotalCycleTimeThread routine returns the accumulated cycle time for the specified thread. |
| [KeQueryUnbiasedInterruptTime function](..\wmiguid\nf-wdm-kequeryunbiasedinterrupttime.md) | The KeQueryUnbiasedInterruptTime routine returns the current value of the system interrupt time count. |
| [KeRaiseIrqlToDpcLevel function](..\wmiguid\nf-ntddk-keraiseirqltodpclevel.md) | The KeRaiseIrqlToDpcLevel routine raises the hardware priority to IRQL = DISPATCH_LEVEL, thereby masking off interrupts of equivalent or lower IRQL on the current processor. |
| [KeRaiseIrqlToDpcLevel function](..\wmiguid\nf-wdm-keraiseirqltodpclevel.md) | The KeRaiseIrqlToDpcLevel routine raises the hardware priority to IRQL = DISPATCH_LEVEL, thereby masking off interrupts of equivalent or lower IRQL on the current processor. |
| [KeReadStateEvent function](..\wmiguid\nf-wdm-kereadstateevent.md) | The KeReadStateEvent routine returns the current state, signaled or not-signaled, of an event object. |
| [KeReadStateMutex function](..\wmiguid\nf-wdm-kereadstatemutex.md) | The KeReadStateMutex routine returns the current state, signaled or not-signaled, of the specified mutex object. |
| [KeReadStateSemaphore function](..\wmiguid\nf-wdm-kereadstatesemaphore.md) | The KeReadStateSemaphore routine returns the current state, signaled or not-signaled, of the specified semaphore object. |
| [KeReadStateTimer function](..\wmiguid\nf-wdm-kereadstatetimer.md) | The KeReadStateTimer routine reads the current state of a timer object. |
| [KeRegisterBoundCallback function](..\wmiguid\nf-wdm-keregisterboundcallback.md) | The KeRegisterBoundCallback routine registers a routine to be called whenever a user-mode bound exception occurs. |
| [KeRegisterBugCheckCallback function](..\wmiguid\nf-wdm-keregisterbugcheckcallback.md) | The KeRegisterBugCheckCallback routine registers a BugCheckCallback routine, which executes when the operating system issues a bug check. |
| [KeRegisterBugCheckReasonCallback function](..\wmiguid\nf-wdm-keregisterbugcheckreasoncallback.md) | The KeRegisterBugCheckReasonCallback routine registers a BugCheckDumpIoCallback, BugCheckSecondaryDumpDataCallback, or BugCheckAddPagesCallback routine, which executes when the operating system issues a bug check. |
| [KeRegisterNmiCallback function](..\wmiguid\nf-wdm-keregisternmicallback.md) | The KeRegisterNmiCallback routine registers a routine to be called whenever a nonmaskable interrupt (NMI) occurs. |
| [KeRegisterProcessorChangeCallback function](..\wmiguid\nf-wdm-keregisterprocessorchangecallback.md) | The KeRegisterProcessorChangeCallback routine registers a callback function with the operating system so that the operating system will notify the driver when a new processor is added to the hardware partition. |
| [KeReleaseMutex function](..\wmiguid\nf-wdm-kereleasemutex.md) | The KeReleaseMutex routine releases a mutex object, and specifies whether the caller is to call one of the KeWaitXxx routines as soon as KeReleaseMutex returns control. |
| [KeReleaseSemaphore function](..\wmiguid\nf-wdm-kereleasesemaphore.md) | The KeReleaseSemaphore routine releases the specified semaphore object. |
| [KeRemoveByKeyDeviceQueue function](..\wmiguid\nf-wdm-keremovebykeydevicequeue.md) | The KeRemoveByKeyDeviceQueue routine removes an entry, selected according to a sort key value, from the specified device queue. |
| [KeRemoveDeviceQueue function](..\wmiguid\nf-wdm-keremovedevicequeue.md) | The KeRemoveDeviceQueue routine removes an entry from the head of a specified device queue. |
| [KeRemoveEntryDeviceQueue function](..\wmiguid\nf-wdm-keremoveentrydevicequeue.md) | The KeRemoveEntryDeviceQueue routine returns whether the specified entry is in the device queue and removes it, if it was queued, from the device queue. |
| [KeRemoveQueueDpc function](..\wmiguid\nf-wdm-keremovequeuedpc.md) | The KeRemoveQueueDpc routine removes the specified DPC object from the system DPC queue. |
| [KeResetEvent function](..\wmiguid\nf-wdm-keresetevent.md) | The KeResetEvent routine resets a specified event object to a not-signaled state and returns the previous state of that event object. |
| [KeRestoreExtendedProcessorState function](..\wmiguid\nf-wdm-kerestoreextendedprocessorstate.md) | The KeRestoreExtendedProcessorState routine restores extended processor state information that was previously saved. |
| [KeRestoreFloatingPointState function](..\wmiguid\nf-wdm-kerestorefloatingpointstate.md) | The KeRestoreFloatingPointState routine restores the nonvolatile floating-point context saved by the preceding call to KeSaveFloatingPointState. |
| [KeRevertToUserAffinityThreadEx function](..\wmiguid\nf-wdm-kereverttouseraffinitythreadex.md) | The KeRevertToUserAffinityThreadEx routine restores the previous affinity of the current thread. |
| [KeRevertToUserGroupAffinityThread function](..\wmiguid\nf-wdm-kereverttousergroupaffinitythread.md) | The KeRevertToUserGroupAffinityThread routine restores the group affinity of the calling thread to its original value at the time that the thread was created. |
| [KeSaveExtendedProcessorState function](..\wmiguid\nf-wdm-kesaveextendedprocessorstate.md) | The KeSaveExtendedProcessorState routine saves extended processor state information. |
| [KeSaveFloatingPointState function](..\wmiguid\nf-wdm-kesavefloatingpointstate.md) | The KeSaveFloatingPointState routine saves the nonvolatile floating-point context so the caller can carry out floating-point operations. |
| [KeSetBasePriorityThread function](..\wmiguid\nf-ntddk-kesetbaseprioritythread.md) | The KeSetBasePriorityThread routine sets the run-time priority, relative to the current process, for a given thread. |
| [KeSetCoalescableTimer function](..\wmiguid\nf-wdm-kesetcoalescabletimer.md) | The KeSetCoalescableTimer routine sets the initial expiration time and period of a timer object and specifies how much delay can be tolerated in the expiration times. |
| [KeSetEvent function](..\wmiguid\nf-wdm-kesetevent.md) | The KeSetEvent routine sets an event object to a signaled state if the event was not already signaled, and returns the previous state of the event object. |
| [KeSetHardwareCounterConfiguration function](..\wmiguid\nf-ntddk-kesethardwarecounterconfiguration.md) | The KeSetHardwareCounterConfiguration routine specifies a list of hardware counters to use for thread profiling. |
| [KeSetImportanceDpc function](..\wmiguid\nf-ntddk-kesetimportancedpc.md) | The KeSetImportanceDpc routine specifies how soon the DPC routine is run. |
| [KeSetImportanceDpc function](..\wmiguid\nf-wdm-kesetimportancedpc.md) | The KeSetImportanceDpc routine specifies how soon the DPC routine is run. |
| [KeSetPriorityThread function](..\wmiguid\nf-wdm-kesetprioritythread.md) | The KeSetPriorityThread routine sets the run-time priority of a driver-created thread. |
| [KeSetSystemAffinityThread function](..\wmiguid\nf-wdm-kesetsystemaffinitythread.md) | The KeSetSystemAffinityThread routine sets the system affinity of the current thread. |
| [KeSetSystemAffinityThreadEx function](..\wmiguid\nf-wdm-kesetsystemaffinitythreadex.md) | The KeSetSystemAffinityThreadEx routine sets the system affinity of the current thread. |
| [KeSetSystemGroupAffinityThread function](..\wmiguid\nf-wdm-kesetsystemgroupaffinitythread.md) | The KeSetSystemGroupAffinityThread routine changes the group number and affinity mask of the calling thread. |
| [KeSetTargetProcessorDpc function](..\wmiguid\nf-ntddk-kesettargetprocessordpc.md) | The KeSetTargetProcessorDpc routine specifies the processor that a DPC routine will be run on. |
| [KeSetTargetProcessorDpc function](..\wmiguid\nf-wdm-kesettargetprocessordpc.md) | The KeSetTargetProcessorDpc routine specifies the processor that a DPC routine will be run on. |
| [KeSetTargetProcessorDpcEx function](..\wmiguid\nf-wdm-kesettargetprocessordpcex.md) | The KeSetTargetProcessorDpcEx routine specifies the processor that a DPC routine will run on. |
| [KeSetTimer function](..\wmiguid\nf-wdm-kesettimer.md) | The KeSetTimer routine sets the absolute or relative interval at which a timer object is to be set to a signaled state and, optionally, supplies a CustomTimerDpc routine to be executed when that interval expires. |
| [KeSetTimerEx function](..\wmiguid\nf-wdm-kesettimerex.md) | The KeSetTimerEx routine sets the absolute or relative interval at which a timer object is to be set to a signaled state, optionally supplies a CustomTimerDpc routine to be executed when that interval expires, and optionally supplies a recurring interval for the timer. |
| [KeStallExecutionProcessor function](..\wmiguid\nf-wdm-kestallexecutionprocessor.md) | The KeStallExecutionProcessor routine stalls the caller on the current processor for a specified time interval. |
| [KeSynchronizeExecution function](..\wmiguid\nf-wdm-kesynchronizeexecution.md) | The KeSynchronizeExecution routine synchronizes the execution of the specified routine with the interrupt service routine (ISR) that is assigned to a set of one or more interrupt objects. |
| [KeTestSpinLock function](..\wmiguid\nf-wdm-ketestspinlock.md) | The KeTestSpinLock routine tests for the availability of a spin lock. |
| [KeTryToAcquireGuardedMutex function](..\wmiguid\nf-wdm-ketrytoacquireguardedmutex.md) | The KeTryToAcquireGuardedMutex routine acquires a guarded mutex, if available. |
| [KeTryToAcquireSpinLockAtDpcLevel function](..\wmiguid\nf-wdm-ketrytoacquirespinlockatdpclevel.md) | The KeTryToAcquireSpinLockAtDpcLevel routine attempts to acquire a spin lock at DISPATCH_LEVEL. |
| [KeWaitForMultipleObjects function](..\wmiguid\nf-wdm-kewaitformultipleobjects.md) | The KeWaitForMultipleObjects routine puts the current thread into an alertable or nonalertable wait state until any or all of a number of dispatcher objects are set to a signaled state or (optionally) until the wait times out. |
| [KeWaitForSingleObject function](..\wmiguid\nf-wdm-kewaitforsingleobject.md) | The KeWaitForSingleObject routine puts the current thread into a wait state until the given dispatcher object is set to a signaled state or (optionally) until the wait times out. |
| [MmAdvanceMdl function](..\wmiguid\nf-wdm-mmadvancemdl.md) | The MmAdvanceMdl routine advances the beginning of an MDL's virtual memory range by the specified number of bytes. |
| [MmAllocateContiguousMemory function](..\wmiguid\nf-ntddk-mmallocatecontiguousmemory.md) | The MmAllocateContiguousMemory routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space. |
| [MmAllocateContiguousMemory function](..\wmiguid\nf-wdm-mmallocatecontiguousmemory.md) | The MmAllocateContiguousMemory routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space. |
| [MmAllocateContiguousMemorySpecifyCache function](..\wmiguid\nf-ntddk-mmallocatecontiguousmemoryspecifycache.md) | The MmAllocateContiguousMemorySpecifyCache routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space. |
| [MmAllocateContiguousMemorySpecifyCache function](..\wmiguid\nf-wdm-mmallocatecontiguousmemoryspecifycache.md) | The MmAllocateContiguousMemorySpecifyCache routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space. |
| [MmAllocateContiguousMemorySpecifyCacheNode function](..\wmiguid\nf-ntddk-mmallocatecontiguousmemoryspecifycachenode.md) | The MmAllocateContiguousMemorySpecifyCacheNode routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space. |
| [MmAllocateContiguousMemorySpecifyCacheNode function](..\wmiguid\nf-wdm-mmallocatecontiguousmemoryspecifycachenode.md) | The MmAllocateContiguousMemorySpecifyCacheNode routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space. |
| [MmAllocateContiguousNodeMemory function](..\wmiguid\nf-ntddk-mmallocatecontiguousnodememory.md) | The MmAllocateContiguousNodeMemory routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space. |
| [MmAllocateContiguousNodeMemory function](..\wmiguid\nf-wdm-mmallocatecontiguousnodememory.md) | The MmAllocateContiguousNodeMemory routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space. |
| [MmAllocateMappingAddress function](..\wmiguid\nf-wdm-mmallocatemappingaddress.md) | The MmAllocateMappingAddress routine reserves a range of system virtual address space of the specified size. |
| [MmAllocateMdlForIoSpace function](..\wmiguid\nf-wdm-mmallocatemdlforiospace.md) | The MmAllocateMdlForIoSpace routine allocates an MDL and initializes this MDL to describe a set of physical address ranges in I/O address space. |
| [MmAllocateNodePagesForMdlEx function](..\wmiguid\nf-wdm-mmallocatenodepagesformdlex.md) | The MmAllocateNodePagesForMdlEx routine allocates nonpaged physical memory from an ideal node, and allocates an MDL structure to describe this memory. |
| [MmAllocateNonCachedMemory function](..\wmiguid\nf-ntddk-mmallocatenoncachedmemory.md) | The MmAllocateNonCachedMemory routine allocates a virtual address range of noncached and cache-aligned memory. |
| [MmAllocatePagesForMdl function](..\wmiguid\nf-wdm-mmallocatepagesformdl.md) | The MmAllocatePagesForMdl routine allocates zero-filled, nonpaged, physical memory pages to an MDL. |
| [MmAllocatePagesForMdlEx function](..\wmiguid\nf-wdm-mmallocatepagesformdlex.md) | The MmAllocatePagesForMdlEx routine allocates nonpaged, physical memory pages to an MDL. |
| [MmBuildMdlForNonPagedPool function](..\wmiguid\nf-wdm-mmbuildmdlfornonpagedpool.md) | The MmBuildMdlForNonPagedPool routine receives an MDL that specifies a nonpaged virtual memory buffer, and updates it to describe the underlying physical pages. |
| [MmCopyMemory function](..\wmiguid\nf-ntddk-mmcopymemory.md) | The MmCopyMemory routine copies the specified range of virtual or physical memory into the caller-supplied buffer. |
| [MmFreeContiguousMemory function](..\wmiguid\nf-ntddk-mmfreecontiguousmemory.md) | The MmFreeContiguousMemory routine releases a range of physically contiguous memory that was allocated by an MmAllocateContiguousMemoryXxx routine. |
| [MmFreeContiguousMemory function](..\wmiguid\nf-wdm-mmfreecontiguousmemory.md) | The MmFreeContiguousMemory routine releases a range of physically contiguous memory that was allocated by an MmAllocateContiguousMemoryXxx routine. |
| [MmFreeContiguousMemorySpecifyCache function](..\wmiguid\nf-ntddk-mmfreecontiguousmemoryspecifycache.md) | The MmFreeContiguousMemorySpecifyCache routine frees a buffer that was allocated by an MmAllocateContiguousMemorySpecifyCacheXxx routine. |
| [MmFreeContiguousMemorySpecifyCache function](..\wmiguid\nf-wdm-mmfreecontiguousmemoryspecifycache.md) | The MmFreeContiguousMemorySpecifyCache routine frees a buffer that was allocated by an MmAllocateContiguousMemorySpecifyCacheXxx routine. |
| [MmFreeMappingAddress function](..\wmiguid\nf-wdm-mmfreemappingaddress.md) | The MmFreeMappingAddress routine frees a range of virtual memory reserved by the MmAllocateMappingAddress routine. |
| [MmFreeNonCachedMemory function](..\wmiguid\nf-ntddk-mmfreenoncachedmemory.md) | The MmFreeNonCachedMemory routine releases a range of noncached memory that was allocated by the MmAllocateNonCachedMemory routine. |
| [MmFreePagesFromMdl function](..\wmiguid\nf-wdm-mmfreepagesfrommdl.md) | The MmFreePagesFromMdl routine frees all the physical pages that are described by an MDL that was created by the MmAllocatePagesForMdl routine. |
| [MmGetPhysicalAddress function](..\wmiguid\nf-ntddk-mmgetphysicaladdress.md) | The MmGetPhysicalAddress routine returns the physical address corresponding to a valid nonpaged virtual address. |
| [MmGetSystemRoutineAddress function](..\wmiguid\nf-wdm-mmgetsystemroutineaddress.md) | The MmGetSystemRoutineAddress routine returns a pointer to a function specified by SystemRoutineName. |
| [MmIsAddressValid function](..\wmiguid\nf-ntddk-mmisaddressvalid.md) | The MmIsAddressValid routine checks whether a page fault will occur for a read or write operation at a given virtual address.Warning  We do not recommend using this function. |
| [MmIsDriverSuspectForVerifier function](..\wmiguid\nf-wdm-mmisdriversuspectforverifier.md) | The MmIsDriverSuspectForVerifier routine indicates whether the driver represented by the specified driver object is in the list of drivers that are selected to be verified by Driver Verifier. |
| [MmIsDriverVerifying function](..\wmiguid\nf-wdm-mmisdriververifying.md) | The MmIsDriverVerifying routine indicates whether the kernel-mode driver that is identified by the specified driver object is being verified or calls a driver that is being verified by Driver Verifier. |
| [MmIsDriverVerifyingByAddress function](..\wmiguid\nf-wdm-mmisdriververifyingbyaddress.md) | The MmIsDriverVerifyingByAddress routine checks whether the kernel-mode driver that is identified by the specified image address is being verified or calls a driver that is being verified by Driver Verifier. |
| [MmIsThisAnNtAsSystem function](..\wmiguid\nf-ntddk-mmisthisanntassystem.md) | The MmIsThisAnNtAsSystem routine is obsolete for Windows XP and later versions of Windows. Use RtlGetVersion or RtlVerifyVersionInfo instead. |
| [MmLockPagableDataSection function](..\wmiguid\nf-wdm-mmlockpagabledatasection.md) | The MmLockPagableDataSection routine locks an entire section of driver data into system space. |
| [MmLockPagableSectionByHandle function](..\wmiguid\nf-ntddk-mmlockpagablesectionbyhandle.md) | The MmLockPagableSectionByHandle routine locks a pageable code or data section into system memory by incrementing the reference count on the handle to the section. |
| [MmMapIoSpace function](..\wmiguid\nf-wdm-mmmapiospace.md) | The MmMapIoSpace routine maps the given physical address range to nonpaged system space. |
| [MmMapIoSpaceEx function](..\wmiguid\nf-wdm-mmmapiospaceex.md) | The MmMapIoSpaceEx routine maps the given physical address range to non-paged system space using the specified page protection. |
| [MmMapLockedPages function](..\wmiguid\nf-wdm-mmmaplockedpages.md) | The MmMapLockedPages routine is obsolete for Windows 2000 and later versions of Windows, and for Windows Me. |
| [MmMapLockedPagesSpecifyCache function](..\wmiguid\nf-wdm-mmmaplockedpagesspecifycache.md) | The MmMapLockedPagesSpecifyCache routine maps the physical pages that are described by an MDL to a virtual address, and enables the caller to specify the cache attribute that is used to create the mapping. |
| [MmMapLockedPagesWithReservedMapping function](..\wmiguid\nf-wdm-mmmaplockedpageswithreservedmapping.md) | The MmMapLockedPagesWithReservedMapping routine maps all or part of an address range that was previously reserved by the MmAllocateMappingAddress routine. |
| [MmMapMdl function](..\wmiguid\nf-wdm-mmmapmdl.md) | This function maps physical pages described by a memory descriptor list (MDL) into the system virtual address space. |
| [MmPageEntireDriver function](..\wmiguid\nf-wdm-mmpageentiredriver.md) | The MmPageEntireDriver routine causes all of a driver's code and data to be made pageable, overriding the attributes of the various sections that make up the driver's image. |
| [MmProbeAndLockPages function](..\wmiguid\nf-wdm-mmprobeandlockpages.md) | The MmProbeAndLockPages routine probes the specified virtual memory pages, makes them resident, and locks them in memory. |
| [MmProbeAndLockSelectedPages function](..\wmiguid\nf-wdm-mmprobeandlockselectedpages.md) | The MmProbeAndLockSelectedPages routine probes the selected virtual memory pages, makes them resident, and locks them in memory. |
| [MmProtectMdlSystemAddress function](..\wmiguid\nf-wdm-mmprotectmdlsystemaddress.md) | The MmProtectMdlSystemAddress routine sets the protection type for a memory address range. |
| [MmQuerySystemSize function](..\wmiguid\nf-wdm-mmquerysystemsize.md) | The MmQuerySystemSize routine returns an estimate of the amount of memory in the system. |
| [MmResetDriverPaging function](..\wmiguid\nf-wdm-mmresetdriverpaging.md) | The MmResetDriverPaging routine resets the pageable status of a driver's sections to that specified when the driver was compiled. |
| [MmSecureVirtualMemory function](..\wmiguid\nf-ntddk-mmsecurevirtualmemory.md) | The MmSecureVirtualMemory routine secures a user-space memory address range so that it cannot be freed and its protection type cannot be made more restrictive. |
| [MmSizeOfMdl function](..\wmiguid\nf-wdm-mmsizeofmdl.md) | The MmSizeOfMdl routine returns the number of bytes to allocate for an MDL describing a given address range. |
| [MmUnlockPagableImageSection function](..\wmiguid\nf-wdm-mmunlockpagableimagesection.md) | The MmUnlockPagableImageSection routine releases a section of driver code or driver data, previously locked into system space with MmLockPagableCodeSection, MmLockPagableDataSection or MmLockPagableSectionByHandle, so the section can be paged out again. |
| [MmUnlockPages function](..\wmiguid\nf-wdm-mmunlockpages.md) | The MmUnlockPages routine unlocks the physical pages that are described by the specified memory descriptor list (MDL). |
| [MmUnmapIoSpace function](..\wmiguid\nf-wdm-mmunmapiospace.md) | The MmUnmapIoSpace routine unmaps a specified range of physical addresses previously mapped by MmMapIoSpace. |
| [MmUnmapLockedPages function](..\wmiguid\nf-wdm-mmunmaplockedpages.md) | The MmUnmapLockedPages routine releases a mapping that was set up by a preceding call to the MmMapLockedPages or MmMapLockedPagesSpecifyCache routine. |
| [MmUnmapReservedMapping function](..\wmiguid\nf-wdm-mmunmapreservedmapping.md) | The MmUnmapReservedMapping routine unmaps a memory buffer that was mapped by the MmMapLockedPagesWithReservedMapping routine. |
| [MmUnsecureVirtualMemory function](..\wmiguid\nf-ntddk-mmunsecurevirtualmemory.md) | The MmUnsecureVirtualMemory routine unsecures a memory address range secured by the MmSecureVirtualMemory routine. |
| [NtCommitComplete function](..\wmiguid\nf-wdm-ntcommitcomplete.md) | The ZwCommitComplete routine notifies KTM that the calling resource manager has finished committing a transaction's data. |
| [NtCommitEnlistment function](..\wmiguid\nf-wdm-ntcommitenlistment.md) | The ZwCommitEnlistment routine initiates the commit operation for a specified enlistment's transaction. |
| [NtCommitTransaction function](..\wmiguid\nf-wdm-ntcommittransaction.md) | The ZwCommitTransaction routine initiates a commit operation for a specified transaction. |
| [NtCreateEnlistment function](..\wmiguid\nf-wdm-ntcreateenlistment.md) | The ZwCreateEnlistment routine creates a new enlistment object for a transaction. |
| [NtCreateResourceManager function](..\wmiguid\nf-wdm-ntcreateresourcemanager.md) | The ZwCreateResourceManager routine creates a resource manager object. |
| [NtCreateTransaction function](..\wmiguid\nf-wdm-ntcreatetransaction.md) | The ZwCreateTransaction routine creates a transaction object. |
| [NtCreateTransactionManager function](..\wmiguid\nf-wdm-ntcreatetransactionmanager.md) | The ZwCreateTransactionManager routine creates a new transaction manager object. |
| [NtEnumerateTransactionObject function](..\wmiguid\nf-wdm-ntenumeratetransactionobject.md) | The ZwEnumerateTransactionObject routine enumerates the KTM objects on a computer. |
| [NtGetNotificationResourceManager function](..\wmiguid\nf-wdm-ntgetnotificationresourcemanager.md) | The ZwGetNotificationResourceManager routine retrieves the next transaction notification from a specified resource manager's notification queue. |
| [NtOpenEnlistment function](..\wmiguid\nf-wdm-ntopenenlistment.md) | The ZwOpenEnlistment routine obtains a handle to an existing enlistment object. |
| [NtOpenProcess function](..\wmiguid\nf-ntddk-ntopenprocess.md) | The ZwOpenProcess routine opens a handle to a process object and sets the access rights to this object. |
| [NtOpenResourceManager function](..\wmiguid\nf-wdm-ntopenresourcemanager.md) | The ZwOpenResourceManager routine returns a handle to an existing resource manager object. |
| [NtOpenTransaction function](..\wmiguid\nf-wdm-ntopentransaction.md) | The ZwOpenTransaction routine obtains a handle to an existing transaction object. |
| [NtOpenTransactionManager function](..\wmiguid\nf-wdm-ntopentransactionmanager.md) | The ZwOpenTransactionManager routine obtains a handle to an existing transaction manager object. |
| [NtPowerInformation function](..\wmiguid\nf-ntpoapi-ntpowerinformation.md) | The ZwPowerInformation routine sets or retrieves system power information. |
| [NtPowerInformation function](..\wmiguid\nf-wdm-ntpowerinformation.md) | The ZwPowerInformation routine sets or retrieves system power information. |
| [NtPrePrepareComplete function](..\wmiguid\nf-wdm-ntprepreparecomplete.md) | The ZwPrePrepareComplete routine notifies KTM that the calling resource manager has finished preliminary preparation of a transaction's data. |
| [NtPrePrepareEnlistment function](..\wmiguid\nf-wdm-ntpreprepareenlistment.md) | The ZwPrePrepareEnlistment routine initiates the pre-prepare operation for a specified enlistment's transaction. |
| [NtPrepareComplete function](..\wmiguid\nf-wdm-ntpreparecomplete.md) | The ZwPrepareComplete routine notifies KTM that the calling resource manager has finished preparing a transaction's data. |
| [NtPrepareEnlistment function](..\wmiguid\nf-wdm-ntprepareenlistment.md) | The ZwPrepareEnlistment routine initiates the prepare operation for a specified enlistment's transaction. |
| [NtQueryInformationEnlistment function](..\wmiguid\nf-wdm-ntqueryinformationenlistment.md) | The ZwQueryInformationEnlistment routine retrieves information about a specified enlistment object. |
| [NtQueryInformationResourceManager function](..\wmiguid\nf-wdm-ntqueryinformationresourcemanager.md) | The ZwQueryInformationResourceManager routine retrieves information about a specified resource manager object. |
| [NtQueryInformationTransaction function](..\wmiguid\nf-wdm-ntqueryinformationtransaction.md) | The ZwQueryInformationTransaction routine retrieves information about a specified transaction. |
| [NtQueryInformationTransactionManager function](..\wmiguid\nf-wdm-ntqueryinformationtransactionmanager.md) | The ZwQueryInformationTransactionManager routine retrieves information about a specified transaction manager object. |
| [NtReadOnlyEnlistment function](..\wmiguid\nf-wdm-ntreadonlyenlistment.md) | The ZwReadOnlyEnlistment routine sets a specified enlistment to be read-only. |
| [NtRecoverEnlistment function](..\wmiguid\nf-wdm-ntrecoverenlistment.md) | The ZwRecoverEnlistment routine initiates a recovery operation for the transaction that is associated with a specified enlistment. |
| [NtRecoverResourceManager function](..\wmiguid\nf-wdm-ntrecoverresourcemanager.md) | The ZwRecoverResourceManager routine tries to recover the transaction that is associated with each enlistment of a specified resource manager object. |
| [NtRecoverTransactionManager function](..\wmiguid\nf-wdm-ntrecovertransactionmanager.md) | The ZwRecoverTransactionManager routine reconstructs the state of the transaction manager object (including all transactions, enlistments, and resource managers) from the recovery information that is in the log stream. |
| [NtRenameTransactionManager function](..\wmiguid\nf-wdm-ntrenametransactionmanager.md) | The NtRenameTransactionManager routine changes the identity of the transaction manager object that is stored in the CLFS log file stream contained in the log file name. |
| [NtRollbackComplete function](..\wmiguid\nf-wdm-ntrollbackcomplete.md) | The ZwRollbackComplete routine notifies KTM that the calling resource manager has finished rolling back a transaction's data. |
| [NtRollbackEnlistment function](..\wmiguid\nf-wdm-ntrollbackenlistment.md) | The ZwRollbackEnlistment routine rolls back the transaction that is associated with a specified enlistment. |
| [NtRollbackTransaction function](..\wmiguid\nf-wdm-ntrollbacktransaction.md) | The ZwRollbackTransaction routine initiates a rollback operation for a specified transaction. |
| [NtRollforwardTransactionManager function](..\wmiguid\nf-wdm-ntrollforwardtransactionmanager.md) | The ZwRollforwardTransactionManager routine initiates recovery operations for all of the in-progress transactions that are assigned to a specified transaction manager. |
| [NtSetInformationEnlistment function](..\wmiguid\nf-wdm-ntsetinformationenlistment.md) | The ZwSetInformationEnlistment routine sets information for a specified enlistment object. |
| [NtSetInformationResourceManager function](..\wmiguid\nf-wdm-ntsetinformationresourcemanager.md) | The ZwSetInformationResourceManager routine is not used. |
| [NtSetInformationTransaction function](..\wmiguid\nf-wdm-ntsetinformationtransaction.md) | The ZwSetInformationTransaction routine sets information for a specified transaction. |
| [NtSetInformationTransactionManager function](..\wmiguid\nf-wdm-ntsetinformationtransactionmanager.md) | Do not call this routine from kernel-mode code. |
| [NtSinglePhaseReject function](..\wmiguid\nf-wdm-ntsinglephasereject.md) | The ZwSinglePhaseReject routine informs KTM that the calling resource manager will not support single-phase commit operations for a specified enlistment. |
| [ObCloseHandle function](..\wmiguid\nf-wdm-obclosehandle.md) | The ObCloseHandle routine closes an object handle. |
| [ObDereferenceObjectDeferDelete function](..\wmiguid\nf-wdm-obdereferenceobjectdeferdelete.md) | The ObDereferenceObjectDeferDelete routine decrements the reference count for the given object, checks for object retention, and avoids deadlocks. |
| [ObDereferenceObjectDeferDeleteWithTag function](..\wmiguid\nf-wdm-obdereferenceobjectdeferdeletewithtag.md) | The ObDereferenceObjectDeferDeleteWithTag routine decrements the reference count for the specified object, defers deletion of the object to avoid deadlocks, and writes a four-byte tag value to the object to support object reference tracing. |
| [ObGetObjectSecurity function](..\wmiguid\nf-wdm-obgetobjectsecurity.md) | The ObGetObjectSecurity routine gets the security descriptor for a given object. |
| [ObReferenceObjectByHandle function](..\wmiguid\nf-wdm-obreferenceobjectbyhandle.md) | The ObReferenceObjectByHandle routine provides access validation on the object handle, and, if access can be granted, returns the corresponding pointer to the object's body. |
| [ObReferenceObjectByHandleWithTag function](..\wmiguid\nf-wdm-obreferenceobjectbyhandlewithtag.md) | The ObReferenceObjectByHandleWithTag routine increments the reference count of the object that is identified by the specified handle, and writes a four-byte tag value to the object to support object reference tracing. |
| [ObReferenceObjectByPointer function](..\wmiguid\nf-wdm-obreferenceobjectbypointer.md) | The ObReferenceObjectByPointer routine increments the pointer reference count for a given object. |
| [ObReferenceObjectByPointerWithTag function](..\wmiguid\nf-wdm-obreferenceobjectbypointerwithtag.md) | The ObReferenceObjectByPointerWithTag routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing. |
| [ObRegisterCallbacks function](..\wmiguid\nf-wdm-obregistercallbacks.md) | The ObRegisterCallbacks routine registers a list of callback routines for thread, process, and desktop handle operations. |
| [ObReleaseObjectSecurity function](..\wmiguid\nf-wdm-obreleaseobjectsecurity.md) | The ObReleaseObjectSecurity routine is the reciprocal to ObGetObjectSecurity. |
| [ObUnRegisterCallbacks function](..\wmiguid\nf-wdm-obunregistercallbacks.md) | The ObUnRegisterCallbacks routine unregisters a set of callback routines that were registered with the ObRegisterCallbacks routine. |
| [ObfReferenceObject function](..\wmiguid\nf-wdm-obfreferenceobject.md) | The ObReferenceObject routine increments the reference count to the given object. |
| [PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function](..\wmiguid\nf-pep_x-pep_acpi_initialize_extended_io_resource.md) | The PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_EXTENDED_ADDRESS structure. |
| [PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function](..\wmiguid\nf-pepfx-pep_acpi_initialize_extended_io_resource.md) | The PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_EXTENDED_ADDRESS structure. |
| [PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function](..\wmiguid\nf-pep_x-pep_acpi_initialize_extended_memory_resource.md) | The PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_EXTENDED_ADDRESS structure. |
| [PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function](..\wmiguid\nf-pepfx-pep_acpi_initialize_extended_memory_resource.md) | The PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_EXTENDED_ADDRESS structure. |
| [PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function](..\wmiguid\nf-pep_x-pep_acpi_initialize_gpio_int_resource.md) | The PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_GPIO_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function](..\wmiguid\nf-pepfx-pep_acpi_initialize_gpio_int_resource.md) | The PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_GPIO_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE function](..\wmiguid\nf-pep_x-pep_acpi_initialize_gpio_io_resource.md) | The PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_GPIO_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE function](..\wmiguid\nf-pepfx-pep_acpi_initialize_gpio_io_resource.md) | The PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_GPIO_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function](..\wmiguid\nf-pep_x-pep_acpi_initialize_interrupt_resource.md) | The PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_INTERRUPT_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function](..\wmiguid\nf-pepfx-pep_acpi_initialize_interrupt_resource.md) | The PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_INTERRUPT_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function](..\wmiguid\nf-pep_x-pep_acpi_initialize_ioport_resource.md) | The PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_IO_MEMORY_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function](..\wmiguid\nf-pepfx-pep_acpi_initialize_ioport_resource.md) | The PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_IO_MEMORY_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function](..\wmiguid\nf-pep_x-pep_acpi_initialize_memory_resource.md) | The PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_IO_MEMORY_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function](..\wmiguid\nf-pepfx-pep_acpi_initialize_memory_resource.md) | The PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_IO_MEMORY_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function](..\wmiguid\nf-pep_x-pep_acpi_initialize_spb_i2c_resource.md) | The PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_I2C_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function](..\wmiguid\nf-pepfx-pep_acpi_initialize_spb_i2c_resource.md) | The PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_I2C_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function](..\wmiguid\nf-pep_x-pep_acpi_initialize_spb_spi_resource.md) | The PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_SPI_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function](..\wmiguid\nf-pepfx-pep_acpi_initialize_spb_spi_resource.md) | The PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_SPI_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function](..\wmiguid\nf-pep_x-pep_acpi_initialize_spb_uart_resource.md) | The PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_UART_RESOURCE structure. |
| [PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function](..\wmiguid\nf-pepfx-pep_acpi_initialize_spb_uart_resource.md) | The PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_UART_RESOURCE structure. |
| [PoCallDriver function](..\wmiguid\nf-wdm-pocalldriver.md) | The PoCallDriver routine passes a power IRP to the next-lower driver in the device stack. (Windows Server 2003, Windows XP, and Windows 2000 only.). |
| [PoClearPowerRequest function](..\wmiguid\nf-wdm-poclearpowerrequest.md) | The PoClearPowerRequest routine decrements the count for the specified power request type. |
| [PoCreatePowerRequest function](..\wmiguid\nf-wdm-pocreatepowerrequest.md) | The PoCreatePowerRequest routine creates a power request object. |
| [PoDeletePowerRequest function](..\wmiguid\nf-wdm-podeletepowerrequest.md) | The PoDeletePowerRequest routine deletes a power request object. |
| [PoEndDeviceBusy function](..\wmiguid\nf-wdm-poenddevicebusy.md) | The PoEndDeviceBusy routine marks the end of a period of time in which the device is busy. |
| [PoFxActivateComponent function](..\wmiguid\nf-wdm-pofxactivatecomponent.md) | The PoFxActivateComponent routine increments the activation reference count on the specified component. |
| [PoFxCompleteDevicePowerNotRequired function](..\wmiguid\nf-wdm-pofxcompletedevicepowernotrequired.md) | The PoFxCompleteDevicePowerNotRequired routine notifies the power management framework (PoFx) that the calling driver has completed its response to a call to the driver's DevicePowerNotRequiredCallback callback routine. |
| [PoFxCompleteIdleCondition function](..\wmiguid\nf-wdm-pofxcompleteidlecondition.md) | The PoFxCompleteIdleCondition routine informs the power management framework (PoFx) that the specified component has completed a pending change to the idle condition. |
| [PoFxCompleteIdleState function](..\wmiguid\nf-wdm-pofxcompleteidlestate.md) | The PoFxCompleteIdleState routine informs the power management framework (PoFx) that the specified component has completed a pending change to an Fx state. |
| [PoFxIdleComponent function](..\wmiguid\nf-wdm-pofxidlecomponent.md) | The PoFxIdleComponent routine decrements the activation reference count on the specified component. |
| [PoFxIssueComponentPerfStateChange function](..\wmiguid\nf-wdm-pofxissuecomponentperfstatechange.md) | The PoFxIssueComponentPerfStateChange routine submits a request to place a device component in a particular performance state. |
| [PoFxIssueComponentPerfStateChangeMultiple function](..\wmiguid\nf-wdm-pofxissuecomponentperfstatechangemultiple.md) | The PoFxIssueComponentPerfStateChangeMultiple routine submits a request to change the performance states in multiple performance state sets simultaneously for a device component. |
| [PoFxNotifySurprisePowerOn function](..\wmiguid\nf-wdm-pofxnotifysurprisepoweron.md) | The PoFxNotifySurprisePowerOn routine notifies the power management framework (PoFx) that a device was turned on as a side effect of supplying power to some other device. |
| [PoFxPowerControl function](..\wmiguid\nf-wdm-pofxpowercontrol.md) | The PoFxPowerControl routine sends a power control request to the power management framework (PoFx). |
| [PoFxPowerOnCrashdumpDevice function](..\wmiguid\nf-wdm-pofxpoweroncrashdumpdevice.md) | The PoFxPowerOnCrashdumpDevice routine requests that a crash-dump device be turned on. |
| [PoFxQueryCurrentComponentPerfState function](..\wmiguid\nf-wdm-pofxquerycurrentcomponentperfstate.md) | The PoFxQueryCurrentComponentPerfState routine retrieves the active performance state in a component's performance state set. |
| [PoFxRegisterComponentPerfStates function](..\wmiguid\nf-wdm-pofxregistercomponentperfstates.md) | The PoFxRegisterComponentPerfStates routine registers a device component for performance state management by the power management framework (PoFx). |
| [PoFxRegisterCoreDevice function](..\wmiguid\nf-pep_x-pofxregistercoredevice.md) | The PoFxRegisterCoreDevice routine registers a new core system resource with the Windows power management framework (PoFx). |
| [PoFxRegisterCoreDevice function](..\wmiguid\nf-pepfx-pofxregistercoredevice.md) | The PoFxRegisterCoreDevice routine registers a new core system resource with the Windows power management framework (PoFx). |
| [PoFxRegisterCrashdumpDevice function](..\wmiguid\nf-wdm-pofxregistercrashdumpdevice.md) | The PoFxRegisterCrashdumpDevice routine registers a crash-dump device. |
| [PoFxRegisterDevice function](..\wmiguid\nf-wdm-pofxregisterdevice.md) | The PoFxRegisterDevice routine registers a device with the power management framework (PoFx). |
| [PoFxRegisterPlugin function](..\wmiguid\nf-pep_x-pofxregisterplugin.md) | The PoFxRegisterPlugin routine registers a platform extension plug-in (PEP) with the Windows power management framework (PoFx). |
| [PoFxRegisterPlugin function](..\wmiguid\nf-pepfx-pofxregisterplugin.md) | The PoFxRegisterPlugin routine registers a platform extension plug-in (PEP) with the Windows power management framework (PoFx). |
| [PoFxRegisterPluginEx function](..\wmiguid\nf-pep_x-pofxregisterpluginex.md) | The PoFxRegisterPluginEx routine registers a platform extension plug-in (PEP) with the Windows power management framework (PoFx). |
| [PoFxRegisterPluginEx function](..\wmiguid\nf-pepfx-pofxregisterpluginex.md) | The PoFxRegisterPluginEx routine registers a platform extension plug-in (PEP) with the Windows power management framework (PoFx). |
| [PoFxReportDevicePoweredOn function](..\wmiguid\nf-wdm-pofxreportdevicepoweredon.md) | The PoFxReportDevicePoweredOn routine notifies the power management framework (PoFx) that the device completed the requested transition to the D0 (fully on) power state. |
| [PoFxSetComponentLatency function](..\wmiguid\nf-wdm-pofxsetcomponentlatency.md) | The PoFxSetComponentLatency routine specifies the maximum latency that can be tolerated in the transition from the idle condition to the active condition in the specified component. |
| [PoFxSetComponentResidency function](..\wmiguid\nf-wdm-pofxsetcomponentresidency.md) | The PoFxSetComponentResidency routine sets the estimated time for how long a component is likely to remain idle after the component enters the idle condition. |
| [PoFxSetComponentWake function](..\wmiguid\nf-wdm-pofxsetcomponentwake.md) | The PoFxSetComponentWake routine indicates whether the driver arms the specified component to wake whenever the component enters the idle condition. |
| [PoFxSetDeviceIdleTimeout function](..\wmiguid\nf-wdm-pofxsetdeviceidletimeout.md) | The PoFxSetDeviceIdleTimeout routine specifies the minimum time interval from when the last component of the device enters the idle condition to when the power management framework (PoFx) calls the driver's DevicePowerNotRequiredCallback routine. |
| [PoFxSetTargetDripsDevicePowerState function](..\wmiguid\nf-wdm-pofxsettargetdripsdevicepowerstate.md) | This routine is called to notify the power manager of the device's target device power state for DRIPS. The driver can override the DRIPS constraint provided by the PEP. |
| [PoFxStartDevicePowerManagement function](..\wmiguid\nf-wdm-pofxstartdevicepowermanagement.md) | The PoFxStartDevicePowerManagement routine completes the registration of a device with the power management framework (PoFx) and starts device power management. |
| [PoFxUnregisterDevice function](..\wmiguid\nf-wdm-pofxunregisterdevice.md) | The PoFxUnregisterDevice routine removes the registration of a device from the power management framework (PoFx). |
| [PoGetSystemWake function](..\wmiguid\nf-wdm-pogetsystemwake.md) | The PoGetSystemWake routine determines whether a specified IRP has been marked as waking the system from a sleeping state. |
| [PoQueryWatchdogTime function](..\wmiguid\nf-wdm-poquerywatchdogtime.md) | The PoQueryWatchdogTime routine indicates whether the power manager has enabled a watchdog time-out counter for any power IRP that is currently assigned to the device stack. |
| [PoRegisterDeviceForIdleDetection function](..\wmiguid\nf-wdm-poregisterdeviceforidledetection.md) | The PoRegisterDeviceForIdleDetection routine enables or cancels idle detection and sets idle time-out values for a device. |
| [PoRegisterPowerSettingCallback function](..\wmiguid\nf-wdm-poregisterpowersettingcallback.md) | The PoRegisterPowerSettingCallback routine registers a power-setting callback routine to receive notifications of changes in the specified power setting. |
| [PoRegisterSystemState function](..\wmiguid\nf-wdm-poregistersystemstate.md) | The PoRegisterSystemState routine registers the system as busy due to certain activity. |
| [PoRequestPowerIrp function](..\wmiguid\nf-wdm-porequestpowerirp.md) | The PoRequestPowerIrp routine allocates a power IRP and sends it to the top driver in the device stack for the specified device. |
| [PoSetDeviceBusyEx function](..\wmiguid\nf-wdm-posetdevicebusyex.md) | The PoSetDeviceBusyEx routine notifies the power manager that the device associated with the specified idle counter is busy. |
| [PoSetPowerRequest function](..\wmiguid\nf-wdm-posetpowerrequest.md) | The PoSetPowerRequest routine increments the count for the specified power request type. |
| [PoSetPowerState function](..\wmiguid\nf-wdm-posetpowerstate.md) | The PoSetPowerState routine notifies the system of a change in the device power state for a device. |
| [PoSetSystemState function](..\wmiguid\nf-wdm-posetsystemstate.md) | Drivers call the PoSetSystemState routine to indicate that the system is active. |
| [PoSetSystemWake function](..\wmiguid\nf-wdm-posetsystemwake.md) | The PoSetSystemWake routine marks the specified IRP as one that contributed to waking the system from a sleep state. |
| [PoStartDeviceBusy function](..\wmiguid\nf-wdm-postartdevicebusy.md) | The PoStartDeviceBusy routine marks the start of a period of time in which the device is busy. |
| [PoStartNextPowerIrp function](..\wmiguid\nf-wdm-postartnextpowerirp.md) | The PoStartNextPowerIrp routine signals the power manager that the driver is ready to handle the next power IRP. (Windows Server 2003, Windows XP, and Windows 2000 only.). |
| [PoUnregisterPowerSettingCallback function](..\wmiguid\nf-wdm-pounregisterpowersettingcallback.md) | The PoUnregisterPowerSettingCallback routine unregisters a power-setting callback routine that a driver previously registered by calling the PoRegisterPowerSettingCallback routine. |
| [PoUnregisterSystemState function](..\wmiguid\nf-wdm-pounregistersystemstate.md) | The PoUnregisterSystemState routine cancels a system state registration created by PoRegisterSystemState. |
| [PopEntryList function](..\wmiguid\nf-wdm-popentrylist.md) | The PopEntryList routine removes the first entry from a singly linked list of SINGLE_LIST_ENTRY structures. |
| [ProbeForRead function](..\wmiguid\nf-wdm-probeforread.md) | The ProbeForRead routine checks that a user-mode buffer actually resides in the user portion of the address space, and is correctly aligned. |
| [ProbeForWrite function](..\wmiguid\nf-wdm-probeforwrite.md) | The ProbeForWrite routine checks that a user-mode buffer actually resides in the user-mode portion of the address space, is writable, and is correctly aligned. |
| [PsAllocSiloContextSlot function](..\wmiguid\nf-ntddk-psallocsilocontextslot.md) | This routine allocates a slot that can be used to insert, retrieve, and delete an object in all silos. . |
| [PsAttachSiloToCurrentThread function](..\wmiguid\nf-ntddk-psattachsilotocurrentthread.md) | This routine places a thread temporarily into the specified Silo. |
| [PsCreateSiloContext function](..\wmiguid\nf-ntddk-pscreatesilocontext.md) | This routine creates an object that will be inserted in a Silo. |
| [PsCreateSystemThread function](..\wmiguid\nf-wdm-pscreatesystemthread.md) | The PsCreateSystemThread routine creates a system thread that executes in kernel mode and returns a handle for the thread. |
| [PsDereferenceSiloContext function](..\wmiguid\nf-ntddk-psdereferencesilocontext.md) | This routine decrements the reference count on the object. |
| [PsDetachSiloFromCurrentThread function](..\wmiguid\nf-ntddk-psdetachsilofromcurrentthread.md) | This routine removes a thread from a silo which was added by an attach. For more info about attaching, see the PsAttachSiloToCurrentThread routine. |
| [PsFreeSiloContextSlot function](..\wmiguid\nf-ntddk-psfreesilocontextslot.md) | This routine frees the specified slot and makes it available in the system. It undoes the effects of the PsAllocSiloContextSlot routine. |
| [PsGetCurrentProcessId function](..\wmiguid\nf-ntddk-psgetcurrentprocessid.md) | The PsGetCurrentProcessId routine identifies the current thread's process. |
| [PsGetCurrentServerSilo function](..\wmiguid\nf-ntddk-psgetcurrentserversilo.md) | This routine returns the effective server silo for the thread. |
| [PsGetCurrentSilo function](..\wmiguid\nf-ntddk-psgetcurrentsilo.md) | This routine returns the current silo for the calling thread. First the thread is checked to see if it has been attached to a silo. If not, then the thread is checked to see if it is in a silo. |
| [PsGetCurrentThread function](..\wmiguid\nf-ntddk-psgetcurrentthread.md) | The PsGetCurrentThread routine identifies the current thread. |
| [PsGetCurrentThread function](..\wmiguid\nf-wdm-psgetcurrentthread.md) | The PsGetCurrentThread routine identifies the current thread. |
| [PsGetCurrentThreadId function](..\wmiguid\nf-ntddk-psgetcurrentthreadid.md) | The PsGetCurrentThreadId routine identifies the current thread. |
| [PsGetCurrentThreadTeb function](..\wmiguid\nf-ntddk-psgetcurrentthreadteb.md) | The PsGetCurrentThreadTeb routine returns the Thread Environment Block (TEB) of the current thread. The call must be made in kernel-mode. |
| [PsGetEffectiveServerSilo function](..\wmiguid\nf-ntddk-psgeteffectiveserversilo.md) | This routine traverses the parent chain of the Silo until finding the effective server silo or host silo. |
| [PsGetHostSilo function](..\wmiguid\nf-ntddk-psgethostsilo.md) | This routine returns the host silo. |
| [PsGetJobServerSilo function](..\wmiguid\nf-ntddk-psgetjobserversilo.md) | This routine returns the effective ServerSilo for the job. The returned pointer is valid as long as the supplied Job object remains referenced. |
| [PsGetJobSilo function](..\wmiguid\nf-ntddk-psgetjobsilo.md) | This routine returns the first job in the hierarchy that is a Silo. The returned pointer is valid as long as the supplied Job object remains referenced. |
| [PsGetParentSilo function](..\wmiguid\nf-ntddk-psgetparentsilo.md) | Retrieves the most immediate parent silo in the hierarchy for a given job object. |
| [PsGetPermanentSiloContext function](..\wmiguid\nf-ntddk-psgetpermanentsilocontext.md) | This routine retrieves an object that was inserted in the Silo without incrementing the reference count. |
| [PsGetProcessCreateTimeQuadPart function](..\wmiguid\nf-ntddk-psgetprocesscreatetimequadpart.md) | The PsGetProcessCreateTimeQuadPart routine returns a LONGLONG value that represents the time at which the process was created. |
| [PsGetProcessId function](..\wmiguid\nf-ntddk-psgetprocessid.md) | The PsGetProcessId routine returns the process identifier (process ID) that is associated with a specified process. |
| [PsGetServerSiloActiveConsoleId function](..\wmiguid\nf-ntddk-psgetserversiloactiveconsoleid.md) | Gets the active console for the current server silo context for the supplied thread. |
| [PsGetSiloContext function](..\wmiguid\nf-ntddk-psgetsilocontext.md) | This routine retrieves the silo context from the specified silo and slot. |
| [PsGetSiloMonitorContextSlot function](..\wmiguid\nf-ntddk-psgetsilomonitorcontextslot.md) | This routine returns the silo context slot that was allocated by the monitor during the registration. |
| [PsGetVersion function](..\wmiguid\nf-wdm-psgetversion.md) | This function is obsolete in Windows XP and later versions of the Windows operating system. Use RtlGetVersion instead.PsGetVersion returns caller-selected information about the current version of the NT-based operating system. |
| [PsInsertPermanentSiloContext function](..\wmiguid\nf-ntddk-psinsertpermanentsilocontext.md) | This routine inserts an object in an empty slot in a Silo. |
| [PsInsertSiloContext function](..\wmiguid\nf-ntddk-psinsertsilocontext.md) | This routine inserts an object in an empty slot in a Silo. |
| [PsIsHostSilo function](..\wmiguid\nf-ntddk-psishostsilo.md) | This routine will check if the supplied Silo is the host silo. |
| [PsMakeSiloContextPermanent function](..\wmiguid\nf-ntddk-psmakesilocontextpermanent.md) | This routine makes the slot in a silo instance read-only, allowing the object in the slot to be retrieved without affecting the reference count on that object. |
| [PsQueryTotalCycleTimeProcess function](..\wmiguid\nf-wdm-psquerytotalcycletimeprocess.md) | The PsQueryTotalCycleTimeProcess routine returns the accumulated cycle time for the specified process. |
| [PsReferenceSiloContext function](..\wmiguid\nf-ntddk-psreferencesilocontext.md) | This routine increments the reference count on the object. |
| [PsRegisterSiloMonitor function](..\wmiguid\nf-ntddk-psregistersilomonitor.md) | This routine registers a server silo monitor that can receive notifications about server silo events. |
| [PsRemoveCreateThreadNotifyRoutine function](..\wmiguid\nf-ntddk-psremovecreatethreadnotifyroutine.md) | The PsRemoveCreateThreadNotifyRoutine routine removes a callback routine that was registered by the PsSetCreateThreadNotifyRoutine routine. |
| [PsRemoveLoadImageNotifyRoutine function](..\wmiguid\nf-ntddk-psremoveloadimagenotifyroutine.md) | The PsRemoveLoadImageNotifyRoutine routine removes a callback routine that was registered by the PsSetLoadImageNotifyRoutine routine. |
| [PsRemoveSiloContext function](..\wmiguid\nf-ntddk-psremovesilocontext.md) | This routine removes an object that was inserted in the Silo. |
| [PsReplaceSiloContext function](..\wmiguid\nf-ntddk-psreplacesilocontext.md) | This routine inserts an object in a Silo. |
| [PsSetCreateProcessNotifyRoutine function](..\wmiguid\nf-ntddk-pssetcreateprocessnotifyroutine.md) | The PsSetCreateProcessNotifyRoutine routine adds a driver-supplied callback routine to, or removes it from, a list of routines to be called whenever a process is created or deleted. |
| [PsSetCreateProcessNotifyRoutineEx function](..\wmiguid\nf-ntddk-pssetcreateprocessnotifyroutineex.md) | The PsSetCreateProcessNotifyRoutineEx routine registers or removes a callback routine that notifies the caller when a process is created or exits. |
| [PsSetCreateProcessNotifyRoutineEx2 function](..\wmiguid\nf-ntddk-pssetcreateprocessnotifyroutineex2.md) | The PsSetCreateProcessNotifyRoutineEx2 routine registers or removes a callback routine that notifies the caller when a process is created or deleted. |
| [PsSetCreateThreadNotifyRoutine function](..\wmiguid\nf-ntddk-pssetcreatethreadnotifyroutine.md) | The PsSetCreateThreadNotifyRoutine routine registers a driver-supplied callback that is subsequently notified when a new thread is created and when such a thread is deleted. |
| [PsSetCreateThreadNotifyRoutineEx function](..\wmiguid\nf-ntddk-pssetcreatethreadnotifyroutineex.md) | The PsSetCreateThreadNotifyRoutineEx routine registers a driver-supplied callback that is subsequently notified when a new thread is created and when such a thread is deleted. |
| [PsSetLoadImageNotifyRoutine function](..\wmiguid\nf-ntddk-pssetloadimagenotifyroutine.md) | The PsSetLoadImageNotifyRoutine routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory). |
| [PsSetLoadImageNotifyRoutineEx function](..\wmiguid\nf-ntddk-pssetloadimagenotifyroutineex.md) | The PsSetLoadImageNotifyRoutineEx routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory). |
| [PsStartSiloMonitor function](..\wmiguid\nf-ntddk-psstartsilomonitor.md) | This routine tries to start the server silo monitor. |
| [PsTerminateServerSilo function](..\wmiguid\nf-ntddk-psterminateserversilo.md) | This routine terminates the specified silo. |
| [PsTerminateSystemThread function](..\wmiguid\nf-wdm-psterminatesystemthread.md) | The PsTerminateSystemThread routine terminates the current system thread. |
| [PsUnregisterSiloMonitor function](..\wmiguid\nf-ntddk-psunregistersilomonitor.md) | This routine unregisters a server silo monitor. |
| [PushEntryList function](..\wmiguid\nf-wdm-pushentrylist.md) | The PushEntryList routine inserts an entry at the beginning of a singly linked list of SINGLE_LIST_ENTRY structures. |
| [PwmParsePinPath function](..\wmiguid\nf-pwmutil-pwmparsepinpath.md) | Parses a pin path under the Pulse Width Modulation (PWM) controller namespace to validate its format and extract the pin number. |
| [READ_PORT_BUFFER_UCHAR function](..\wmiguid\nf-wdm-read_port_buffer_uchar.md) | The READ_PORT_BUFFER_UCHAR routine reads a number of bytes from the specified port address into a buffer. |
| [READ_PORT_BUFFER_ULONG function](..\wmiguid\nf-wdm-read_port_buffer_ulong.md) | The READ_PORT_BUFFER_ULONG routine reads a number of ULONG values from the specified port address into a buffer. |
| [READ_PORT_BUFFER_USHORT function](..\wmiguid\nf-wdm-read_port_buffer_ushort.md) | The READ_PORT_BUFFER_USHORT routine reads a number of USHORT values from the specified port address into a buffer. |
| [READ_PORT_UCHAR function](..\wmiguid\nf-ioaccess-read_port_uchar.md) | The READ_PORT_UCHAR routine reads a byte from the specified port address. |
| [READ_PORT_UCHAR function](..\wmiguid\nf-wdm-read_port_uchar.md) | The READ_PORT_UCHAR routine reads a byte from the specified port address. |
| [READ_PORT_ULONG function](..\wmiguid\nf-ioaccess-read_port_ulong.md) | The READ_PORT_ULONG routine reads a ULONG value from the specified port address. |
| [READ_PORT_ULONG function](..\wmiguid\nf-wdm-read_port_ulong.md) | The READ_PORT_ULONG routine reads a ULONG value from the specified port address. |
| [READ_PORT_USHORT function](..\wmiguid\nf-ioaccess-read_port_ushort.md) | The READ_PORT_USHORT routine reads a USHORT value from the specified port address. |
| [READ_PORT_USHORT function](..\wmiguid\nf-wdm-read_port_ushort.md) | The READ_PORT_USHORT routine reads a USHORT value from the specified port address. |
| [READ_REGISTER_BUFFER_UCHAR function](..\wmiguid\nf-wdm-read_register_buffer_uchar.md) | The READ_REGISTER_BUFFER_UCHAR routine reads a number of bytes from the specified register address into a buffer. |
| [READ_REGISTER_BUFFER_ULONG function](..\wmiguid\nf-wdm-read_register_buffer_ulong.md) | The READ_REGISTER_BUFFER_ULONG routine reads a number of ULONG values from the specified register address into a buffer. |
| [READ_REGISTER_BUFFER_USHORT function](..\wmiguid\nf-wdm-read_register_buffer_ushort.md) | The READ_REGISTER_BUFFER_USHORT routine reads a number of USHORT values from the specified register address into a buffer. |
| [READ_REGISTER_UCHAR function](..\wmiguid\nf-wdm-read_register_uchar.md) | The READ_REGISTER_UCHAR routine reads a byte from the specified register address. |
| [READ_REGISTER_ULONG function](..\wmiguid\nf-wdm-read_register_ulong.md) | The READ_REGISTER_ULONG routine reads a ULONG value from the specified register address. |
| [READ_REGISTER_USHORT function](..\wmiguid\nf-wdm-read_register_ushort.md) | The READ_REGISTER_USHORT routine reads a USHORT value from the specified register address. |
| [RemoveEntryList function](..\wmiguid\nf-wdm-removeentrylist.md) | The RemoveEntryList routine removes an entry from a doubly linked list of LIST_ENTRY structures. |
| [RemoveHeadList function](..\wmiguid\nf-wdm-removeheadlist.md) | The RemoveHeadList routine removes an entry from the beginning of a doubly linked list of LIST_ENTRY structures. |
| [RemoveTailList function](..\wmiguid\nf-wdm-removetaillist.md) | The RemoveTailList routine removes an entry from the end of a doubly linked list of LIST_ENTRY structures. |
| [RtlAnsiStringToUnicodeString function](..\wmiguid\nf-wdm-rtlansistringtounicodestring.md) | RtlAnsiStringToUnicodeString converts the given ANSI source string into a Unicode string. |
| [RtlAppendUnicodeStringToString function](..\wmiguid\nf-wdm-rtlappendunicodestringtostring.md) | The RtlAppendUnicodeStringToString routine concatenates two Unicode strings. |
| [RtlAppendUnicodeToString function](..\wmiguid\nf-wdm-rtlappendunicodetostring.md) | The RtlAppendUnicodeToString routine concatenates the supplied Unicode string to a buffered Unicode string. |
| [RtlAreBitsClear function](..\wmiguid\nf-wdm-rtlarebitsclear.md) | The RtlAreBitsClear routine determines whether a given range of bits within a bitmap variable is clear. |
| [RtlAreBitsSet function](..\wmiguid\nf-wdm-rtlarebitsset.md) | The RtlAreBitsSet routine determines whether a given range of bits within a bitmap variable is set. |
| [RtlByteToChar function](..\wmiguid\nf-ntintsafe-rtlbytetochar.md) | Converts a value of type BYTE to a value of type CHAR. |
| [RtlByteToInt8 function](..\wmiguid\nf-ntintsafe-rtlbytetoint8.md) | Converts a value of type BYTE to a value of type INT8. |
| [RtlCharToInteger function](..\wmiguid\nf-ntddk-rtlchartointeger.md) | The RtlCharToInteger routine converts a single-byte character string to an integer value in the specified base. |
| [RtlCheckRegistryKey function](..\wmiguid\nf-wdm-rtlcheckregistrykey.md) | The RtlCheckRegistryKey routine checks for the existence of a given named key in the registry. |
| [RtlClearAllBits function](..\wmiguid\nf-wdm-rtlclearallbits.md) | The RtlClearAllBits routine sets all bits in a given bitmap variable to zero. |
| [RtlClearBit function](..\wmiguid\nf-wdm-rtlclearbit.md) | The RtlClearBit routine sets the specified bit in a bitmap to zero. |
| [RtlClearBits function](..\wmiguid\nf-wdm-rtlclearbits.md) | The RtlClearBits routine sets all bits in the specified range of bits in the bitmap to zero. |
| [RtlCmDecodeMemIoResource function](..\wmiguid\nf-wdm-rtlcmdecodememioresource.md) | The RtlCmDecodeMemIoResource routine provides the starting address and length of a CM_PARTIAL_RESOURCE_DESCRIPTOR structure that describes a range of memory or I/O port addresses. |
| [RtlCmEncodeMemIoResource function](..\wmiguid\nf-wdm-rtlcmencodememioresource.md) | The RtlCmEncodeMemIoResource routine updates a CM_PARTIAL_RESOURCE_DESCRIPTOR structure to describe a range of memory or I/O port addresses. |
| [RtlCompareMemory function](..\wmiguid\nf-wdm-rtlcomparememory.md) | The RtlCompareMemory routine compares two blocks of memory and returns the number of bytes that match. |
| [RtlCompareString function](..\wmiguid\nf-ntddk-rtlcomparestring.md) | The RtlCompareString routine compares two counted strings. |
| [RtlCompareUnicodeString function](..\wmiguid\nf-wdm-rtlcompareunicodestring.md) | The RtlCompareUnicodeString routine compares two Unicode strings. |
| [RtlConvertLongToLargeInteger function](..\wmiguid\nf-wdm-rtlconvertlongtolargeinteger.md) | The RtlConvertLongToLargeInteger routine converts the input signed integer to a signed large integer. |
| [RtlConvertLongToLuid function](..\wmiguid\nf-ntddk-rtlconvertlongtoluid.md) | The RtlConvertLongToLuid routine converts a long integer to a locally unique identifier (LUID), which is used by the system to represent a security privilege. |
| [RtlConvertUlongToLargeInteger function](..\wmiguid\nf-wdm-rtlconvertulongtolargeinteger.md) | The RtlConvertUlongToLargeInteger routine converts the input unsigned integer to a signed large integer. For Windows XP and later versions of Windows, do not use this routine; use the native support for __int64. |
| [RtlConvertUlongToLuid function](..\wmiguid\nf-ntddk-rtlconvertulongtoluid.md) | The RtlConvertUlongToLuid routine converts an unsigned long integer to a locally unique identifier (LUID), which is used by the system to represent a security privilege. |
| [RtlCopyString function](..\wmiguid\nf-ntddk-rtlcopystring.md) | The RtlCopyString routine copies a source string to a destination string. |
| [RtlCopyUnicodeString function](..\wmiguid\nf-wdm-rtlcopyunicodestring.md) | The RtlCopyUnicodeString routine copies a source string to a destination string. |
| [RtlCreateRegistryKey function](..\wmiguid\nf-wdm-rtlcreateregistrykey.md) | The RtlCreateRegistryKey routine adds a key object in the registry along a given relative path. |
| [RtlCreateSecurityDescriptor function](..\wmiguid\nf-wdm-rtlcreatesecuritydescriptor.md) | The RtlCreateSecurityDescriptor routine initializes a new absolute-format security descriptor. On return, the security descriptor is initialized with no system ACL, no discretionary ACL, no owner, no primary group, and all control flags set to zero. |
| [RtlDWordPtrAdd function](..\wmiguid\nf-ntintsafe-rtldwordptradd.md) | Adds two values of type DWORD_PTR. |
| [RtlDWordPtrMult function](..\wmiguid\nf-ntintsafe-rtldwordptrmult.md) | Multiplies one value of type DWORD_PTR by another. |
| [RtlDWordPtrSub function](..\wmiguid\nf-ntintsafe-rtldwordptrsub.md) | Subtracts one value of type DWORD_PTR from another. |
| [RtlDeleteRegistryValue function](..\wmiguid\nf-wdm-rtldeleteregistryvalue.md) | The RtlDeleteRegistryValue routine removes the specified entry name and the associated values from the registry along the given relative path. |
| [RtlDowncaseUnicodeChar function](..\wmiguid\nf-wdm-rtldowncaseunicodechar.md) | The RtlDowncaseUnicodeChar routine converts the specified Unicode character to lowercase. |
| [RtlEqualString function](..\wmiguid\nf-ntddk-rtlequalstring.md) | The RtlEqualString routine compares two counted strings to determine whether they are equal. |
| [RtlEqualUnicodeString function](..\wmiguid\nf-wdm-rtlequalunicodestring.md) | The RtlEqualUnicodeString routine compares two Unicode strings to determine whether they are equal. |
| [RtlExtendCorrelationVector function](..\wmiguid\nf-ntddk-rtlextendcorrelationvector.md) | This routine extends the supplied correlation vector. For a correlation vector of the form X.i, the extended value is X.i.0. |
| [RtlFindClearBits function](..\wmiguid\nf-wdm-rtlfindclearbits.md) | The RtlFindClearBits routine searches for a range of clear bits of a requested size within a bitmap. |
| [RtlFindClearBitsAndSet function](..\wmiguid\nf-wdm-rtlfindclearbitsandset.md) | The RtlFindClearBitsAndSet routine searches for a range of clear bits of a requested size within a bitmap and sets all bits in the range when it has been located. |
| [RtlFindClearRuns function](..\wmiguid\nf-wdm-rtlfindclearruns.md) | The RtlFindClearRuns routine finds the specified number of runs of clear bits within a given bitmap. |
| [RtlFindFirstRunClear function](..\wmiguid\nf-wdm-rtlfindfirstrunclear.md) | The RtlFindFirstRunClear routine searches for the initial contiguous range of clear bits within a given bitmap. |
| [RtlFindLastBackwardRunClear function](..\wmiguid\nf-wdm-rtlfindlastbackwardrunclear.md) | The RtlFindLastBackwardRunClear routine searches a given bitmap for the preceding clear run of bits, starting from the specified index position. |
| [RtlFindLeastSignificantBit function](..\wmiguid\nf-wdm-rtlfindleastsignificantbit.md) | The RtlFindLeastSignificantBit routine returns the zero-based position of the least significant nonzero bit in its parameter. |
| [RtlFindLongestRunClear function](..\wmiguid\nf-wdm-rtlfindlongestrunclear.md) | The RtlFindLongestRunClear routine searches for the largest contiguous range of clear bits within a given bitmap. |
| [RtlFindMostSignificantBit function](..\wmiguid\nf-wdm-rtlfindmostsignificantbit.md) | The RtlFindMostSignificantBit routine returns the zero-based position of the most significant nonzero bit in its parameter. |
| [RtlFindNextForwardRunClear function](..\wmiguid\nf-wdm-rtlfindnextforwardrunclear.md) | The RtlFindNextForwardRunClear routine searches a given bitmap variable for the next clear run of bits, starting from the specified index position. |
| [RtlFindSetBits function](..\wmiguid\nf-wdm-rtlfindsetbits.md) | The RtlFindSetBits routine searches for a range of set bits of a requested size within a bitmap. |
| [RtlFindSetBitsAndClear function](..\wmiguid\nf-wdm-rtlfindsetbitsandclear.md) | The RtlFindSetBitsAndClear routine searches for a range of set bits of a requested size within a bitmap and clears all bits in the range when it has been located. |
| [RtlFreeAnsiString function](..\wmiguid\nf-wdm-rtlfreeansistring.md) | The RtlFreeAnsiString routine releases storage that was allocated by RtlUnicodeStringToAnsiString. |
| [RtlFreeUnicodeString function](..\wmiguid\nf-wdm-rtlfreeunicodestring.md) | The RtlFreeUnicodeString routine releases storage that was allocated by RtlAnsiStringToUnicodeString or RtlUpcaseUnicodeString. |
| [RtlGUIDFromString function](..\wmiguid\nf-wdm-rtlguidfromstring.md) | The RtlGUIDFromString routine converts the given Unicode string to a GUID in binary format. |
| [RtlGetEnabledExtendedFeatures function](..\wmiguid\nf-ntddk-rtlgetenabledextendedfeatures.md) | The RtlGetEnabledExtendedFeatures routine returns a mask of extended processor features that are enabled by the system. |
| [RtlGetVersion function](..\wmiguid\nf-wdm-rtlgetversion.md) | The RtlGetVersion routine returns version information about the currently running operating system. |
| [RtlHashUnicodeString function](..\wmiguid\nf-wdm-rtlhashunicodestring.md) | The RtlHashUnicodeString routine creates a hash value from a given Unicode string and hash algorithm. |
| [RtlIncrementCorrelationVector function](..\wmiguid\nf-ntddk-rtlincrementcorrelationvector.md) | Increments the specified correlation vector. For a correlation vector of the form X.i, the incremented value is be X.(i+1). |
| [RtlInitAnsiString function](..\wmiguid\nf-wdm-rtlinitansistring.md) | The RtlInitAnsiString routine initializes a counted string of ANSI characters. |
| [RtlInitString function](..\wmiguid\nf-wdm-rtlinitstring.md) | The RtlInitString routine initializes a counted string of 8-bit characters. |
| [RtlInitStringEx function](..\wmiguid\nf-wdm-rtlinitstringex.md) | The RtlInitStringEx routine initializes a counted string of 8-bit characters. |
| [RtlInitUnicodeString function](..\wmiguid\nf-wdm-rtlinitunicodestring.md) | For more information, see the WdmlibRtlInitUnicodeStringEx function. |
| [RtlInitializeBitMap function](..\wmiguid\nf-wdm-rtlinitializebitmap.md) | The RtlInitializeBitMap routine initializes the header of a bitmap variable. |
| [RtlInitializeCorrelationVector function](..\wmiguid\nf-ntddk-rtlinitializecorrelationvector.md) | Initializes the specified correlation vector with the supplied GUID. |
| [RtlInt64ToUnicodeString function](..\wmiguid\nf-wdm-rtlint64tounicodestring.md) | The RtlInt64ToUnicodeString routine converts a specified unsigned 64-bit integer value to a Unicode string that represents the value in a specified base. |
| [RtlInt8Add function](..\wmiguid\nf-ntintsafe-rtlint8add.md) | Adds two values of type INT8. |
| [RtlInt8Mult function](..\wmiguid\nf-ntintsafe-rtlint8mult.md) | Multiplies one value of type INT8 by another. |
| [RtlInt8Sub function](..\wmiguid\nf-ntintsafe-rtlint8sub.md) | Subtracts one value of type INT8 from another. |
| [RtlInt8ToUChar function](..\wmiguid\nf-ntintsafe-rtlint8touchar.md) | Converts a value of type INT8 to a value of type UCHAR. |
| [RtlInt8ToUInt function](..\wmiguid\nf-ntintsafe-rtlint8touint.md) | Converts a value of type INT8 to a value of type UINT. |
| [RtlInt8ToUInt8 function](..\wmiguid\nf-ntintsafe-rtlint8touint8.md) | Converts a value of type INT8 to a value of type UINT8. |
| [RtlInt8ToUIntPtr function](..\wmiguid\nf-ntintsafe-rtlint8touintptr.md) | Converts a value of type INT8 to a value of type UINT_PTR. |
| [RtlInt8ToULong function](..\wmiguid\nf-ntintsafe-rtlint8toulong.md) | Converts a value of type INT8 to a value of type ULONG. |
| [RtlInt8ToULongLong function](..\wmiguid\nf-ntintsafe-rtlint8toulonglong.md) | Converts a value of type INT8 to a value of type ULONGLONG. |
| [RtlInt8ToULongPtr function](..\wmiguid\nf-ntintsafe-rtlint8toulongptr.md) | Converts a value of type INT8 to a value of type ULONG_PTR. |
| [RtlInt8ToUShort function](..\wmiguid\nf-ntintsafe-rtlint8toushort.md) | Converts a value of type INT8 to a value of type USHORT. |
| [RtlIntAdd function](..\wmiguid\nf-ntintsafe-rtlintadd.md) | Adds two values of type INT. |
| [RtlIntMult function](..\wmiguid\nf-ntintsafe-rtlintmult.md) | Multiplies one value of type INT by another. |
| [RtlIntPtrAdd function](..\wmiguid\nf-ntintsafe-rtlintptradd.md) | Adds two values of type INT_PTR. |
| [RtlIntPtrMult function](..\wmiguid\nf-ntintsafe-rtlintptrmult.md) | Multiplies one value of type INT_PTR by another. |
| [RtlIntPtrSub function](..\wmiguid\nf-ntintsafe-rtlintptrsub.md) | Subtracts one value of type INT_PTR from another. |
| [RtlIntPtrToChar function](..\wmiguid\nf-ntintsafe-rtlintptrtochar.md) | Converts a value of type INT_PTR to a value of type CHAR. |
| [RtlIntPtrToInt function](..\wmiguid\nf-ntintsafe-rtlintptrtoint.md) | Converts a value of type INT_PTR to a value of type INT. |
| [RtlIntPtrToInt8 function](..\wmiguid\nf-ntintsafe-rtlintptrtoint8.md) | Converts a value of type INT_PTR to a value of type INT8. |
| [RtlIntPtrToLong function](..\wmiguid\nf-ntintsafe-rtlintptrtolong.md) | Converts a value of type INT_PTR to a value of type LONG. |
| [RtlIntPtrToLongPtr function](..\wmiguid\nf-ntintsafe-rtlintptrtolongptr.md) | Converts a value of type INT_PTR to a value of type LONG_PTR. |
| [RtlIntPtrToShort function](..\wmiguid\nf-ntintsafe-rtlintptrtoshort.md) | Converts a value of type INT_PTR to a value of type SHORT. |
| [RtlIntPtrToUChar function](..\wmiguid\nf-ntintsafe-rtlintptrtouchar.md) | Converts a value of type INT_PTR to a value of type UCHAR. |
| [RtlIntPtrToUInt function](..\wmiguid\nf-ntintsafe-rtlintptrtouint.md) | Converts a value of type INT_PTR to a value of type UINT. |
| [RtlIntPtrToUInt8 function](..\wmiguid\nf-ntintsafe-rtlintptrtouint8.md) | Converts a value of type INT_PTR to a value of type UINT8. |
| [RtlIntPtrToUIntPtr function](..\wmiguid\nf-ntintsafe-rtlintptrtouintptr.md) | Converts a value of type INT_PTR to a value of type UINT_PTR. |
| [RtlIntPtrToULong function](..\wmiguid\nf-ntintsafe-rtlintptrtoulong.md) | Converts a value of type INT_PTR to a value of type ULONG. |
| [RtlIntPtrToULongLong function](..\wmiguid\nf-ntintsafe-rtlintptrtoulonglong.md) | Converts a value of type INT_PTR to a value of type ULONGLONG. |
| [RtlIntPtrToULongPtr function](..\wmiguid\nf-ntintsafe-rtlintptrtoulongptr.md) | Converts a value of type INT_PTR to a value of type ULONG_PTR. |
| [RtlIntPtrToUShort function](..\wmiguid\nf-ntintsafe-rtlintptrtoushort.md) | Converts a value of type INT_PTR to a value of type USHORT. |
| [RtlIntSub function](..\wmiguid\nf-ntintsafe-rtlintsub.md) | Subtracts one value of type INT from another. |
| [RtlIntToChar function](..\wmiguid\nf-ntintsafe-rtlinttochar.md) | Converts a value of type INT to a value of type CHAR. |
| [RtlIntToInt8 function](..\wmiguid\nf-ntintsafe-rtlinttoint8.md) | Converts a value of type INT to a value of type INT8. |
| [RtlIntToShort function](..\wmiguid\nf-ntintsafe-rtlinttoshort.md) | Converts a value of type INT to a value of type SHORT. |
| [RtlIntToUChar function](..\wmiguid\nf-ntintsafe-rtlinttouchar.md) | Converts a value of type INT to a value of type UCHAR. |
| [RtlIntToUInt function](..\wmiguid\nf-ntintsafe-rtlinttouint.md) | Converts a value of type INT to a value of type UINT. |
| [RtlIntToUInt8 function](..\wmiguid\nf-ntintsafe-rtlinttouint8.md) | Converts a value of type INT to a value of type UINT8. |
| [RtlIntToULong function](..\wmiguid\nf-ntintsafe-rtlinttoulong.md) | Converts a value of type INT to a value of type ULONG. |
| [RtlIntToULongLong function](..\wmiguid\nf-ntintsafe-rtlinttoulonglong.md) | Converts a value of type INT to a value of type ULONGLONG. |
| [RtlIntToUShort function](..\wmiguid\nf-ntintsafe-rtlinttoushort.md) | Converts a value of type INT to a value of type USHORT. |
| [RtlIntegerToUnicodeString function](..\wmiguid\nf-wdm-rtlintegertounicodestring.md) | The RtlIntegerToUnicodeString routine converts an unsigned integer value to a null-terminated string of one or more Unicode characters in the specified base. |
| [RtlIoDecodeMemIoResource function](..\wmiguid\nf-wdm-rtliodecodememioresource.md) | The RtlIoDecodeMemIoResource routine provides the address information that is contained in an IO_RESOURCE_DESCRIPTOR structure that describes a range of memory or I/O port addresses. |
| [RtlIoEncodeMemIoResource function](..\wmiguid\nf-wdm-rtlioencodememioresource.md) | The RtlIoEncodeMemIoResource routine updates an IO_RESOURCE_DESCRIPTOR structure to describe a range of memory or I/O port addresses. |
| [RtlIsNtDdiVersionAvailable function](..\wmiguid\nf-wdm-rtlisntddiversionavailable.md) | The RtlIsNtDdiVersionAvailable routine determines if a specified version of the Microsoft Windows device driver interface (DDI) is available. |
| [RtlIsServicePackVersionInstalled function](..\wmiguid\nf-wdm-rtlisservicepackversioninstalled.md) | The RtlIsServicePackVersionInstalled routine determines if a specified service pack version of the Microsoft Windows device driver interface (DDI) is installed. |
| [RtlIsStateSeparationEnabled function](..\wmiguid\nf-ntddk-rtlisstateseparationenabled.md) | Checks if the SKU for the current context supports multiple sessions. |
| [RtlLengthSecurityDescriptor function](..\wmiguid\nf-wdm-rtllengthsecuritydescriptor.md) | The RtlLengthSecurityDescriptor routine returns the size of a given security descriptor. |
| [RtlLongAdd function](..\wmiguid\nf-ntintsafe-rtllongadd.md) | Adds two values of type LONG. |
| [RtlLongLongAdd function](..\wmiguid\nf-ntintsafe-rtllonglongadd.md) | Adds two values of type LONGLONG. |
| [RtlLongLongMult function](..\wmiguid\nf-ntintsafe-rtllonglongmult.md) | Multiplies one value of type LONGLONG by another. |
| [RtlLongLongSub function](..\wmiguid\nf-ntintsafe-rtllonglongsub.md) | Subtracts one value of type LONGLONG from another. |
| [RtlLongLongToChar function](..\wmiguid\nf-ntintsafe-rtllonglongtochar.md) | Converts a value of type LONGLONG to a value of type CHAR. |
| [RtlLongLongToInt function](..\wmiguid\nf-ntintsafe-rtllonglongtoint.md) | Converts a value of type LONGLONG to a value of type INT. |
| [RtlLongLongToInt8 function](..\wmiguid\nf-ntintsafe-rtllonglongtoint8.md) | Converts a value of type LONGLONG to a value of type INT8. |
| [RtlLongLongToIntPtr function](..\wmiguid\nf-ntintsafe-rtllonglongtointptr.md) | Converts a value of type LONGLONG to a value of type INT_PTR. |
| [RtlLongLongToLong function](..\wmiguid\nf-ntintsafe-rtllonglongtolong.md) | Converts a value of type LONGLONG to a value of type LONG. |
| [RtlLongLongToLongPtr function](..\wmiguid\nf-ntintsafe-rtllonglongtolongptr.md) | Converts a value of type LONGLONG to a value of type LONG_PTR. |
| [RtlLongLongToShort function](..\wmiguid\nf-ntintsafe-rtllonglongtoshort.md) | Converts a value of type LONGLONG to a value of type SHORT. |
| [RtlLongLongToUChar function](..\wmiguid\nf-ntintsafe-rtllonglongtouchar.md) | Converts a value of type LONGLONG to a value of type UCHAR. |
| [RtlLongLongToUInt function](..\wmiguid\nf-ntintsafe-rtllonglongtouint.md) | Converts a value of type LONGLONG to a value of type UINT. |
| [RtlLongLongToUInt8 function](..\wmiguid\nf-ntintsafe-rtllonglongtouint8.md) | Converts a value of type LONGLONG to a value of type UNIT8. |
| [RtlLongLongToULong function](..\wmiguid\nf-ntintsafe-rtllonglongtoulong.md) | Converts a value of type LONGLONG to a value of type ULONG. |
| [RtlLongLongToULongLong function](..\wmiguid\nf-ntintsafe-rtllonglongtoulonglong.md) | Converts a value of type LONGLONG to a value of type LONGLONG. |
| [RtlLongLongToUShort function](..\wmiguid\nf-ntintsafe-rtllonglongtoushort.md) | Converts a value of type LONGLONG to a value of type USHORT. |
| [RtlLongMult function](..\wmiguid\nf-ntintsafe-rtllongmult.md) | Multiplies one value of type LONG by another. |
| [RtlLongPtrAdd function](..\wmiguid\nf-ntintsafe-rtllongptradd.md) | Adds two values of type LONG_PTR. |
| [RtlLongPtrMult function](..\wmiguid\nf-ntintsafe-rtllongptrmult.md) | Multiplies one value of type LONG_PTR by another. |
| [RtlLongPtrSub function](..\wmiguid\nf-ntintsafe-rtllongptrsub.md) | Subtracts one value of type LONG_PTR from another. |
| [RtlLongPtrToChar function](..\wmiguid\nf-ntintsafe-rtllongptrtochar.md) | Converts a value of type LONG_PTR to a value of type CHAR. |
| [RtlLongPtrToInt function](..\wmiguid\nf-ntintsafe-rtllongptrtoint.md) | Converts a value of type LONG_PTR to a value of type INT. |
| [RtlLongPtrToInt8 function](..\wmiguid\nf-ntintsafe-rtllongptrtoint8.md) | Converts a value of type LONG_PTR to a value of type INT8. |
| [RtlLongPtrToIntPtr function](..\wmiguid\nf-ntintsafe-rtllongptrtointptr.md) | Converts a value of type LONG_PTR to a value of type INT_PTR. |
| [RtlLongPtrToLong function](..\wmiguid\nf-ntintsafe-rtllongptrtolong.md) | Converts a value of type LONG_PTR to a value of type LONG. |
| [RtlLongPtrToShort function](..\wmiguid\nf-ntintsafe-rtllongptrtoshort.md) | Converts a value of type LONG_PTR to a value of type SHORT. |
| [RtlLongPtrToUChar function](..\wmiguid\nf-ntintsafe-rtllongptrtouchar.md) | Converts a value of type LONG_PTR to a value of type UCHAR. |
| [RtlLongPtrToUInt function](..\wmiguid\nf-ntintsafe-rtllongptrtouint.md) | Converts a value of type LONG_PTR to a value of type UINT. |
| [RtlLongPtrToUInt8 function](..\wmiguid\nf-ntintsafe-rtllongptrtouint8.md) | Converts a value of type LONG_PTR to a value of type UINT8. |
| [RtlLongPtrToUIntPtr function](..\wmiguid\nf-ntintsafe-rtllongptrtouintptr.md) | Converts a value of type LONG_PTR to a value of type UINT_PTR. |
| [RtlLongPtrToULong function](..\wmiguid\nf-ntintsafe-rtllongptrtoulong.md) | Converts a value of type LONG_PTR to a value of type ULONG. |
| [RtlLongPtrToULongLong function](..\wmiguid\nf-ntintsafe-rtllongptrtoulonglong.md) | Converts a value of type LONG_PTR to a value of type ULONGLONG. |
| [RtlLongPtrToULongPtr function](..\wmiguid\nf-ntintsafe-rtllongptrtoulongptr.md) | Converts a value of type LONG_PTR to a value of type ULONG_PTR. |
| [RtlLongPtrToUShort function](..\wmiguid\nf-ntintsafe-rtllongptrtoushort.md) | Converts a value of type LONG_PTR to a value of type USHORT. |
| [RtlLongSub function](..\wmiguid\nf-ntintsafe-rtllongsub.md) | Subtracts one value of type LONG from another. |
| [RtlLongToChar function](..\wmiguid\nf-ntintsafe-rtllongtochar.md) | Converts a value of type LONG to a value of type CHAR. |
| [RtlLongToInt function](..\wmiguid\nf-ntintsafe-rtllongtoint.md) | Converts a value of type LONG to a value of type INT. |
| [RtlLongToInt8 function](..\wmiguid\nf-ntintsafe-rtllongtoint8.md) | Converts a value of type LONG to a value of type INT8. |
| [RtlLongToIntPtr function](..\wmiguid\nf-ntintsafe-rtllongtointptr.md) | Converts a value of type LONG to a value of type INT_PTR. |
| [RtlLongToShort function](..\wmiguid\nf-ntintsafe-rtllongtoshort.md) | Converts a value of type LONG to a value of type SHORT. |
| [RtlLongToUChar function](..\wmiguid\nf-ntintsafe-rtllongtouchar.md) | Converts a value of type LONG to a value of type UCHAR. |
| [RtlLongToUInt function](..\wmiguid\nf-ntintsafe-rtllongtouint.md) | Converts a value of type LONG to a value of type UINT. |
| [RtlLongToUInt8 function](..\wmiguid\nf-ntintsafe-rtllongtouint8.md) | Converts a value of type LONG to a value of type UINT8. |
| [RtlLongToUIntPtr function](..\wmiguid\nf-ntintsafe-rtllongtouintptr.md) | Converts a value of type LONG to a value of type UINT_PTR. |
| [RtlLongToULong function](..\wmiguid\nf-ntintsafe-rtllongtoulong.md) | Converts a value of type LONG to a value of type ULONG. |
| [RtlLongToULongLong function](..\wmiguid\nf-ntintsafe-rtllongtoulonglong.md) | Converts a value of type LONG to a value of type ULONGLONG. |
| [RtlLongToULongPtr function](..\wmiguid\nf-ntintsafe-rtllongtoulongptr.md) | Converts a value of type LONG to a value of type ULONG_PTR. |
| [RtlLongToUShort function](..\wmiguid\nf-ntintsafe-rtllongtoushort.md) | Converts a value of type LONG to a value of type USHORT. |
| [RtlMapGenericMask function](..\wmiguid\nf-ntddk-rtlmapgenericmask.md) | The RtlMapGenericMask routine determines the nongeneric access rights specified by an ACCESS_MASK. |
| [RtlNumberOfClearBits function](..\wmiguid\nf-wdm-rtlnumberofclearbits.md) | The RtlNumberOfClearBits routine returns a count of the clear bits in a given bitmap variable. |
| [RtlNumberOfSetBits function](..\wmiguid\nf-wdm-rtlnumberofsetbits.md) | The RtlNumberOfSetBits routine returns a count of the set bits in a given bitmap variable. |
| [RtlNumberOfSetBitsUlongPtr function](..\wmiguid\nf-wdm-rtlnumberofsetbitsulongptr.md) | The RtlNumberOfSetBitsUlongPtr routine returns the number of bits in the specified ULONG_PTR integer value that are set to one. |
| [RtlPrefetchMemoryNonTemporal function](..\wmiguid\nf-wdm-rtlprefetchmemorynontemporal.md) | The RtlPrefetchMemoryNonTemporal routine provides a hint to the processor that a buffer should be temporarily moved into the processor cache. |
| [RtlPrefixUnicodeString function](..\wmiguid\nf-ntddk-rtlprefixunicodestring.md) | The RtlPrefixUnicodeString routine compares two Unicode strings to determine whether one string is a prefix of the other. |
| [RtlPtrdiffTAdd function](..\wmiguid\nf-ntintsafe-rtlptrdifftadd.md) | Adds two values of type PTRDIFF_T. |
| [RtlPtrdiffTMult function](..\wmiguid\nf-ntintsafe-rtlptrdifftmult.md) | Multiplies one value of type PTRDIFF_T by another. |
| [RtlPtrdiffTSub function](..\wmiguid\nf-ntintsafe-rtlptrdifftsub.md) | Subtracts one value of type PTRDIFF_T from another. |
| [RtlQueryRegistryValues function](..\wmiguid\nf-wdm-rtlqueryregistryvalues.md) | The RtlQueryRegistryValues routine allows the caller to query several values from the registry subtree with a single call. |
| [RtlRunOnceBeginInitialize function](..\wmiguid\nf-ntddk-rtlrunoncebegininitialize.md) | The RtlRunOnceBeginInitialize routine begins a one-time initialization. |
| [RtlRunOnceComplete function](..\wmiguid\nf-ntddk-rtlrunoncecomplete.md) | The RtlRunOnceComplete routine completes the one-time initialization began by RtlRunOnceBeginInitialize. |
| [RtlRunOnceExecuteOnce function](..\wmiguid\nf-ntddk-rtlrunonceexecuteonce.md) | The RtlRunOnceExecuteOnce performs a one-time initialization. |
| [RtlRunOnceInitialize function](..\wmiguid\nf-ntddk-rtlrunonceinitialize.md) | The RtlRunOnceInitialize routine initializes a RTL_RUN_ONCE structure. |
| [RtlSSIZETAdd function](..\wmiguid\nf-ntintsafe-rtlssizetadd.md) | Adds two values of type SSIZE_T. |
| [RtlSSIZETMult function](..\wmiguid\nf-ntintsafe-rtlssizetmult.md) | Multiplies one value of type SSIZE_T by another. |
| [RtlSSIZETSub function](..\wmiguid\nf-ntintsafe-rtlssizetsub.md) | Subtracts one value of type SSIZE_T from another. |
| [RtlSecureZeroMemory function](..\wmiguid\nf-wdm-rtlsecurezeromemory.md) | The RtlSecureZeroMemory routine fills a block of memory with zeros in a way that is guaranteed to be secure. |
| [RtlSetAllBits function](..\wmiguid\nf-wdm-rtlsetallbits.md) | The RtlSetAllBits routine sets all bits in a given bitmap variable. |
| [RtlSetBit function](..\wmiguid\nf-wdm-rtlsetbit.md) | The RtlSetBit routine sets the specified bit in a bitmap to one. |
| [RtlSetBits function](..\wmiguid\nf-wdm-rtlsetbits.md) | The RtlSetBits routine sets all bits in a given range of a given bitmap variable. |
| [RtlSetDaclSecurityDescriptor function](..\wmiguid\nf-wdm-rtlsetdaclsecuritydescriptor.md) | The RtlSetDaclSecurityDescriptor routine sets the DACL information of an absolute-format security descriptor, or if there is already a DACL present in the security descriptor, it is superseded. |
| [RtlShortAdd function](..\wmiguid\nf-ntintsafe-rtlshortadd.md) | Adds two values of type SHORT. |
| [RtlShortMult function](..\wmiguid\nf-ntintsafe-rtlshortmult.md) | Multiplies one value of type SHORT by another. |
| [RtlShortSub function](..\wmiguid\nf-ntintsafe-rtlshortsub.md) | Subtracts one value of type SHORT from another. |
| [RtlShortToChar function](..\wmiguid\nf-ntintsafe-rtlshorttochar.md) | Converts a value of type SHORT to a value of type CHAR. |
| [RtlShortToDWordPtr function](..\wmiguid\nf-ntintsafe-rtlshorttodwordptr.md) | Converts a value of type SHORT to a value of type DWORD_PTR. |
| [RtlShortToInt8 function](..\wmiguid\nf-ntintsafe-rtlshorttoint8.md) | Converts a value of type SHORT to a value of type INT8. |
| [RtlShortToUChar function](..\wmiguid\nf-ntintsafe-rtlshorttouchar.md) | Converts a value of type SHORT to a value of type UCHAR. |
| [RtlShortToUInt function](..\wmiguid\nf-ntintsafe-rtlshorttouint.md) | Converts a value of type SHORT to a value of type UINT. |
| [RtlShortToUInt8 function](..\wmiguid\nf-ntintsafe-rtlshorttouint8.md) | Converts a value of type SHORT to a value of type UINT8. |
| [RtlShortToUIntPtr function](..\wmiguid\nf-ntintsafe-rtlshorttouintptr.md) | Converts a value of type SHORT to a value of type UINT_PTR. |
| [RtlShortToULong function](..\wmiguid\nf-ntintsafe-rtlshorttoulong.md) | Converts a value of type SHORT to a value of type ULONG. |
| [RtlShortToULongLong function](..\wmiguid\nf-ntintsafe-rtlshorttoulonglong.md) | Converts a value of type SHORT to a value of type ULONGLONG. |
| [RtlShortToULongPtr function](..\wmiguid\nf-ntintsafe-rtlshorttoulongptr.md) | Converts a value of type SHORT to a value of type ULONG_PTR. |
| [RtlShortToUShort function](..\wmiguid\nf-ntintsafe-rtlshorttoushort.md) | Converts a value of type SHORT to a value of type USHORT. |
| [RtlSizeTAdd function](..\wmiguid\nf-ntintsafe-rtlsizetadd.md) | Adds two values of type SIZE_T. |
| [RtlSizeTMult function](..\wmiguid\nf-ntintsafe-rtlsizetmult.md) | Multiplies one value of type SIZE_T by another. |
| [RtlSizeTSub function](..\wmiguid\nf-ntintsafe-rtlsizetsub.md) | Subtracts one value of type SIZE_T from another. |
| [RtlStringCbCatA function](..\wmiguid\nf-ntstrsafe-rtlstringcbcata.md) | The RtlStringCbCatW and RtlStringCbCatA functions concatenate two byte-counted strings. |
| [RtlStringCbCatExA function](..\wmiguid\nf-ntstrsafe-rtlstringcbcatexa.md) | The RtlStringCbCatExW and RtlStringCbCatExA functions concatenate two byte-counted strings. |
| [RtlStringCbCatExW function](..\wmiguid\nf-ntstrsafe-rtlstringcbcatexw.md) | The RtlStringCbCatExW and RtlStringCbCatExA functions concatenate two byte-counted strings. |
| [RtlStringCbCatNA function](..\wmiguid\nf-ntstrsafe-rtlstringcbcatna.md) | The RtlStringCbCatNW and RtlStringCbCatNA functions concatenate two byte-counted strings while limiting the size of the appended string. |
| [RtlStringCbCatNExA function](..\wmiguid\nf-ntstrsafe-rtlstringcbcatnexa.md) | The RtlStringCbCatNExW and RtlStringCbCatNExA functions concatenate two byte-counted strings while limiting the size of the appended string. |
| [RtlStringCbCatNExW function](..\wmiguid\nf-ntstrsafe-rtlstringcbcatnexw.md) | The RtlStringCbCatNExW and RtlStringCbCatNExA functions concatenate two byte-counted strings while limiting the size of the appended string. |
| [RtlStringCbCatNW function](..\wmiguid\nf-ntstrsafe-rtlstringcbcatnw.md) | The RtlStringCbCatNW and RtlStringCbCatNA functions concatenate two byte-counted strings while limiting the size of the appended string. |
| [RtlStringCbCatW function](..\wmiguid\nf-ntstrsafe-rtlstringcbcatw.md) | The RtlStringCbCatW and RtlStringCbCatA functions concatenate two byte-counted strings. |
| [RtlStringCbCopyA function](..\wmiguid\nf-ntstrsafe-rtlstringcbcopya.md) | The RtlStringCbCopyW and RtlStringCbCopyA functions copy a byte-counted string into a buffer. |
| [RtlStringCbCopyExA function](..\wmiguid\nf-ntstrsafe-rtlstringcbcopyexa.md) | The RtlStringCbCopyExW and RtlStringCbCopyExA functions copy a byte-counted string into a buffer. |
| [RtlStringCbCopyExW function](..\wmiguid\nf-ntstrsafe-rtlstringcbcopyexw.md) | The RtlStringCbCopyExW and RtlStringCbCopyExA functions copy a byte-counted string into a buffer. |
| [RtlStringCbCopyNA function](..\wmiguid\nf-ntstrsafe-rtlstringcbcopyna.md) | The RtlStringCbCopyNW and RtlStringCbCopyNA functions copy a byte-counted string to a buffer while limiting the size of the copied string. |
| [RtlStringCbCopyNExA function](..\wmiguid\nf-ntstrsafe-rtlstringcbcopynexa.md) | The RtlStringCbCopyNExW and RtlStringCbCopyNExA functions copy a byte-counted string to a buffer while limiting the size of the copied string. |
| [RtlStringCbCopyNExW function](..\wmiguid\nf-ntstrsafe-rtlstringcbcopynexw.md) | The RtlStringCbCopyNExW and RtlStringCbCopyNExA functions copy a byte-counted string to a buffer while limiting the size of the copied string. |
| [RtlStringCbCopyNW function](..\wmiguid\nf-ntstrsafe-rtlstringcbcopynw.md) | The RtlStringCbCopyNW and RtlStringCbCopyNA functions copy a byte-counted string to a buffer while limiting the size of the copied string. |
| [RtlStringCbCopyUnicodeString function](..\wmiguid\nf-ntstrsafe-rtlstringcbcopyunicodestring.md) | The RtlStringCbCopyUnicodeString function copies the contents of a UNICODE_STRING structure to a specified destination. |
| [RtlStringCbCopyUnicodeStringEx function](..\wmiguid\nf-ntstrsafe-rtlstringcbcopyunicodestringex.md) | The RtlStringCbCopyUnicodeStringEx function copies the contents of a UNICODE_STRING structure to a specified destination. |
| [RtlStringCbCopyW function](..\wmiguid\nf-ntstrsafe-rtlstringcbcopyw.md) | The RtlStringCbCopyW and RtlStringCbCopyA functions copy a byte-counted string into a buffer. |
| [RtlStringCbLengthA function](..\wmiguid\nf-ntstrsafe-rtlstringcblengtha.md) | The RtlStringCbLengthW and RtlStringCbLengthA functions determine the length, in bytes, of a supplied string. |
| [RtlStringCbLengthW function](..\wmiguid\nf-ntstrsafe-rtlstringcblengthw.md) | The RtlStringCbLengthW and RtlStringCbLengthA functions determine the length, in bytes, of a supplied string. |
| [RtlStringCbPrintfA function](..\wmiguid\nf-ntstrsafe-rtlstringcbprintfa.md) | The RtlStringCbPrintfW and RtlStringCbPrintfA functions create a byte-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCbPrintfExA function](..\wmiguid\nf-ntstrsafe-rtlstringcbprintfexa.md) | The RtlStringCbPrintfExW and RtlStringCbPrintfExA functions create a byte-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCbPrintfExW function](..\wmiguid\nf-ntstrsafe-rtlstringcbprintfexw.md) | The RtlStringCbPrintfExW and RtlStringCbPrintfExA functions create a byte-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCbPrintfW function](..\wmiguid\nf-ntstrsafe-rtlstringcbprintfw.md) | The RtlStringCbPrintfW and RtlStringCbPrintfA functions create a byte-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCbVPrintfA function](..\wmiguid\nf-ntstrsafe-rtlstringcbvprintfa.md) | The RtlStringCbVPrintfW and RtlStringCbVPrintfA functions create a byte-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCbVPrintfExA function](..\wmiguid\nf-ntstrsafe-rtlstringcbvprintfexa.md) | The RtlStringCbVPrintfExW and RtlStringCbVPrintfExA functions create a byte-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCbVPrintfExW function](..\wmiguid\nf-ntstrsafe-rtlstringcbvprintfexw.md) | The RtlStringCbVPrintfExW and RtlStringCbVPrintfExA functions create a byte-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCbVPrintfW function](..\wmiguid\nf-ntstrsafe-rtlstringcbvprintfw.md) | The RtlStringCbVPrintfW and RtlStringCbVPrintfA functions create a byte-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCchCatA function](..\wmiguid\nf-ntstrsafe-rtlstringcchcata.md) | The RtlStringCchCatW and RtlStringCchCatA functions concatenate two character-counted strings. |
| [RtlStringCchCatExA function](..\wmiguid\nf-ntstrsafe-rtlstringcchcatexa.md) | The RtlStringCchCatExW and RtlStringCchCatExA functions concatenate two character-counted strings. |
| [RtlStringCchCatExW function](..\wmiguid\nf-ntstrsafe-rtlstringcchcatexw.md) | The RtlStringCchCatExW and RtlStringCchCatExA functions concatenate two character-counted strings. |
| [RtlStringCchCatNA function](..\wmiguid\nf-ntstrsafe-rtlstringcchcatna.md) | The RtlStringCchCatNW and RtlStringCchCatNA functions concatenate two character-counted strings while limiting the size of the appended string. |
| [RtlStringCchCatNExA function](..\wmiguid\nf-ntstrsafe-rtlstringcchcatnexa.md) | The RtlStringCchCatNExW and RtlStringCchCatNExA functions concatenate two character-counted strings while limiting the size of the appended string. |
| [RtlStringCchCatNExW function](..\wmiguid\nf-ntstrsafe-rtlstringcchcatnexw.md) | The RtlStringCchCatNExW and RtlStringCchCatNExA functions concatenate two character-counted strings while limiting the size of the appended string. |
| [RtlStringCchCatNW function](..\wmiguid\nf-ntstrsafe-rtlstringcchcatnw.md) | The RtlStringCchCatNW and RtlStringCchCatNA functions concatenate two character-counted strings while limiting the size of the appended string. |
| [RtlStringCchCatW function](..\wmiguid\nf-ntstrsafe-rtlstringcchcatw.md) | The RtlStringCchCatW and RtlStringCchCatA functions concatenate two character-counted strings. |
| [RtlStringCchCopyA function](..\wmiguid\nf-ntstrsafe-rtlstringcchcopya.md) | The RtlStringCchCopyW and RtlStringCchCopyA functions copy a null-terminated source string into a destination buffer of specified length. |
| [RtlStringCchCopyExA function](..\wmiguid\nf-ntstrsafe-rtlstringcchcopyexa.md) | The RtlStringCchCopyExW and RtlStringCchCopyExA functions copy a character-counted string into a buffer. |
| [RtlStringCchCopyExW function](..\wmiguid\nf-ntstrsafe-rtlstringcchcopyexw.md) | The RtlStringCchCopyExW and RtlStringCchCopyExA functions copy a character-counted string into a buffer. |
| [RtlStringCchCopyNA function](..\wmiguid\nf-ntstrsafe-rtlstringcchcopyna.md) | The RtlStringCchCopyNW and RtlStringCchCopyNA functions copy a character-counted string to a buffer while limiting the size of the copied string. |
| [RtlStringCchCopyNExA function](..\wmiguid\nf-ntstrsafe-rtlstringcchcopynexa.md) | The RtlStringCchCopyNExW and RtlStringCchCopyNExA functions copy a character-counted string to a buffer while limiting the size of the copied string. |
| [RtlStringCchCopyNExW function](..\wmiguid\nf-ntstrsafe-rtlstringcchcopynexw.md) | The RtlStringCchCopyNExW and RtlStringCchCopyNExA functions copy a character-counted string to a buffer while limiting the size of the copied string. |
| [RtlStringCchCopyNW function](..\wmiguid\nf-ntstrsafe-rtlstringcchcopynw.md) | The RtlStringCchCopyNW and RtlStringCchCopyNA functions copy a character-counted string to a buffer while limiting the size of the copied string. |
| [RtlStringCchCopyUnicodeString function](..\wmiguid\nf-ntstrsafe-rtlstringcchcopyunicodestring.md) | The RtlStringCchCopyUnicodeString function copies the contents of a UNICODE_STRING structure to a specified destination. |
| [RtlStringCchCopyUnicodeStringEx function](..\wmiguid\nf-ntstrsafe-rtlstringcchcopyunicodestringex.md) | The RtlStringCchCopyUnicodeStringEx function copies the contents of a UNICODE_STRING structure to a specified destination. |
| [RtlStringCchCopyW function](..\wmiguid\nf-ntstrsafe-rtlstringcchcopyw.md) | The RtlStringCchCopyW and RtlStringCchCopyA functions copy a null-terminated source string into a destination buffer of specified length. |
| [RtlStringCchLengthA function](..\wmiguid\nf-ntstrsafe-rtlstringcchlengtha.md) | The RtlStringCchLengthW and RtlStringCchLengthA functions determine the length, in characters, of a supplied string. |
| [RtlStringCchLengthW function](..\wmiguid\nf-ntstrsafe-rtlstringcchlengthw.md) | The RtlStringCchLengthW and RtlStringCchLengthA functions determine the length, in characters, of a supplied string. |
| [RtlStringCchPrintfA function](..\wmiguid\nf-ntstrsafe-rtlstringcchprintfa.md) | The RtlStringCchPrintfW and RtlStringCchPrintfA functions create a character-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCchPrintfExA function](..\wmiguid\nf-ntstrsafe-rtlstringcchprintfexa.md) | The RtlStringCchPrintfExW and RtlStringCchPrintfExA functions create a character-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCchPrintfExW function](..\wmiguid\nf-ntstrsafe-rtlstringcchprintfexw.md) | The RtlStringCchPrintfExW and RtlStringCchPrintfExA functions create a character-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCchPrintfW function](..\wmiguid\nf-ntstrsafe-rtlstringcchprintfw.md) | The RtlStringCchPrintfW and RtlStringCchPrintfA functions create a character-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCchVPrintfA function](..\wmiguid\nf-ntstrsafe-rtlstringcchvprintfa.md) | The RtlStringCchVPrintfW and RtlStringCchVPrintfA functions create a character-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCchVPrintfExA function](..\wmiguid\nf-ntstrsafe-rtlstringcchvprintfexa.md) | The RtlStringCchVPrintfExW and RtlStringCchVPrintfExA functions create a character-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCchVPrintfExW function](..\wmiguid\nf-ntstrsafe-rtlstringcchvprintfexw.md) | The RtlStringCchVPrintfExW and RtlStringCchVPrintfExA functions create a character-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringCchVPrintfW function](..\wmiguid\nf-ntstrsafe-rtlstringcchvprintfw.md) | The RtlStringCchVPrintfW and RtlStringCchVPrintfA functions create a character-counted text string, with formatting that is based on supplied formatting information. |
| [RtlStringFromGUID function](..\wmiguid\nf-wdm-rtlstringfromguid.md) | The RtlStringFromGUID routine converts a given GUID from binary format into a Unicode string. |
| [RtlTestBit function](..\wmiguid\nf-wdm-rtltestbit.md) | The RtlTestBit routine returns the value of a bit in a bitmap. |
| [RtlTimeFieldsToTime function](..\wmiguid\nf-wdm-rtltimefieldstotime.md) | The RtlTimeFieldsToTime routine converts TIME_FIELDS information to a system time value. |
| [RtlTimeToTimeFields function](..\wmiguid\nf-wdm-rtltimetotimefields.md) | The RtlTimeToTimeFields routine converts system time into a TIME_FIELDS structure. |
| [RtlUInt8Add function](..\wmiguid\nf-ntintsafe-rtluint8add.md) | Adds two values of type UINT8. |
| [RtlUInt8Mult function](..\wmiguid\nf-ntintsafe-rtluint8mult.md) | Multiplies one value of type UINT8 by another. |
| [RtlUInt8Sub function](..\wmiguid\nf-ntintsafe-rtluint8sub.md) | The RtlUInt8Sub routine subtracts one value of type UINT8 from another. |
| [RtlUInt8ToChar function](..\wmiguid\nf-ntintsafe-rtluint8tochar.md) | Converts a value of type UINT8 to a value of type CHAR. |
| [RtlUInt8ToInt8 function](..\wmiguid\nf-ntintsafe-rtluint8toint8.md) | Converts a value of type UINT8 to a value of type INT8. |
| [RtlUIntAdd function](..\wmiguid\nf-ntintsafe-rtluintadd.md) | Adds two values of type UINT. |
| [RtlUIntMult function](..\wmiguid\nf-ntintsafe-rtluintmult.md) | Multiplies one value of type UINT by another. |
| [RtlUIntPtrAdd function](..\wmiguid\nf-ntintsafe-rtluintptradd.md) | Adds two values of type UINT_PTR. |
| [RtlUIntPtrMult function](..\wmiguid\nf-ntintsafe-rtluintptrmult.md) | Multiplies one value of type UINT_PTR by another. |
| [RtlUIntPtrSub function](..\wmiguid\nf-ntintsafe-rtluintptrsub.md) | Subtracts one value of type UINT_PTR from another. |
| [RtlUIntPtrToChar function](..\wmiguid\nf-ntintsafe-rtluintptrtochar.md) | Converts a value of type UINT_PTR to a value of type CHAR. |
| [RtlUIntPtrToInt function](..\wmiguid\nf-ntintsafe-rtluintptrtoint.md) | Converts a value of type UINT_PTR to a value of type INT. |
| [RtlUIntPtrToInt16 function](..\wmiguid\nf-ntintsafe-rtluintptrtoint16.md) | Converts a value of type UINT_PTR to a value of type INT16. |
| [RtlUIntPtrToInt8 function](..\wmiguid\nf-ntintsafe-rtluintptrtoint8.md) | Converts a value of type UINT_PTR to a value of type INT8. |
| [RtlUIntPtrToIntPtr function](..\wmiguid\nf-ntintsafe-rtluintptrtointptr.md) | Converts a value of type UINT_PTR to a value of type INT_PTR. |
| [RtlUIntPtrToLong function](..\wmiguid\nf-ntintsafe-rtluintptrtolong.md) | Converts a value of type UINT_PTR to a value of type LONG. |
| [RtlUIntPtrToLongLong function](..\wmiguid\nf-ntintsafe-rtluintptrtolonglong.md) | Converts a value of type UINT_PTR to a value of type LONGLONG. |
| [RtlUIntPtrToLongPtr function](..\wmiguid\nf-ntintsafe-rtluintptrtolongptr.md) | Converts a value of type UINT_PTR to a value of type LONG_PTR. |
| [RtlUIntPtrToShort function](..\wmiguid\nf-ntintsafe-rtluintptrtoshort.md) | Converts a value of type UINT_PTR to a value of type SHORT. |
| [RtlUIntPtrToUChar function](..\wmiguid\nf-ntintsafe-rtluintptrtouchar.md) | Converts a value of type UINT_PTR to a value of type UCHAR. |
| [RtlUIntPtrToUInt function](..\wmiguid\nf-ntintsafe-rtluintptrtouint.md) | Converts a value of type UINT_PTR to a value of type UINT. |
| [RtlUIntPtrToUInt16 function](..\wmiguid\nf-ntintsafe-rtluintptrtouint16.md) | Converts a value of type UINT_PTR to a value of type UINT16. |
| [RtlUIntPtrToUInt8 function](..\wmiguid\nf-ntintsafe-rtluintptrtouint8.md) | Converts a value of type UINT_PTR to a value of type UINT8. |
| [RtlUIntPtrToULong function](..\wmiguid\nf-ntintsafe-rtluintptrtoulong.md) | Converts a value of type UINT_PTR to a value of type LONG. |
| [RtlUIntPtrToUShort function](..\wmiguid\nf-ntintsafe-rtluintptrtoushort.md) | Converts a value of type UINT_PTR to a value of type USHORT. |
| [RtlUIntSub function](..\wmiguid\nf-ntintsafe-rtluintsub.md) | Subtracts one value of type UINT from another. |
| [RtlUIntToChar function](..\wmiguid\nf-ntintsafe-rtluinttochar.md) | Converts a value of type UINT to a value of type CHAR. |
| [RtlUIntToInt function](..\wmiguid\nf-ntintsafe-rtluinttoint.md) | Converts a value of type UINT to a value of type INT. |
| [RtlUIntToInt8 function](..\wmiguid\nf-ntintsafe-rtluinttoint8.md) | Converts a value of type UINT to a value of type INT8. |
| [RtlUIntToIntPtr function](..\wmiguid\nf-ntintsafe-rtluinttointptr.md) | Converts a value of type UINT to a value of type INT_PTR. |
| [RtlUIntToLong function](..\wmiguid\nf-ntintsafe-rtluinttolong.md) | Converts a value of type UINT to a value of type LONG. |
| [RtlUIntToLongPtr function](..\wmiguid\nf-ntintsafe-rtluinttolongptr.md) | Converts a value of type UINT to a value of type LONG_PTR. |
| [RtlUIntToShort function](..\wmiguid\nf-ntintsafe-rtluinttoshort.md) | Converts a value of type UINT to a value of type SHORT. |
| [RtlUIntToUChar function](..\wmiguid\nf-ntintsafe-rtluinttouchar.md) | Converts a value of type UINT to a value of type UCHAR. |
| [RtlUIntToUInt8 function](..\wmiguid\nf-ntintsafe-rtluinttouint8.md) | Converts a value of type UINT to a value of type UINT8. |
| [RtlUIntToUShort function](..\wmiguid\nf-ntintsafe-rtluinttoushort.md) | Converts a value of type UINT to a value of type USHORT. |
| [RtlULongAdd function](..\wmiguid\nf-ntintsafe-rtlulongadd.md) | Adds two values of type ULONG. |
| [RtlULongLongAdd function](..\wmiguid\nf-ntintsafe-rtlulonglongadd.md) | Adds two values of type ULONGLONG. |
| [RtlULongLongMult function](..\wmiguid\nf-ntintsafe-rtlulonglongmult.md) | Multiplies one value of type ULONGLONG by another. |
| [RtlULongLongSub function](..\wmiguid\nf-ntintsafe-rtlulonglongsub.md) | Subtracts one value of type ULONGLONG from another. |
| [RtlULongLongToChar function](..\wmiguid\nf-ntintsafe-rtlulonglongtochar.md) | Converts a value of type ULONGLONG to a value of type CHAR. |
| [RtlULongLongToInt function](..\wmiguid\nf-ntintsafe-rtlulonglongtoint.md) | Converts a value of type ULONGLONG to a value of type INT. |
| [RtlULongLongToInt8 function](..\wmiguid\nf-ntintsafe-rtlulonglongtoint8.md) | Converts a value of type ULONGLONG to a value of type INT8. |
| [RtlULongLongToLong function](..\wmiguid\nf-ntintsafe-rtlulonglongtolong.md) | Converts a value of type ULONGLONG to a value of type LONG. |
| [RtlULongLongToLongLong function](..\wmiguid\nf-ntintsafe-rtlulonglongtolonglong.md) | Converts a value of type ULONGLONG to a value of type LONGLONG. |
| [RtlULongLongToLongPtr function](..\wmiguid\nf-ntintsafe-rtlulonglongtolongptr.md) | Converts a value of type ULONGLONG to a value of type LONG_PTR. |
| [RtlULongLongToShort function](..\wmiguid\nf-ntintsafe-rtlulonglongtoshort.md) | Converts a value of type ULONGLONG to a value of type SHORT. |
| [RtlULongLongToUChar function](..\wmiguid\nf-ntintsafe-rtlulonglongtouchar.md) | Converts a value of type ULONGLONG to a value of type UCHAR. |
| [RtlULongLongToUInt function](..\wmiguid\nf-ntintsafe-rtlulonglongtouint.md) | Converts a value of type ULONGLONG to a value of type UINT. |
| [RtlULongLongToUInt8 function](..\wmiguid\nf-ntintsafe-rtlulonglongtouint8.md) | Converts a value of type ULONGLONG to a value of type UINT8. |
| [RtlULongLongToUIntPtr function](..\wmiguid\nf-ntintsafe-rtlulonglongtouintptr.md) | Converts a value of type ULONGLONG to a value of type UINT_PTR. |
| [RtlULongLongToULong function](..\wmiguid\nf-ntintsafe-rtlulonglongtoulong.md) | Converts a value of type ULONGLONG to a value of type ULONG. |
| [RtlULongLongToULongPtr function](..\wmiguid\nf-ntintsafe-rtlulonglongtoulongptr.md) | Converts a value of type ULONGLONG to a value of type ULONG_PTR. |
| [RtlULongLongToUShort function](..\wmiguid\nf-ntintsafe-rtlulonglongtoushort.md) | Converts a value of type ULONGLONG to a value of type USHORT. |
| [RtlULongMult function](..\wmiguid\nf-ntintsafe-rtlulongmult.md) | Multiplies one value of type ULONG by another. |
| [RtlULongPtrAdd function](..\wmiguid\nf-ntintsafe-rtlulongptradd.md) | Adds two values of type ULONG_PTR. |
| [RtlULongPtrMult function](..\wmiguid\nf-ntintsafe-rtlulongptrmult.md) | Multiplies one value of type ULONG_PTR by another. |
| [RtlULongPtrSub function](..\wmiguid\nf-ntintsafe-rtlulongptrsub.md) | Subtracts one value of type ULONG_PTR from another. |
| [RtlULongPtrToChar function](..\wmiguid\nf-ntintsafe-rtlulongptrtochar.md) | Converts a value of type ULONG_PTR to a value of type CHAR. |
| [RtlULongPtrToInt function](..\wmiguid\nf-ntintsafe-rtlulongptrtoint.md) | Converts a value of type ULONG_PTR to a value of type INT. |
| [RtlULongPtrToInt8 function](..\wmiguid\nf-ntintsafe-rtlulongptrtoint8.md) | Converts a value of type ULONG_PTR to a value of type INT8. |
| [RtlULongPtrToIntPtr function](..\wmiguid\nf-ntintsafe-rtlulongptrtointptr.md) | Converts a value of type ULONG_PTR to a value of type INT_PTR. |
| [RtlULongPtrToLong function](..\wmiguid\nf-ntintsafe-rtlulongptrtolong.md) | Converts a value of type ULONG_PTR to a value of type LONG. |
| [RtlULongPtrToLongLong function](..\wmiguid\nf-ntintsafe-rtlulongptrtolonglong.md) | Converts a value of type ULONG_PTR to a value of type LONGLONG. |
| [RtlULongPtrToLongPtr function](..\wmiguid\nf-ntintsafe-rtlulongptrtolongptr.md) | Converts a value of type ULONG_PTR to a value of type LONG_PTR. |
| [RtlULongPtrToShort function](..\wmiguid\nf-ntintsafe-rtlulongptrtoshort.md) | Converts a value of type ULONG_PTR to a value of type SHORT. |
| [RtlULongPtrToUChar function](..\wmiguid\nf-ntintsafe-rtlulongptrtouchar.md) | Converts a value of type ULONG_PTR to a value of type UCHAR. |
| [RtlULongPtrToUInt function](..\wmiguid\nf-ntintsafe-rtlulongptrtouint.md) | Converts a value of type ULONG_PTR to a value of type UINT. |
| [RtlULongPtrToUInt8 function](..\wmiguid\nf-ntintsafe-rtlulongptrtouint8.md) | Converts a value of type ULONG_PTR to a value of type UINT8. |
| [RtlULongPtrToUIntPtr function](..\wmiguid\nf-ntintsafe-rtlulongptrtouintptr.md) | Converts a value of type ULONG_PTR to a value of type UINT_PTR. |
| [RtlULongPtrToULong function](..\wmiguid\nf-ntintsafe-rtlulongptrtoulong.md) | Converts a value of type ULONG_PTR to a value of type ULONG. |
| [RtlULongPtrToUShort function](..\wmiguid\nf-ntintsafe-rtlulongptrtoushort.md) | Converts a value of type ULONG_PTR to a value of type USHORT. |
| [RtlULongSub function](..\wmiguid\nf-ntintsafe-rtlulongsub.md) | Subtracts one value of type ULONG from another. |
| [RtlULongToChar function](..\wmiguid\nf-ntintsafe-rtlulongtochar.md) | Converts a value of type ULONG to a value of type CHAR. |
| [RtlULongToInt function](..\wmiguid\nf-ntintsafe-rtlulongtoint.md) | Converts a value of type ULONG to a value of type INT. |
| [RtlULongToInt8 function](..\wmiguid\nf-ntintsafe-rtlulongtoint8.md) | Converts a value of type ULONG to a value of type INT8. |
| [RtlULongToIntPtr function](..\wmiguid\nf-ntintsafe-rtlulongtointptr.md) | Converts a value of type ULONG to a value of type INT_PTR. |
| [RtlULongToLong function](..\wmiguid\nf-ntintsafe-rtlulongtolong.md) | Converts a value of type ULONG to a value of type LONG. |
| [RtlULongToLongPtr function](..\wmiguid\nf-ntintsafe-rtlulongtolongptr.md) | Converts a value of type ULONG to a value of type LONG_PTR. |
| [RtlULongToShort function](..\wmiguid\nf-ntintsafe-rtlulongtoshort.md) | Converts a value of type ULONG to a value of type SHORT. |
| [RtlULongToUChar function](..\wmiguid\nf-ntintsafe-rtlulongtouchar.md) | Converts a value of type ULONG to a value of type UCHAR. |
| [RtlULongToUInt function](..\wmiguid\nf-ntintsafe-rtlulongtouint.md) | Converts a value of type ULONG to a value of type UINT. |
| [RtlULongToUInt8 function](..\wmiguid\nf-ntintsafe-rtlulongtouint8.md) | Converts a value of type ULONG_PTR to a value of type UINT8. |
| [RtlULongToUIntPtr function](..\wmiguid\nf-ntintsafe-rtlulongtouintptr.md) | Converts a value of type ULONG_PTR to a value of type UINT_PTR. |
| [RtlULongToUShort function](..\wmiguid\nf-ntintsafe-rtlulongtoushort.md) | Converts a value of type ULONG to a value of type USHORT. |
| [RtlUShortAdd function](..\wmiguid\nf-ntintsafe-rtlushortadd.md) | Adds two values of type USHORT. |
| [RtlUShortMult function](..\wmiguid\nf-ntintsafe-rtlushortmult.md) | Multiplies one value of type USHORT by another. |
| [RtlUShortSub function](..\wmiguid\nf-ntintsafe-rtlushortsub.md) | Subtracts one value of type USHORT from another. |
| [RtlUShortToChar function](..\wmiguid\nf-ntintsafe-rtlushorttochar.md) | Converts a value of type USHORT to a value of type CHAR. |
| [RtlUShortToInt8 function](..\wmiguid\nf-ntintsafe-rtlushorttoint8.md) | Converts a value of type USHORT to a value of type INT8. |
| [RtlUShortToShort function](..\wmiguid\nf-ntintsafe-rtlushorttoshort.md) | Converts a value of type USHORT to a value of type SHORT. |
| [RtlUShortToUChar function](..\wmiguid\nf-ntintsafe-rtlushorttouchar.md) | Converts a value of type USHORT to a value of type UCHAR. |
| [RtlUShortToUInt8 function](..\wmiguid\nf-ntintsafe-rtlushorttouint8.md) | Converts a value of type USHORT to a value of type UINT8. |
| [RtlUTF8ToUnicodeN function](..\wmiguid\nf-wdm-rtlutf8tounicoden.md) | The RtlUTF8ToUnicodeN routine converts a UTF-8 string to a Unicode string. |
| [RtlUnalignedStringCbLengthW function](..\wmiguid\nf-ntstrsafe-rtlunalignedstringcblengthw.md) | The RtlUnalignedStringCbLengthW function is a version of the RtlStringCbLength function that accepts an unaligned pointer to a string of Unicode characters. |
| [RtlUnalignedStringCchLengthW function](..\wmiguid\nf-ntstrsafe-rtlunalignedstringcchlengthw.md) | The RtlUnalignedStringCchLengthW function is a version of the RtlStringCchLength function that accepts an unaligned pointer to a string of Unicode characters. |
| [RtlUnicodeStringCat function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcat.md) | The RtlUnicodeStringCat function concatenates two strings that are contained in UNICODE_STRING structures. |
| [RtlUnicodeStringCatEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcatex.md) | The RtlUnicodeStringCatEx function concatenates two strings that are contained in UNICODE_STRING structures. |
| [RtlUnicodeStringCatString function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcatstring.md) | The RtlUnicodeStringCatString function concatenates two strings when the destination string is contained in a UNICODE_STRING structure. |
| [RtlUnicodeStringCatStringEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcatstringex.md) | The RtlUnicodeStringCatStringEx function concatenates two strings when the destination string is contained in a UNICODE_STRING structure. |
| [RtlUnicodeStringCbCatN function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcbcatn.md) | The RtlUnicodeStringCbCatN function concatenates two strings that are contained in UNICODE_STRING structures while limiting the size of the copied string. |
| [RtlUnicodeStringCbCatNEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcbcatnex.md) | The RtlUnicodeStringCbCatNEx function concatenates two strings that are contained in UNICODE_STRING structures while limiting the size of the copied string. |
| [RtlUnicodeStringCbCatStringN function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcbcatstringn.md) | The RtlUnicodeStringCbCatStringN function concatenates two strings when the destination string is contained in a UNICODE_STRING structure, while limiting the size of the appended string. |
| [RtlUnicodeStringCbCatStringNEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcbcatstringnex.md) | The RtlUnicodeStringCbCatStringNEx function concatenates two strings when the destination string is contained in a UNICODE_STRING structure, while limiting the size of the appended string. |
| [RtlUnicodeStringCbCopyN function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcbcopyn.md) | The RtlUnicodeStringCbCopyN function copies a string from one UNICODE_STRING structure to another while limiting the size of the copied string. |
| [RtlUnicodeStringCbCopyNEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcbcopynex.md) | The RtlUnicodeStringCbCopyNEx function copies a string from one UNICODE_STRING structure to another while limiting the size of the copied string. |
| [RtlUnicodeStringCbCopyStringN function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcbcopystringn.md) | The RtlUnicodeStringCbCopyStringN function copies a string into a UNICODE_STRING structure while limiting the size of the copied string. |
| [RtlUnicodeStringCbCopyStringNEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcbcopystringnex.md) | The RtlUnicodeStringCbCopyStringNEx function copies a string into a UNICODE_STRING structure while limiting the size of the copied string. |
| [RtlUnicodeStringCchCatN function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcchcatn.md) | The RtlUnicodeStringCchCatN function concatenates two strings that are contained in UNICODE_STRING structures while limiting the size of the copied string. |
| [RtlUnicodeStringCchCatNEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcchcatnex.md) | The RtlUnicodeStringCchCatNEx function concatenates two strings that are contained in UNICODE_STRING structures while limiting the size of the copied string. |
| [RtlUnicodeStringCchCatStringN function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcchcatstringn.md) | The RtlUnicodeStringCchCatStringN function concatenates two strings when the destination string is contained in a UNICODE_STRING structure, while limiting the size of the appended string. |
| [RtlUnicodeStringCchCatStringNEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcchcatstringnex.md) | The RtlUnicodeStringCchCatStringNEx function concatenates two strings when the destination string is contained in a UNICODE_STRING structure, while limiting the size of the appended string. |
| [RtlUnicodeStringCchCopyN function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcchcopyn.md) | The RtlUnicodeStringCchCopyN function copies a string from one UNICODE_STRING structure to another while limiting the size of the copied string. |
| [RtlUnicodeStringCchCopyNEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcchcopynex.md) | The RtlUnicodeStringCchCopyNEx function copies a string from one UNICODE_STRING structure to another while limiting the size of the copied string. |
| [RtlUnicodeStringCchCopyStringN function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcchcopystringn.md) | The RtlUnicodeStringCchCopyStringN function copies a string into a UNICODE_STRING structure while limiting the size of the copied string. |
| [RtlUnicodeStringCchCopyStringNEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcchcopystringnex.md) | The RtlUnicodeStringCchCopyStringNEx function copies a string into a UNICODE_STRING structure while limiting the size of the copied string. |
| [RtlUnicodeStringCopy function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcopy.md) | The RtlUnicodeStringCopy function copies a string from one UNICODE_STRING structure to another. |
| [RtlUnicodeStringCopyEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcopyex.md) | The RtlUnicodeStringCopyEx function copies a string from one UNICODE_STRING structure to another. |
| [RtlUnicodeStringCopyString function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcopystring.md) | The RtlUnicodeStringCopyString function copies a string into a UNICODE_STRING structure. |
| [RtlUnicodeStringCopyStringEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringcopystringex.md) | The RtlUnicodeStringCopyStringEx function copies a string into a UNICODE_STRING structure. |
| [RtlUnicodeStringInit function](..\wmiguid\nf-ntstrsafe-rtlunicodestringinit.md) | The RtlUnicodeStringInit function initializes a UNICODE_STRING structure. |
| [RtlUnicodeStringInitEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringinitex.md) | The RtlUnicodeStringInitEx function initializes a UNICODE_STRING structure. |
| [RtlUnicodeStringPrintf function](..\wmiguid\nf-ntstrsafe-rtlunicodestringprintf.md) | The RtlUnicodeStringPrintf function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a UNICODE_STRING structure. |
| [RtlUnicodeStringPrintfEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringprintfex.md) | The RtlUnicodeStringPrintfEx function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a UNICODE_STRING structure. |
| [RtlUnicodeStringToAnsiString function](..\wmiguid\nf-wdm-rtlunicodestringtoansistring.md) | The RtlUnicodeStringToAnsiString routine converts a given Unicode string into an ANSI string. |
| [RtlUnicodeStringToInteger function](..\wmiguid\nf-wdm-rtlunicodestringtointeger.md) | The RtlUnicodeStringToInteger routine converts a Unicode string representation of a number to the equivalent integer value. |
| [RtlUnicodeStringVPrintf function](..\wmiguid\nf-ntstrsafe-rtlunicodestringvprintf.md) | The RtlUnicodeStringVPrintf function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a UNICODE_STRING structure. |
| [RtlUnicodeStringVPrintfEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringvprintfex.md) | The RtlUnicodeStringVPrintfEx function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a UNICODE_STRING structure. |
| [RtlUnicodeStringValidate function](..\wmiguid\nf-ntstrsafe-rtlunicodestringvalidate.md) | The RtlUnicodeStringValidate function validates the contents of a UNICODE_STRING structure. |
| [RtlUnicodeStringValidateEx function](..\wmiguid\nf-ntstrsafe-rtlunicodestringvalidateex.md) | The RtlUnicodeStringValidateEx function validates the contents of a UNICODE_STRING structure. |
| [RtlUnicodeToUTF8N function](..\wmiguid\nf-wdm-rtlunicodetoutf8n.md) | The RtlUnicodeToUTF8N routine converts a Unicode string to a UTF-8 string. |
| [RtlUpcaseUnicodeChar function](..\wmiguid\nf-wdm-rtlupcaseunicodechar.md) | The RtlUpcaseUnicodeChar routine converts the specified Unicode character to uppercase. |
| [RtlUpcaseUnicodeString function](..\wmiguid\nf-ntddk-rtlupcaseunicodestring.md) | The RtlUpcaseUnicodeString routine converts a copy of the source string to uppercase and writes the converted string in the destination buffer. |
| [RtlUpperChar function](..\wmiguid\nf-ntddk-rtlupperchar.md) | The RtlUpperChar routine converts the specified character to uppercase. |
| [RtlUpperString function](..\wmiguid\nf-ntddk-rtlupperstring.md) | The RtlUpperString routine copies the given SourceString to the DestinationString buffer, converting it to uppercase. |
| [RtlValidRelativeSecurityDescriptor function](..\wmiguid\nf-wdm-rtlvalidrelativesecuritydescriptor.md) | The RtlValidRelativeSecurityDescriptor routine checks the validity of a self-relative security descriptor. |
| [RtlValidSecurityDescriptor function](..\wmiguid\nf-wdm-rtlvalidsecuritydescriptor.md) | The RtlValidSecurityDescriptor routine checks a given security descriptor's validity. |
| [RtlValidateCorrelationVector function](..\wmiguid\nf-ntddk-rtlvalidatecorrelationvector.md) | Validates the specified correlation vector to check whether it conforms to the Correlation Vector Specification (v2). |
| [RtlVerifyVersionInfo function](..\wmiguid\nf-wdm-rtlverifyversioninfo.md) | The RtlVerifyVersionInfo routine compares a specified set of operating system version requirements to the corresponding attributes of the currently running version of the operating system. |
| [RtlVolumeDeviceToDosName function](..\wmiguid\nf-ntddk-rtlvolumedevicetodosname.md) | The RtlVolumeDeviceToDosName routine is obsolete for Windows XP and later versions of Windows. Use IoVolumeDeviceToDosName instead.RtlVolumeDeviceToDosName returns the MS-DOS path for a specified device object that represents a file system volume. |
| [RtlWriteRegistryValue function](..\wmiguid\nf-wdm-rtlwriteregistryvalue.md) | The RtlWriteRegistryValue routine writes caller-supplied data into the registry along the specified relative path at the given value name. |
| [RtlxAnsiStringToUnicodeSize function](..\wmiguid\nf-wdm-rtlxansistringtounicodesize.md) | The RtlxAnsiStringToUnicodeSize routine returns the number of bytes that are required for a null-terminated Unicode string that is equivalent to a specified ANSI string. |
| [RtlxUnicodeStringToAnsiSize function](..\wmiguid\nf-wdm-rtlxunicodestringtoansisize.md) | The RtlxUnicodeStringToAnsiSize routine returns the number of bytes required for a null-terminated ANSI string that is equivalent to a specified Unicode string. |
| [SeAccessCheck function](..\wmiguid\nf-wdm-seaccesscheck.md) | The SeAccessCheck routine determines whether the requested access rights can be granted to an object protected by a security descriptor and an object owner. |
| [SeAssignSecurity function](..\wmiguid\nf-wdm-seassignsecurity.md) | The SeAssignSecurity routine builds a self-relative security descriptor for a new object, given the security descriptor of its parent directory and any originally requested security for the object. |
| [SeAssignSecurityEx function](..\wmiguid\nf-wdm-seassignsecurityex.md) | The SeAssignSecurityEx routine builds a self-relative security descriptor for a new object given the following optional parameters |
| [SeDeassignSecurity function](..\wmiguid\nf-wdm-sedeassignsecurity.md) | The SeDeassignSecurity routine deallocates the memory associated with a security descriptor that was assigned using SeAssignSecurity. |
| [SeSinglePrivilegeCheck function](..\wmiguid\nf-ntddk-sesingleprivilegecheck.md) | The SeSinglePrivilegeCheck routine checks for the passed privilege value in the context of the current thread. |
| [SeValidSecurityDescriptor function](..\wmiguid\nf-wdm-sevalidsecuritydescriptor.md) | The SeValidSecurityDescriptor routine returns whether a given security descriptor is structurally valid. |
| [TmCommitComplete function](..\wmiguid\nf-wdm-tmcommitcomplete.md) | The TmCommitComplete routine notifies KTM that the calling resource manager has finished committing a transaction. |
| [TmCommitEnlistment function](..\wmiguid\nf-wdm-tmcommitenlistment.md) | The TmCommitEnlistment routine initiates the commit operation for a specified enlistment's transaction. |
| [TmCommitTransaction function](..\wmiguid\nf-wdm-tmcommittransaction.md) | The TmCommitTransaction routine initiates a commit operation for a specified transaction. |
| [TmCreateEnlistment function](..\wmiguid\nf-wdm-tmcreateenlistment.md) | The TmCreateEnlistment routine creates a new enlistment object for a transaction. |
| [TmDereferenceEnlistmentKey function](..\wmiguid\nf-wdm-tmdereferenceenlistmentkey.md) | The TmDereferenceEnlistmentKey routine decrements the reference count for the key of a specified enlistment object. |
| [TmEnableCallbacks function](..\wmiguid\nf-wdm-tmenablecallbacks.md) | The TmEnableCallbacks routine enables a callback routine that receives transaction notifications. |
| [TmGetTransactionId function](..\wmiguid\nf-wdm-tmgettransactionid.md) | The TmGetTransactionId routine retrieves a transaction object's unit of work (UOW) identifier. |
| [TmInitializeTransactionManager function](..\wmiguid\nf-wdm-tminitializetransactionmanager.md) | The TmInitializeTransactionManager routine initializes a transaction manager object. |
| [TmIsTransactionActive function](..\wmiguid\nf-wdm-tmistransactionactive.md) | The TmIsTransactionActive routine indicates whether a specified transaction is in its active state. |
| [TmPrePrepareComplete function](..\wmiguid\nf-wdm-tmprepreparecomplete.md) | The TmPrePrepareComplete routine notifies KTM that the calling resource manager has finished preliminary preparation of a transaction's data. |
| [TmPrePrepareEnlistment function](..\wmiguid\nf-wdm-tmpreprepareenlistment.md) | The TmPrePrepareEnlistment routine initiates the pre-prepare operation for a specified enlistment's transaction. |
| [TmPrepareComplete function](..\wmiguid\nf-wdm-tmpreparecomplete.md) | The TmPrepareComplete routine notifies KTM that the calling resource manager has finished preparing a transaction's data. |
| [TmPrepareEnlistment function](..\wmiguid\nf-wdm-tmprepareenlistment.md) | The TmPrepareEnlistment routine initiates the prepare operation for a specified enlistment's transaction. |
| [TmReadOnlyEnlistment function](..\wmiguid\nf-wdm-tmreadonlyenlistment.md) | The TmReadOnlyEnlistment routine sets a specified enlistment to be read-only. |
| [TmRecoverEnlistment function](..\wmiguid\nf-wdm-tmrecoverenlistment.md) | The TmRecoverEnlistment routine initiates a recovery operation for the transaction that is associated with a specified enlistment. |
| [TmRecoverResourceManager function](..\wmiguid\nf-wdm-tmrecoverresourcemanager.md) | The TmRecoverResourceManager routine tries to recover the transaction that is associated with each enlistment of a specified resource manager object. |
| [TmRecoverTransactionManager function](..\wmiguid\nf-wdm-tmrecovertransactionmanager.md) | The TmRecoverTransactionManager routine reconstructs the state of the transaction manager object (including all transactions, enlistments, and resource managers) from the recovery information that is in the log stream. |
| [TmReferenceEnlistmentKey function](..\wmiguid\nf-wdm-tmreferenceenlistmentkey.md) | The TmReferenceEnlistmentKey routine increments the reference count for the key of a specified enlistment object and retrieves the key. |
| [TmRenameTransactionManager function](..\wmiguid\nf-wdm-tmrenametransactionmanager.md) | The TmRenameTransactionManager routine changes the identity of the transaction manager object that is stored in the CLFS log file stream contained in the log file name. |
| [TmRequestOutcomeEnlistment function](..\wmiguid\nf-wdm-tmrequestoutcomeenlistment.md) | The TmRequestOutcomeEnlistment routine asks KTM to try to provide an immediate outcome (commit or rollback) for the transaction that is associated with a specified enlistment. |
| [TmRollbackComplete function](..\wmiguid\nf-wdm-tmrollbackcomplete.md) | The TmRollbackComplete routine notifies KTM that the calling resource manager has finished rolling back a transaction's data. |
| [TmRollbackEnlistment function](..\wmiguid\nf-wdm-tmrollbackenlistment.md) | The TmRollbackEnlistment routine rolls back a specified enlistment. |
| [TmRollbackTransaction function](..\wmiguid\nf-wdm-tmrollbacktransaction.md) | The TmRollbackTransaction routine initiates a rollback operation for a specified transaction. |
| [TmSinglePhaseReject function](..\wmiguid\nf-wdm-tmsinglephasereject.md) | The TmSinglePhaseReject routine informs KTM that the calling resource manager will not support a single-phase commit operation for a specified enlistment. |
| [VslCreateSecureSection function](..\wmiguid\nf-wdm-vslcreatesecuresection.md) | This material is not yet available. This placeholder topic is provided as an example of documentation that may be included in a later release. |
| [WRITE_PORT_BUFFER_UCHAR function](..\wmiguid\nf-wdm-write_port_buffer_uchar.md) | The WRITE_PORT_BUFFER_UCHAR routine writes a number of bytes from a buffer to the specified port. |
| [WRITE_PORT_BUFFER_ULONG function](..\wmiguid\nf-wdm-write_port_buffer_ulong.md) | The WRITE_PORT_BUFFER_ULONG routine writes a number of ULONG values from a buffer to the specified port address. |
| [WRITE_PORT_BUFFER_USHORT function](..\wmiguid\nf-wdm-write_port_buffer_ushort.md) | The WRITE_PORT_BUFFER_USHORT routine writes a number of USHORT values from a buffer to the specified port address. |
| [WRITE_PORT_UCHAR function](..\wmiguid\nf-ioaccess-write_port_uchar.md) | The WRITE_PORT_UCHAR routine writes a byte to the specified port address. |
| [WRITE_PORT_UCHAR function](..\wmiguid\nf-wdm-write_port_uchar.md) | The WRITE_PORT_UCHAR routine writes a byte to the specified port address. |
| [WRITE_PORT_ULONG function](..\wmiguid\nf-ioaccess-write_port_ulong.md) | The WRITE_PORT_ULONG routine writes a ULONG value to the specified port address. |
| [WRITE_PORT_ULONG function](..\wmiguid\nf-wdm-write_port_ulong.md) | The WRITE_PORT_ULONG routine writes a ULONG value to the specified port address. |
| [WRITE_PORT_USHORT function](..\wmiguid\nf-ioaccess-write_port_ushort.md) | The WRITE_PORT_USHORT routine writes a USHORT value to the specified port address. |
| [WRITE_PORT_USHORT function](..\wmiguid\nf-wdm-write_port_ushort.md) | The WRITE_PORT_USHORT routine writes a USHORT value to the specified port address. |
| [WRITE_REGISTER_BUFFER_UCHAR function](..\wmiguid\nf-wdm-write_register_buffer_uchar.md) | The WRITE_REGISTER_BUFFER_UCHAR routine writes a number of bytes from a buffer to the specified register. |
| [WRITE_REGISTER_BUFFER_ULONG function](..\wmiguid\nf-wdm-write_register_buffer_ulong.md) | The WRITE_REGISTER_BUFFER_ULONG routine writes a number of ULONG values from a buffer to the specified register. |
| [WRITE_REGISTER_BUFFER_USHORT function](..\wmiguid\nf-wdm-write_register_buffer_ushort.md) | The WRITE_REGISTER_BUFFER_USHORT routine writes a number of USHORT values from a buffer to the specified register. |
| [WRITE_REGISTER_UCHAR function](..\wmiguid\nf-wdm-write_register_uchar.md) | The WRITE_REGISTER_UCHAR routine writes a byte to the specified address. |
| [WRITE_REGISTER_ULONG function](..\wmiguid\nf-wdm-write_register_ulong.md) | The WRITE_REGISTER_ULONG routine writes a ULONG value to the specified address. |
| [WRITE_REGISTER_USHORT function](..\wmiguid\nf-wdm-write_register_ushort.md) | The WRITE_REGISTER_USHORT routine writes a USHORT value to the specified address. |
| [WdmlibIoConnectInterruptEx function](..\wmiguid\nf-iointex-wdmlibioconnectinterruptex.md) | The WdmlibIoConnectInterruptEx function registers an interrupt-handling routine for a device's interrupts. |
| [WdmlibIoCreateDeviceSecure function](..\wmiguid\nf-wdmsec-wdmlibiocreatedevicesecure.md) | The WdmlibIoCreateDeviceSecure function (or IoCreateDeviceSecure) creates a named device object and applies the specified security settings. |
| [WdmlibIoDisconnectInterruptEx function](..\wmiguid\nf-iointex-wdmlibiodisconnectinterruptex.md) | The WdmlibIoDisconnectInterruptEx function unregisters an interrupt service routine (ISR) that was registered by a previous call to the WdmlibIoConnectInterruptEx function. |
| [WdmlibIoGetAffinityInterrupt function](..\wmiguid\nf-iointex-wdmlibiogetaffinityinterrupt.md) | The WdmlibIoGetAffinityInterrupt function gets the group affinity of an interrupt object. |
| [WdmlibIoValidateDeviceIoControlAccess function](..\wmiguid\nf-wdmsec-wdmlibiovalidatedeviceiocontrolaccess.md) | The WdmlibIoValidateDeviceIoControlAccess function verifies that the sender of an IRP_MJ_DEVICE_CONTROL or IRP_MJ_FILE_SYSTEM_CONTROL IRP has the specified access to the device object. |
| [WdmlibProcgrpInitialize function](..\wmiguid\nf-procgrp-wdmlibprocgrpinitialize.md) | The WdmlibProcgrpInitialize function initializes the Processor Group (ProcGrp) compatibility library. |
| [WdmlibRtlInitUnicodeStringEx function](..\wmiguid\nf-wdmsec-wdmlibrtlinitunicodestringex.md) | The WdmlibRtlInitUnicodeStringEx function initializes a counted string of Unicode characters. |
| [WmiCompleteRequest function](..\wmiguid\nf-wmilib-wmicompleterequest.md) | The WmiCompleteRequest routine indicates that a driver has finished processing a WMI request in a DpWmiXxx routine. |
| [WmiFireEvent function](..\wmiguid\nf-wmilib-wmifireevent.md) | The WmiFireEvent routine sends an event to WMI for delivery to data consumers that have requested notification of the event. |
| [WmiQueryTraceInformation function](..\wmiguid\nf-wdm-wmiquerytraceinformation.md) | The WmiQueryTraceInformation routine returns information about a WMI event trace. |
| [WmiSystemControl function](..\wmiguid\nf-wmilib-wmisystemcontrol.md) | The WmiSystemControl routine is a dispatch routine for drivers that use WMI library support routines to handle WMI IRPs. |
| [WmiTraceMessage function](..\wmiguid\nf-wdm-wmitracemessage.md) | The WmiTraceMessage routine adds a message to the output log of a WPP software tracing session. |
| [WmiTraceMessageVa function](..\wmiguid\nf-wdm-wmitracemessageva.md) | The WmiTraceMessageVa routine adds a message to the output log of a WPP software tracing session. |
| [ZwAllocateLocallyUniqueId function](..\wmiguid\nf-ntddk-zwallocatelocallyuniqueid.md) | The ZwAllocateLocallyUniqueId routine allocates a locally unique identifier (LUID). |
| [ZwClose function](..\wmiguid\nf-wdm-zwclose.md) | The ZwClose routine closes an object handle. |
| [ZwCommitComplete function](..\wmiguid\nf-wdm-zwcommitcomplete.md) | The ZwCommitComplete routine notifies KTM that the calling resource manager has finished committing a transaction's data. |
| [ZwCommitEnlistment function](..\wmiguid\nf-wdm-zwcommitenlistment.md) | The ZwCommitEnlistment routine initiates the commit operation for a specified enlistment's transaction. |
| [ZwCommitTransaction function](..\wmiguid\nf-wdm-zwcommittransaction.md) | The ZwCommitTransaction routine initiates a commit operation for a specified transaction. |
| [ZwCreateDirectoryObject function](..\wmiguid\nf-wdm-zwcreatedirectoryobject.md) | The ZwCreateDirectoryObject routine creates or opens an object-directory object. |
| [ZwCreateEnlistment function](..\wmiguid\nf-wdm-zwcreateenlistment.md) | The ZwCreateEnlistment routine creates a new enlistment object for a transaction. |
| [ZwCreateFile function](..\wmiguid\nf-wdm-zwcreatefile.md) | The ZwCreateFile routine creates a new file or opens an existing file. |
| [ZwCreateKey function](..\wmiguid\nf-wdm-zwcreatekey.md) | The ZwCreateKey routine creates a new registry key or opens an existing one. |
| [ZwCreateKeyTransacted function](..\wmiguid\nf-wdm-zwcreatekeytransacted.md) | The ZwCreateKeyTransacted routine creates a new registry key or opens an existing one, and it associates the key with a transaction. |
| [ZwCreateResourceManager function](..\wmiguid\nf-wdm-zwcreateresourcemanager.md) | The ZwCreateResourceManager routine creates a resource manager object. |
| [ZwCreateSection function](..\wmiguid\nf-wdm-zwcreatesection.md) | The ZwCreateSection routine creates a section object. |
| [ZwCreateTransaction function](..\wmiguid\nf-wdm-zwcreatetransaction.md) | The ZwCreateTransaction routine creates a transaction object. |
| [ZwCreateTransactionManager function](..\wmiguid\nf-wdm-zwcreatetransactionmanager.md) | The ZwCreateTransactionManager routine creates a new transaction manager object. |
| [ZwDeleteKey function](..\wmiguid\nf-wdm-zwdeletekey.md) | The ZwDeleteKey routine deletes an open key from the registry. |
| [ZwDeleteValueKey function](..\wmiguid\nf-wdm-zwdeletevaluekey.md) | The ZwDeleteValueKey routine deletes a value entry matching a name from an open key in the registry. If no such entry exists, an error is returned. |
| [ZwDeviceIoControlFile function](..\wmiguid\nf-ntddk-zwdeviceiocontrolfile.md) | The ZwDeviceIoControlFile routine sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified operation. |
| [ZwEnumerateKey function](..\wmiguid\nf-wdm-zwenumeratekey.md) | The ZwEnumerateKey routine returns information about a subkey of an open registry key. |
| [ZwEnumerateTransactionObject function](..\wmiguid\nf-wdm-zwenumeratetransactionobject.md) | The ZwEnumerateTransactionObject routine enumerates the KTM objects on a computer. |
| [ZwEnumerateValueKey function](..\wmiguid\nf-wdm-zwenumeratevaluekey.md) | The ZwEnumerateValueKey routine gets information about the value entries of an open key. |
| [ZwFlushKey function](..\wmiguid\nf-wdm-zwflushkey.md) | The ZwFlushKey routine forces a registry key to be committed to disk. |
| [ZwGetNotificationResourceManager function](..\wmiguid\nf-wdm-zwgetnotificationresourcemanager.md) | The ZwGetNotificationResourceManager routine retrieves the next transaction notification from a specified resource manager's notification queue. |
| [ZwLoadDriver function](..\wmiguid\nf-wdm-zwloaddriver.md) | The ZwLoadDriver routine loads a driver into the system. |
| [ZwMakeTemporaryObject function](..\wmiguid\nf-wdm-zwmaketemporaryobject.md) | The ZwMakeTemporaryObject routine changes the attributes of an object to make it temporary. |
| [ZwMapViewOfSection function](..\wmiguid\nf-wdm-zwmapviewofsection.md) | The ZwMapViewOfSection routine maps a view of a section into the virtual address space of a subject process. |
| [ZwOpenEnlistment function](..\wmiguid\nf-wdm-zwopenenlistment.md) | The ZwOpenEnlistment routine obtains a handle to an existing enlistment object. |
| [ZwOpenEvent function](..\wmiguid\nf-wdm-zwopenevent.md) | The ZwOpenEvent routine opens a handle to an existing named event object with the specified desired access. |
| [ZwOpenFile function](..\wmiguid\nf-wdm-zwopenfile.md) | The ZwOpenFile routine opens an existing file, directory, device, or volume. |
| [ZwOpenKey function](..\wmiguid\nf-wdm-zwopenkey.md) | The ZwOpenKey routine opens an existing registry key. |
| [ZwOpenKeyEx function](..\wmiguid\nf-wdm-zwopenkeyex.md) | The ZwOpenKeyEx routine opens an existing registry key. |
| [ZwOpenKeyTransacted function](..\wmiguid\nf-wdm-zwopenkeytransacted.md) | The ZwOpenKeyTransacted routine opens an existing registry key and associates the key with a transaction. |
| [ZwOpenKeyTransactedEx function](..\wmiguid\nf-wdm-zwopenkeytransactedex.md) | The ZwOpenKeyTransactedEx routine opens an existing registry key and associates the key with a transaction. |
| [ZwOpenProcess function](..\wmiguid\nf-ntddk-zwopenprocess.md) | The ZwOpenProcess routine opens a handle to a process object and sets the access rights to this object. |
| [ZwOpenResourceManager function](..\wmiguid\nf-wdm-zwopenresourcemanager.md) | The ZwOpenResourceManager routine returns a handle to an existing resource manager object. |
| [ZwOpenSection function](..\wmiguid\nf-wdm-zwopensection.md) | The ZwOpenSection routine opens a handle for an existing section object. |
| [ZwOpenSymbolicLinkObject function](..\wmiguid\nf-wdm-zwopensymboliclinkobject.md) | The ZwOpenSymbolicLinkObject routine opens an existing symbolic link. |
| [ZwOpenTransaction function](..\wmiguid\nf-wdm-zwopentransaction.md) | The ZwOpenTransaction routine obtains a handle to an existing transaction object. |
| [ZwOpenTransactionManager function](..\wmiguid\nf-wdm-zwopentransactionmanager.md) | The ZwOpenTransactionManager routine obtains a handle to an existing transaction manager object. |
| [ZwPowerInformation function](..\wmiguid\nf-ntddk-zwpowerinformation.md) | The ZwPowerInformation routine sets or retrieves system power information. |
| [ZwPrePrepareComplete function](..\wmiguid\nf-wdm-zwprepreparecomplete.md) | The ZwPrePrepareComplete routine notifies KTM that the calling resource manager has finished preliminary preparation of a transaction's data. |
| [ZwPrePrepareEnlistment function](..\wmiguid\nf-wdm-zwpreprepareenlistment.md) | The ZwPrePrepareEnlistment routine initiates the pre-prepare operation for a specified enlistment's transaction. |
| [ZwPrepareComplete function](..\wmiguid\nf-wdm-zwpreparecomplete.md) | The ZwPrepareComplete routine notifies KTM that the calling resource manager has finished preparing a transaction's data. |
| [ZwPrepareEnlistment function](..\wmiguid\nf-wdm-zwprepareenlistment.md) | The ZwPrepareEnlistment routine initiates the prepare operation for a specified enlistment's transaction. |
| [ZwQueryFullAttributesFile function](..\wmiguid\nf-wdm-zwqueryfullattributesfile.md) | The ZwQueryFullAttributesFile routine supplies network open information for the specified file. |
| [ZwQueryInformationEnlistment function](..\wmiguid\nf-wdm-zwqueryinformationenlistment.md) | The ZwQueryInformationEnlistment routine retrieves information about a specified enlistment object. |
| [ZwQueryInformationFile function](..\wmiguid\nf-wdm-zwqueryinformationfile.md) | The ZwQueryInformationFile routine returns various kinds of information about a file object. |
| [ZwQueryInformationResourceManager function](..\wmiguid\nf-wdm-zwqueryinformationresourcemanager.md) | The ZwQueryInformationResourceManager routine retrieves information about a specified resource manager object. |
| [ZwQueryInformationTransaction function](..\wmiguid\nf-wdm-zwqueryinformationtransaction.md) | The ZwQueryInformationTransaction routine retrieves information about a specified transaction. |
| [ZwQueryInformationTransactionManager function](..\wmiguid\nf-wdm-zwqueryinformationtransactionmanager.md) | The ZwQueryInformationTransactionManager routine retrieves information about a specified transaction manager object. |
| [ZwQueryKey function](..\wmiguid\nf-wdm-zwquerykey.md) | The ZwQueryKey routine provides information about the class of a registry key, and the number and sizes of its subkeys. |
| [ZwQuerySymbolicLinkObject function](..\wmiguid\nf-wdm-zwquerysymboliclinkobject.md) | The ZwQuerySymbolicLinkObject routine returns a Unicode string that contains the target of a symbolic link. |
| [ZwQueryValueKey function](..\wmiguid\nf-wdm-zwqueryvaluekey.md) | The ZwQueryValueKey routine returns a value entry for a registry key. |
| [ZwQueryVolumeInformationFile function](..\wmiguid\nf-ntddk-zwqueryvolumeinformationfile.md) | The ZwQueryVolumeInformationFile routine retrieves information about the volume associated with a given file, directory, storage device, or volume. |
| [ZwReadFile function](..\wmiguid\nf-wdm-zwreadfile.md) | The ZwReadFile routine reads data from an open file. |
| [ZwReadOnlyEnlistment function](..\wmiguid\nf-wdm-zwreadonlyenlistment.md) | The ZwReadOnlyEnlistment routine sets a specified enlistment to be read-only. |
| [ZwRecoverEnlistment function](..\wmiguid\nf-wdm-zwrecoverenlistment.md) | The ZwRecoverEnlistment routine initiates a recovery operation for the transaction that is associated with a specified enlistment. |
| [ZwRecoverResourceManager function](..\wmiguid\nf-wdm-zwrecoverresourcemanager.md) | The ZwRecoverResourceManager routine tries to recover the transaction that is associated with each enlistment of a specified resource manager object. |
| [ZwRecoverTransactionManager function](..\wmiguid\nf-wdm-zwrecovertransactionmanager.md) | The ZwRecoverTransactionManager routine reconstructs the state of the transaction manager object (including all transactions, enlistments, and resource managers) from the recovery information that is in the log stream. |
| [ZwRollbackComplete function](..\wmiguid\nf-wdm-zwrollbackcomplete.md) | The ZwRollbackComplete routine notifies KTM that the calling resource manager has finished rolling back a transaction's data. |
| [ZwRollbackEnlistment function](..\wmiguid\nf-wdm-zwrollbackenlistment.md) | The ZwRollbackEnlistment routine rolls back the transaction that is associated with a specified enlistment. |
| [ZwRollbackTransaction function](..\wmiguid\nf-wdm-zwrollbacktransaction.md) | The ZwRollbackTransaction routine initiates a rollback operation for a specified transaction. |
| [ZwRollforwardTransactionManager function](..\wmiguid\nf-wdm-zwrollforwardtransactionmanager.md) | The ZwRollforwardTransactionManager routine initiates recovery operations for all of the in-progress transactions that are assigned to a specified transaction manager. |
| [ZwSetInformationEnlistment function](..\wmiguid\nf-wdm-zwsetinformationenlistment.md) | The ZwSetInformationEnlistment routine sets information for a specified enlistment object. |
| [ZwSetInformationFile function](..\wmiguid\nf-wdm-zwsetinformationfile.md) | The ZwSetInformationFile routine changes various kinds of information about a file object. |
| [ZwSetInformationResourceManager function](..\wmiguid\nf-wdm-zwsetinformationresourcemanager.md) | The ZwSetInformationResourceManager routine is not used. |
| [ZwSetInformationThread function](..\wmiguid\nf-ntddk-zwsetinformationthread.md) | The ZwSetInformationThread routine sets the priority of a thread. |
| [ZwSetInformationTransaction function](..\wmiguid\nf-wdm-zwsetinformationtransaction.md) | The ZwSetInformationTransaction routine sets information for a specified transaction. |
| [ZwSetValueKey function](..\wmiguid\nf-wdm-zwsetvaluekey.md) | The ZwSetValueKey routine creates or replaces a registry key's value entry. |
| [ZwSinglePhaseReject function](..\wmiguid\nf-wdm-zwsinglephasereject.md) | The ZwSinglePhaseReject routine informs KTM that the calling resource manager will not support single-phase commit operations for a specified enlistment. |
| [ZwTerminateProcess function](..\wmiguid\nf-ntddk-zwterminateprocess.md) | The ZwTerminateProcess routine terminates a process and all of its threads. |
| [ZwUnloadDriver function](..\wmiguid\nf-wdm-zwunloaddriver.md) | The ZwUnloadDriver routine unloads a driver from the system. |
| [ZwUnmapViewOfSection function](..\wmiguid\nf-wdm-zwunmapviewofsection.md) | The ZwUnmapViewOfSection routine unmaps a view of a section from the virtual address space of a subject process. |
| [ZwWriteFile function](..\wmiguid\nf-wdm-zwwritefile.md) | The ZwWriteFile routine writes data to an open file. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [ExFreePool macro](..\wmiguid\nf-ntddk-exfreepool.md) | The ExFreePool routine deallocates a block of pool memory. |
| [ExInterlockedAddLargeStatistic macro](..\wmiguid\nf-wdm-exinterlockedaddlargestatistic.md) | The ExInterlockedAddLargeStatistic routine performs an interlocked addition of a ULONG increment value to a LARGE_INTEGER variable. |
| [ExInterlockedCompareExchange64 macro](..\wmiguid\nf-wdm-exinterlockedcompareexchange64.md) | The ExInterlockedCompareExchange64 routine compares one integer variable to another and, if they are equal, sets the first variable to a caller-supplied value. |
| [ExInterlockedFlushSList macro](..\wmiguid\nf-wdm-exinterlockedflushslist.md) | The ExInterlockedFlushSList routine atomically removes all entries from a sequenced singly linked list. |
| [ExInterlockedPopEntrySList macro](..\wmiguid\nf-wdm-exinterlockedpopentryslist.md) | The ExInterlockedPopEntrySList routine atomically removes the first entry from a sequenced singly linked list. |
| [ExInterlockedPushEntrySList macro](..\wmiguid\nf-wdm-exinterlockedpushentryslist.md) | The ExInterlockedPushEntrySList routine atomically inserts an entry at the beginning of a sequenced singly linked list. |
| [FIELD_OFFSET macro](..\wmiguid\nf-wdm-field_offset.md) | The FIELD_OFFSET macro returns the byte offset of a named field in a known structure type. |
| [IoAcquireRemoveLock macro](..\wmiguid\nf-wdm-ioacquireremovelock.md) | The IoAcquireRemoveLock routine increments the count for a remove lock, indicating that the associated device object should not be detached from the device stack or deleted. |
| [IoAdjustPagingPathCount macro](..\wmiguid\nf-wdm-ioadjustpagingpathcount.md) | The IoAdjustPagingPathCount routine increments or decrements a caller-supplied page-file counter as an atomic operation. |
| [IoAssignArcName macro](..\wmiguid\nf-ntddk-ioassignarcname.md) | The IoAssignArcName routine creates a symbolic link between the ARC name of a physical device and the name of the corresponding device object when it has been created. |
| [IoCallDriver macro](..\wmiguid\nf-wdm-iocalldriver.md) | The IoCallDriver routine sends an IRP to the driver associated with a specified device object. |
| [IoCompleteRequest macro](..\wmiguid\nf-wdm-iocompleterequest.md) | The IoCompleteRequest routine indicates that the caller has completed all processing for a given I/O request and is returning the given IRP to the I/O manager. |
| [IoDeassignArcName macro](..\wmiguid\nf-ntddk-iodeassignarcname.md) | The IoDeassignArcName routine removes a symbolic link between the ARC name for a device and the named device object. |
| [IoGetFunctionCodeFromCtlCode macro](..\wmiguid\nf-wdm-iogetfunctioncodefromctlcode.md) | The IoGetFunctionCodeFromCtlCode macro returns the value of the function code contained in an I/O control code. |
| [IoInitializeRemoveLock macro](..\wmiguid\nf-wdm-ioinitializeremovelock.md) | The IoInitializeRemoveLock routine initializes a remove lock for a device object. |
| [IoIsErrorUserInduced macro](..\wmiguid\nf-wdm-ioiserroruserinduced.md) | The IoIsErrorUserInduced routine determines whether an I/O error encountered while processing a request to a removable-media device was caused by the user. |
| [IoReleaseRemoveLock macro](..\wmiguid\nf-wdm-ioreleaseremovelock.md) | The IoReleaseRemoveLock routine releases a remove lock acquired with a previous call to IoAcquireRemoveLock. |
| [IoReleaseRemoveLockAndWait macro](..\wmiguid\nf-wdm-ioreleaseremovelockandwait.md) | The IoReleaseRemoveLockAndWait routine releases a remove lock that the driver acquired in a previous call to IoAcquireRemoveLock, and waits until all acquisitions of the lock have been released. |
| [IoSizeOfIrp macro](..\wmiguid\nf-wdm-iosizeofirp.md) | The IoSizeOfIrp routine determines the size in bytes for an IRP, given the number of stack locations in the IRP. |
| [KeAcquireSpinLock macro](..\wmiguid\nf-wdm-keacquirespinlock.md) | The KeAcquireSpinLock routine acquires a spin lock so the caller can synchronize access to shared data in a multiprocessor-safe way by raising IRQL. |
| [KeAcquireSpinLockAtDpcLevel macro](..\wmiguid\nf-wdm-keacquirespinlockatdpclevel.md) | The KeAcquireSpinLockAtDpcLevel routine acquires a spin lock when the caller is already running at IRQL &gt;= DISPATCH_LEVEL. |
| [KeLowerIrql macro](..\wmiguid\nf-wdm-kelowerirql.md) | The KeLowerIrql routine restores the IRQL on the current processor to its original value. |
| [KeQuerySystemTime macro](..\wmiguid\nf-wdm-kequerysystemtime.md) | The KeQuerySystemTime routine obtains the current system time. |
| [KeQueryTickCount macro](..\wmiguid\nf-ntddk-kequerytickcount.md) | The KeQueryTickCount routine maintains a count of the interval timer interrupts that have occurred since the system was booted. |
| [KeQueryTickCount macro](..\wmiguid\nf-wdm-kequerytickcount.md) | The KeQueryTickCount routine maintains a count of the interval timer interrupts that have occurred since the system was booted. |
| [KeRaiseIrql macro](..\wmiguid\nf-wdm-keraiseirql.md) | The KeRaiseIrql routine raises the hardware priority to the specified IRQL value, thereby masking off interrupts of equivalent or lower IRQL on the current processor. |
| [KeReleaseSpinLock macro](..\wmiguid\nf-wdm-kereleasespinlock.md) | The KeReleaseSpinLock routine releases a spin lock and restores the original IRQL at which the caller was running. |
| [KeReleaseSpinLockFromDpcLevel macro](..\wmiguid\nf-wdm-kereleasespinlockfromdpclevel.md) | The KeReleaseSpinLockFromDpcLevel routine releases an executive spin lock without changing the IRQL. |
| [MmGetSystemAddressForMdl macro](..\wmiguid\nf-wdm-mmgetsystemaddressformdl.md) | The MmGetSystemAddressForMdl routine is obsolete for Windows 2000 and later versions of Windows, and for Windows Me. |
| [MmLockPagableCodeSection macro](..\wmiguid\nf-wdm-mmlockpagablecodesection.md) | The MmLockPagableCodeSection routine locks a section of driver code, containing a set of driver routines marked with a special compiler directive, into system space. |
| [ObDereferenceObject macro](..\wmiguid\nf-wdm-obdereferenceobject.md) | The ObDereferenceObject routine decrements the given object's reference count and performs retention checks. |
| [ObDereferenceObjectWithTag macro](..\wmiguid\nf-wdm-obdereferenceobjectwithtag.md) | The ObDereferenceObjectWithTag routine decrements the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing. |
| [ObReferenceObject macro](..\wmiguid\nf-wdm-obreferenceobject.md) | The ObReferenceObject routine increments the reference count to the given object. |
| [ObReferenceObjectWithTag macro](..\wmiguid\nf-wdm-obreferenceobjectwithtag.md) | The ObReferenceObjectWithTag routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing. |
| [READ_REGISTER_UCHAR macro](..\wmiguid\nf-ioaccess-read_register_uchar.md) | The READ_REGISTER_UCHAR routine reads a byte from the specified register address. |
| [READ_REGISTER_ULONG macro](..\wmiguid\nf-ioaccess-read_register_ulong.md) | The READ_REGISTER_ULONG routine reads a ULONG value from the specified register address. |
| [READ_REGISTER_USHORT macro](..\wmiguid\nf-ioaccess-read_register_ushort.md) | The READ_REGISTER_USHORT routine reads a USHORT value from the specified register address. |
| [RtlAnsiStringToUnicodeSize macro](..\wmiguid\nf-wdm-rtlansistringtounicodesize.md) | The RtlAnsiStringToUnicodeSize routine returns the number of bytes required to hold an ANSI string converted into a Unicode string. |
| [RtlCheckBit macro](..\wmiguid\nf-wdm-rtlcheckbit.md) | The RtlCheckBit routine determines whether a particular bit in a given bitmap variable is clear or set. |
| [RtlCopyMemory macro](..\wmiguid\nf-wdm-rtlcopymemory.md) | The RtlCopyMemory routine copies the contents of a source memory block to a destination memory block. |
| [RtlEqualMemory macro](..\wmiguid\nf-wdm-rtlequalmemory.md) | The RtlEqualMemory routine compares two blocks of memory to determine whether the specified number of bytes are identical. |
| [RtlFillMemory macro](..\wmiguid\nf-wdm-rtlfillmemory.md) | The RtlFillMemory routine fills a block of memory with the specified fill value. |
| [RtlIntPtrToUnicodeString macro](..\wmiguid\nf-wdm-rtlintptrtounicodestring.md) | The RtlIntPtrToUnicodeString routine converts a specified ULONG_PTR value to a Unicode string that represents the value in a specified base. |
| [RtlMoveMemory macro](..\wmiguid\nf-wdm-rtlmovememory.md) | The RtlMoveMemory routine copies the contents of a source memory block to a destination memory block, and supports overlapping source and destination memory blocks. |
| [RtlUlongByteSwap macro](..\wmiguid\nf-wdm-rtlulongbyteswap.md) | The RtlUlongByteSwap routine reverses the ordering of the four bytes in a 32-bit unsigned integer value. |
| [RtlUlonglongByteSwap macro](..\wmiguid\nf-wdm-rtlulonglongbyteswap.md) | The RtlUlonglongByteSwap routine reverses the ordering of the eight bytes in a 64-bit unsigned integer value. |
| [RtlUnicodeStringToAnsiSize macro](..\wmiguid\nf-wdm-rtlunicodestringtoansisize.md) | The RtlUnicodeStringToAnsiSize routine returns the number of bytes required for a null-terminated ANSI string that is equivalent to a specified Unicode string. |
| [RtlUshortByteSwap macro](..\wmiguid\nf-wdm-rtlushortbyteswap.md) | The RtlUshortByteSwap routine reverses the ordering of the two bytes in a 16-bit unsigned integer value. |
| [RtlZeroMemory macro](..\wmiguid\nf-wdm-rtlzeromemory.md) | The RtlZeroMemory routine fills a block of memory with zeros, given a pointer to the block and the length, in bytes, to be filled. |
| [WRITE_REGISTER_UCHAR macro](..\wmiguid\nf-ioaccess-write_register_uchar.md) | The WRITE_REGISTER_UCHAR routine writes a byte to the specified address. |
| [WRITE_REGISTER_ULONG macro](..\wmiguid\nf-ioaccess-write_register_ulong.md) | The WRITE_REGISTER_ULONG routine writes a ULONG value to the specified address. |
| [WRITE_REGISTER_USHORT macro](..\wmiguid\nf-ioaccess-write_register_ushort.md) | The WRITE_REGISTER_USHORT routine writes a USHORT value to the specified address. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_SYSENV_ENUM_VARIABLES IOCTL](..\wmiguid\ni-ntddsysenv-ioctl_sysenv_enum_variables.md) | Returns information about system environment variables using SysEnv device. |
| [IOCTL_SYSENV_GET_VARIABLE IOCTL](..\wmiguid\ni-ntddsysenv-ioctl_sysenv_get_variable.md) | Gets the value of the specified system environment variables using SysEnv device. |
| [IOCTL_SYSENV_QUERY_VARIABLE_INFO IOCTL](..\wmiguid\ni-ntddsysenv-ioctl_sysenv_query_variable_info.md) | Returns information about system environment variables using SysEnv device. |
| [IOCTL_SYSENV_SET_VARIABLE IOCTL](..\wmiguid\ni-ntddsysenv-ioctl_sysenv_set_variable.md) | Sets the value of the specified system environment variables using SysEnv device. |
