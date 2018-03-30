---
UID: NA:minitape
ms.assetid: 80c8fbfb-18b9-395e-83eb-ae21dd19d444
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Minitape.h header



This header is used by Storage, Windows kernel. For more information, see
- [Storage](../_storage/index.md)
- [Windows kernel](../_kernel/index.md)

Minitape.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [ScsiDebugPrint function](nf-minitape-scsidebugprint.md) | The ScsiDebugPrint routine prints debug information with a level of verbosity based on global values set in the kernel debugger or set in the registry and initialized when the system boots. |
| [TapeClassAllocateSrbBuffer function](nf-minitape-tapeclassallocatesrbbuffer.md) | The TapeClassAllocateSrbBuffer routine allocates an Srb-&gt;DataBuffer. |
| [TapeClassCompareMemory function](nf-minitape-tapeclasscomparememory.md) | The TapeClassCompareMemory routine compares two memory buffers and returns the number of bytes that are equivalent. |
| [TapeClassInitialize function](nf-minitape-tapeclassinitialize.md) | The TapeClassInitialize routine performs much of the driver and device initialization on behalf of a miniclass driver. |
| [TapeClassLiDiv function](nf-minitape-tapeclasslidiv.md) | The TapeClassLiDiv routine performs a division of the two indicated integers. |
| [TapeClassLogicalBlockToPhysicalBlock function](nf-minitape-tapeclasslogicalblocktophysicalblock.md) | The TapeClassLogicalBlockToPhysicalBlock routine translates a pseudological block address to a physical block address. This routine is for SCSI-1 devices. |
| [TapeClassPhysicalBlockToLogicalBlock function](nf-minitape-tapeclassphysicalblocktologicalblock.md) | The TapeClassPhysicalBlockToLogicalBlock routine translates a physical block address to a pseudological block address. This routine is for SCSI-1 devices. |
| [TapeClassZeroMemory function](nf-minitape-tapeclasszeromemory.md) | The TapeClassZeroMemory routine fills a buffer with zeros. |
| [TapeDebugPrint function](nf-minitape-tapedebugprint.md) | The TapeDebugPrint routine prints the indicated string. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [TAPE_ERROR_ROUTINE callback](nc-minitape-tape_error_routine.md) | TAPE_ERROR_ROUTINE provides device-specific error handling when an SRB is completed with an error status. This routine is optional. |
| [TAPE_EXTENSION_INIT_ROUTINE callback](nc-minitape-tape_extension_init_routine.md) | ExtensionInit initializes an optional, driver-specific context area. This routine is called by TapeClassInitialize when the tape miniclass driver is loaded. This routine is optional. |
| [TAPE_PROCESS_COMMAND_ROUTINE callback](nc-minitape-tape_process_command_routine.md) | TAPE_PROCESS_COMMAND_ROUTINE handles the device-specific aspects of an IOCTL request. |
| [TAPE_VERIFY_INQUIRY_ROUTINE callback](nc-minitape-tape_verify_inquiry_routine.md) | TAPE_VERIFY_INQUIRY_ROUTINE determines whether the tape miniclass driver recognizes and supports a given device. This routine is required. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [BLOCK_DEVICE_RANGE_DESCRIPTOR structure](ns-minitape-block_device_range_descriptor.md) | The BLOCK_DEVICE_RANGE_DESCRIPTOR structure describes a range of logical blocks associated with various fragments of a file for an offload copy operation. |
| [BLOCK_DEVICE_TOKEN_DESCRIPTOR structure](ns-minitape-block_device_token_descriptor.md) | BLOCK_DEVICE_TOKEN_DESCRIPTOR contains the token returned from a the POPULATE TOKEN command for an offload read data operation. |
| [POPULATE_TOKEN_HEADER structure](ns-minitape-populate_token_header.md) | A populate token parameter list starts with a POPULATE_TOKEN_HEADER structure. This is the header for the parameters in a command data block (CDB) of the POPULATE TOKEN command. |
| [PRI_REGISTRATION_LIST structure](ns-minitape-pri_registration_list.md) | The PRI_REGISTRATION_LIST structure is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_KEYS. |
| [PRI_RESERVATION_DESCRIPTOR structure](ns-minitape-pri_reservation_descriptor.md) | The PRI_RESERVATION_DESCRIPTOR structure is used to construct the PRI_RESERVATION_LIST structure that is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_RESERVATIONS. |
| [PRI_RESERVATION_LIST structure](ns-minitape-pri_reservation_list.md) | The PRI_RESERVATION_LIST structure is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_RESERVATIONS. |
| [PRO_PARAMETER_LIST structure](ns-minitape-pro_parameter_list.md) | The PRO_PARAMETER_LIST structure is sent in a Persistent Reserve Out command to a device server. |
| [RECEIVE_TOKEN_INFORMATION_HEADER structure](ns-minitape-receive_token_information_header.md) | The RECEIVE_TOKEN_INFORMATION_HEADER structure contains information returned as status from an offload data transfer operation. |
| [RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure](ns-minitape-receive_token_information_response_header.md) | A token, created as a representation of data (ROD), for an offload read data operation is returned in a RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure. |
| [RT_PARAMETER_DATA structure](ns-minitape-rt_parameter_data.md) | The RT_PARAMETER_DATA structure contains the parameter data for the report timestamp command. |
| [ST_PARAMETER_DATA structure](ns-minitape-st_parameter_data.md) | The ST_PARAMETER_DATA structure contains the parameter list for the set timestamp command. |
| [WRITE_USING_TOKEN_HEADER structure](ns-minitape-write_using_token_header.md) | The WRITE_USING_TOKEN_HEADER structure describes the destination data locations for an offload write data operation. |
| [_DEVICE_MEDIA_INFO structure](ns-minitape-_device_media_info.md) | A storage class driver returns an array of DEVICE_MEDIA_INFO structures, embedded in a GET_MEDIA_TYPES structure, in response to an IOCTL_STORAGE_GET_MEDIA_TYPES_EX device-control request. |
| [_GET_MEDIA_TYPES structure](ns-minitape-_get_media_types.md) | The GET_MEDIA_TYPES structure is used in conjunction with the IOCTL_STORAGE_GET_MEDIA_TYPES_EX request to retrieve information about the types of media supported by a device. |
| [_GROUP_AFFINITY structure](ns-minitape-_group_affinity.md) | The GROUP_AFFINITY structure specifies a group number and the processor affinity within that group. |
| [_INQUIRYDATA structure](ns-minitape-_inquirydata.md) | The INQUIRYDATA structure is used in conjunction with the TapeMiniExtensionInit and TapeMiniVerifyInquiry routines to report SCSI inquiry data associated with a tape device. |
| [_PROCESSOR_NUMBER structure](ns-minitape-_processor_number.md) | The PROCESSOR_NUMBER structure identifies a processor by its group number and group-relative processor number. |
| [_REPORT_ZONES_DATA structure](ns-minitape-_report_zones_data.md) | Note  This structure is for internal use only and should not be called from your code. . |
| [_SCSI_PNP_REQUEST_BLOCK structure](ns-minitape-_scsi_pnp_request_block.md) | TheSCSI_PNP_REQUEST_BLOCK structure is a special version of a SCSI_REQUEST_BLOCK that is used for plug and play (PNP) requests.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [_SCSI_POWER_REQUEST_BLOCK structure](ns-minitape-_scsi_power_request_block.md) | The SCSI_POWER_REQUEST_BLOCK structure is a special version of a SCSI_REQUEST_BLOCK that is used for power management requests.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [_SCSI_REQUEST_BLOCK structure](ns-minitape-_scsi_request_block.md) | SCSI_REQUEST_BLOCK structure |
| [_SCSI_WMI_REQUEST_BLOCK structure](ns-minitape-_scsi_wmi_request_block.md) | This structure is a special version of a SCSI_REQUEST_BLOCK for use with WMI commands. |
| [_SES_CONFIGURATION_DIAGNOSTIC_PAGE structure](ns-minitape-_ses_configuration_diagnostic_page.md) | TBD. |
| [_SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE structure](ns-minitape-_ses_download_microcode_control_diagnostic_page.md) | The SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE structure contains a vendor specific microcode (i.e., firmware) image for use by the enclosure services process. |
| [_SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR structure](ns-minitape-_ses_download_microcode_status_descriptor.md) | The SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR structure specifies the status and additional status of a download microcode. |
| [_SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE structure](ns-minitape-_ses_download_microcode_status_diagnostic_page.md) | The Download Microcode Status diagnostic page includes information about the status of one or more download microcode operations. |
| [_SRBEX_DATA structure](ns-minitape-_srbex_data.md) | The SRBEX_DATA structure is the generalized format for containing extended SRB data. |
| [_SRBEX_DATA_BIDIRECTIONAL structure](ns-minitape-_srbex_data_bidirectional.md) | The SRBEX_DATA_BIDIRECTIONAL structure contains the extended SRB data for bi-directional transfer commands. |
| [_SRBEX_DATA_IO_INFO structure](ns-minitape-_srbex_data_io_info.md) | The SRBEX_DATA_IO_INFO structure contains additional information related to a read or write request in an extended SRB. |
| [_SRBEX_DATA_PNP structure](ns-minitape-_srbex_data_pnp.md) | The SRBEX_DATA_PNP structure contains the request data for an extended plug and play (PNP) SRB. |
| [_SRBEX_DATA_POWER structure](ns-minitape-_srbex_data_power.md) | The SRBEX_DATA_POWER structure contains the request data for an extended power SRB. |
| [_SRBEX_DATA_SCSI_CDB16 structure](ns-minitape-_srbex_data_scsi_cdb16.md) | The SRBEX_DATA_SCSI_CDB16 structure contains the extended SRB data for a 16-byte SCSI command data block (CDB). |
| [_SRBEX_DATA_SCSI_CDB32 structure](ns-minitape-_srbex_data_scsi_cdb32.md) | The SRBEX_DATA_SCSI_CDB32 structure contains the extended SRB data for a 32-byte SCSI command data block (CDB). |
| [_SRBEX_DATA_SCSI_CDB_VAR structure](ns-minitape-_srbex_data_scsi_cdb_var.md) | The SRBEX_DATA_SCSI_CDB_VAR structure contains the extended SRB data for a variable length SCSI command data block (CDB). |
| [_SRBEX_DATA_WMI structure](ns-minitape-_srbex_data_wmi.md) | The SRBEX_DATA_WMI structure contains the request data for an extended WMI SRB. |
| [_STORAGE_PREDICT_FAILURE structure](ns-minitape-_storage_predict_failure.md) | The STORAGE_PREDICT_FAILURE structure is used in conjunction with IOCTL_STORAGE_PREDICT_FAILURE to report whether a device is currently predicting a failure. |
| [_STORAGE_REQUEST_BLOCK structure](ns-minitape-_storage_request_block.md) | The STORAGE_REQUEST_BLOCK is the extended format SCSI Request Block (SRB) structure. |
| [_STOR_ADDRESS structure](ns-minitape-_stor_address.md) | A general structure for holding a storage device address. |
| [_STOR_ADDR_BTL8 structure](ns-minitape-_stor_addr_btl8.md) | The STOR_ADDR_BTL8 address structure contains the addressing information for an 8-bit Bus-Target-LUN (BTL8) address. |
| [_STOR_DEVICE_CAPABILITIES structure](ns-minitape-_stor_device_capabilities.md) | The STOR_DEVICE_CAPABILITIES structure reports device capabilities to the Storport driver in response to a capabilities query in a SCSI request block (SRB) with a function of SRB_FUNCTION_PNP. |
| [_STOR_DEVICE_CAPABILITIES_EX structure](ns-minitape-_stor_device_capabilities_ex.md) | The STOR_DEVICE_CAPABILITIES_EX structure reports device capabilities to the Storport driver in response to a capabilities query in a SCSI request block (SRB) with a function of SRB_FUNCTION_PNP. |
| [_TAPE_CREATE_PARTITION structure](ns-minitape-_tape_create_partition.md) | The TAPE_CREATE_PARTITION structure is used in conjunction with the IOCTL_TAPE_CREATE_PARTITION request to create a specified number of fixed, select, or initiator partitions of a given size on the tape media. |
| [_TAPE_ERASE structure](ns-minitape-_tape_erase.md) | The TAPE_ERASE structure is used in conjunction with the IOCTL_TAPE_ERASE request to erase the current tape partition. |
| [_TAPE_GET_DRIVE_PARAMETERS structure](ns-minitape-_tape_get_drive_parameters.md) | The TAPE_GET_DRIVE_PARAMETERS structure is used in conjunction with the IOCTL_TAPE_GET_DRIVE_PARAMS request to retrieve information about capabilities of the tape drive. |
| [_TAPE_GET_MEDIA_PARAMETERS structure](ns-minitape-_tape_get_media_parameters.md) | The TAPE_GET_MEDIA_PARAMETERS structure is used in conjunction with the TapeMiniGetMediaParameters routine to retrieve tape media parameters. |
| [_TAPE_GET_POSITION structure](ns-minitape-_tape_get_position.md) | The TAPE_GET_POSITION structure is used in conjunction with the IOCTL_TAPE_GET_POSITION request to retrieve the current absolute, logical, or pseudological partition and offset position on the tape. |
| [_TAPE_INIT_DATA structure](ns-minitape-_tape_init_data.md) | TAPE_INIT_DATA is used only by legacy tape miniclass drivers. Use TAPE_INIT_DATA_EX instead. |
| [_TAPE_INIT_DATA_EX structure](ns-minitape-_tape_init_data_ex.md) | TAPE_INIT_DATA_EX defines values and routines that are specific to a Windows 2000 tape miniclass driver. The tape miniclass DriverEntry routine passes this information to the tape class driver to complete miniclass driver initialization. |
| [_TAPE_PREPARE structure](ns-minitape-_tape_prepare.md) | The TAPE_PREPARE structure is used in conjunction with the IOCTL_TAPE_PREPARE request to load or unload tape, reset the tape's tension, lock or unlock the ejection mechanism, or format the tape. |
| [_TAPE_SET_DRIVE_PARAMETERS structure](ns-minitape-_tape_set_drive_parameters.md) | The TAPE_SET_DRIVE_PARAMETERS structure is used in conjunction with the IOCTL_TAPE_SET_DRIVE_PARAMS request to adjust the configurable parameters of a tape drive. |
| [_TAPE_SET_MEDIA_PARAMETERS structure](ns-minitape-_tape_set_media_parameters.md) | The TAPE_SET_MEDIA_PARAMETERS structure is used in conjunction with the IOCTL_TAPE_SET_MEDIA_PARAMS request to reset the block size of the media in a tape drive. |
| [_TAPE_SET_POSITION structure](ns-minitape-_tape_set_position.md) | The TAPE_SET_POSITION structure is used in conjunction with the IOCTL_TAPE_SET_POSITION request to move the current position on the tape to the specified partition and offset. |
| [_TAPE_WMI_OPERATIONS structure](ns-minitape-_tape_wmi_operations.md) | The tape miniclass driver passes this structure to its TapeMiniWMIControl routine to indicate which WMI operation must be performed by the device. |
| [_TAPE_WRITE_MARKS structure](ns-minitape-_tape_write_marks.md) | The TAPE_WRITE_MARKS structure is used in conjunction with an IOCTL_TAPE_WRITE_MARKS request to write a setmark, a filemark, a short filemark, or a long filemark to tape. |
| [_TRACK_INFORMATION2 structure](ns-minitape-_track_information2.md) | The TRACK_INFORMATION2 structure is used to report track information. |
| [_VPD_THIRD_PARTY_COPY_PAGE structure](ns-minitape-_vpd_third_party_copy_page.md) | The VPD_THIRD_PARTY_COPY_PAGE structure defines the vital product data (VPD) page for offload data transfer operations. |
| [_VPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE structure](ns-minitape-_vpd_zoned_block_device_characteristics_page.md) | Note  This structure is for internal use only and should not be called from your code. . |
| [_WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR structure](ns-minitape-_windows_block_device_token_limits_descriptor.md) | The WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR structure is the third party copy descriptor for Windows systems. |
| [_ZONE_DESCRIPTIOR structure](ns-minitape-_zone_descriptior.md) | Note  This structure is for internal use only and should not be called from your code. . |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [*PSTOR_POWER_ACTION enumeration](ne-minitape-pstor_power_action.md) | The STOR_POWER_ACTION enumerator indicates the power state that the system is about to enter during a power transition. |
| [_SES_DOWNLOAD_MICROCODE_STATE enumeration](ne-minitape-_ses_download_microcode_state.md) | TBD. |
| [_STORAGE_MEDIA_TYPE enumeration](ne-minitape-_storage_media_type.md) | The STORAGE_MEDIA_TYPE enumeration is used in conjunction with the IOCTL_STORAGE_GET_MEDIA_TYPES_EX request to query the class driver for the types of media that a device supports. |
| [_STOR_DEVICE_POWER_STATE enumeration](ne-minitape-_stor_device_power_state.md) | The STOR_DEVICE_POWER_STATE enumerator specifies a device power state. |
| [_TAPE_DRIVE_PROBLEM_TYPE enumeration](ne-minitape-_tape_drive_problem_type.md) | The TAPE_DRIVE_PROBLEM_TYPE enumerator is used to report problems with the tape drive. |
| [_TAPE_STATUS enumeration](ne-minitape-_tape_status.md) | The TAPE_STATUS enumeration provides a list of the status codes that the tape class driver uses to report the status of a tape device. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [FIELD_OFFSET macro](nf-minitape-field_offset.md) | The FIELD_OFFSET macro returns the byte offset of a named field in a known structure type. |
| [RtlZeroMemory macro](nf-minitape-rtlzeromemory.md) | The RtlZeroMemory routine fills a block of memory with zeros, given a pointer to the block and the length, in bytes, to be filled. |
