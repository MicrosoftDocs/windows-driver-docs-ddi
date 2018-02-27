---
UID: NA:ntddcdrm
ms.assetid: 21939472-b0b4-3c10-86e6-842cb8446575
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntddcdrm.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Ntddcdrm.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_CDROM_AUDIO_CONTROL structure](ns-ntddcdrm-_cdrom_audio_control.md) | The CDROM_AUDIO_CONTROL structure is used in conjunction with the IOCTL_CDROM_GET_CONTROL request to report the audio playback mode. |
| [_CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR structure](ns-ntddcdrm-_cdrom_exception_performance_descriptor.md) | The CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR structure indicates that the result data from the IOCTL_CDROM_GET_PERFORMANCE I/O control request is for exception conditions. |
| [_CDROM_EXCLUSIVE_ACCESS structure](ns-ntddcdrm-_cdrom_exclusive_access.md) | The CDROM_EXCLUSIVE_ACCESS structure is used with the IOCTL_CDROM_EXCLUSIVE_ACCESS request to query the access state of a CD-ROM device or to lock or unlock the device for exclusive access. |
| [_CDROM_EXCLUSIVE_LOCK structure](ns-ntddcdrm-_cdrom_exclusive_lock.md) | The CDROM_EXCLUSIVE_LOCK structure is used with the IOCTL_CDROM_EXCLUSIVE_ACCESS request to lock a CD-ROM device for exclusive access. |
| [_CDROM_EXCLUSIVE_LOCK_STATE structure](ns-ntddcdrm-_cdrom_exclusive_lock_state.md) | The CDROM_EXCLUSIVE_LOCK_STATE structure is used by the CD-ROM class driver to report the exclusive access state of a CD-ROM device. |
| [_CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR structure](ns-ntddcdrm-_cdrom_nominal_performance_descriptor.md) | The CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR structure gives the host an approximation of logical unit performance. |
| [_CDROM_PERFORMANCE_HEADER structure](ns-ntddcdrm-_cdrom_performance_header.md) | The CDROM_PERFORMANCE_HEADER structure is used by the IOCTL_CDROM_GET_PERFORMANCE IOCTL to return data. When the request type is CdromPerformanceRequest, the IOCTL returns this header followed by optional descriptors. |
| [_CDROM_PERFORMANCE_REQUEST structure](ns-ntddcdrm-_cdrom_performance_request.md) | The CDROM_PERFORMANCE_REQUEST structure is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE I/O control request and describes the performance data requested. |
| [_CDROM_PLAY_AUDIO_MSF structure](ns-ntddcdrm-_cdrom_play_audio_msf.md) | Device control IRPs with a control code of IOCTL_CDROM_PLAY_AUDIO_MSF use this structure to play an audio CD. |
| [_CDROM_READ_TOC_EX structure](ns-ntddcdrm-_cdrom_read_toc_ex.md) | When drivers query a target CD-ROM device with IOCTL_CDROM_READ_TOC_EX they must define the query with this structure. |
| [_CDROM_SEEK_AUDIO_MSF structure](ns-ntddcdrm-_cdrom_seek_audio_msf.md) | The CDROM_SEEK_AUDIO_MSF structure contains the minute, second, and frame that the device must seek to upon receipt of a device control IRP with a control code of IOCTL_CDROM_SEEK_AUDIO_MSF. |
| [_CDROM_SET_SPEED structure](ns-ntddcdrm-_cdrom_set_speed.md) | The CDROM_SET_SPEED structure is used with the IOCTL_CDROM_SET_SPEED request to set the spindle speed of a CD-ROM drive during data transfers in which no data loss is permitted. |
| [_CDROM_SET_STREAMING structure](ns-ntddcdrm-_cdrom_set_streaming.md) | The CDROM_SET_SPEED structure is used with the IOCTL_CDROM_SET_SPEED request to set the spindle speed of a CD-ROM drive during isochronous transfers that permit some data loss. |
| [_CDROM_SIMPLE_OPC_INFO structure](ns-ntddcdrm-_cdrom_simple_opc_info.md) | The CDROM_SIMPLE_OPC_INFO structure is the only input for the IOCTL_CDROM_SEND_OPC_INFORMATION I/O control code. |
| [_CDROM_STREAMING_CONTROL structure](ns-ntddcdrm-_cdrom_streaming_control.md) | The CDROM_STREAMING_CONTROL structure is used as an input parameter to the IOCTL_CDROM_ENABLE_STREAMING IOCTL. |
| [_CDROM_SUB_Q_DATA_FORMAT structure](ns-ntddcdrm-_cdrom_sub_q_data_format.md) | The CDROM_SUB_Q_DATA_FORMAT structure is used with device control IRPs of type IOCTL_CDROM_READ_Q_CHANNEL. |
| [_CDROM_TOC structure](ns-ntddcdrm-_cdrom_toc.md) | Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_TOC return their output data in this structure followed by a series of TRACK_DATA structures. |
| [_CDROM_TOC_ATIP_DATA structure](ns-ntddcdrm-_cdrom_toc_atip_data.md) | Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_ATIP return their output data in this header structure followed by a series of descriptors of type CDROM_TOC_ATIP_DATA_BLOCK. |
| [_CDROM_TOC_ATIP_DATA_BLOCK structure](ns-ntddcdrm-_cdrom_toc_atip_data_block.md) | Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_ATIP return their output data in a header structure of type CDROM_TOC_ATIP_DATA followed by a series of ATIP data block descriptors defined by CDROM_TOC_ATIP_DATA_BLOCK. |
| [_CDROM_TOC_CD_TEXT_DATA structure](ns-ntddcdrm-_cdrom_toc_cd_text_data.md) | Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_CDTEXT return their output data in this structure followed by a series of descriptors of type CDROM_TOC_CD_TEXT_DATA_BLOCK. |
| [_CDROM_TOC_CD_TEXT_DATA_BLOCK structure](ns-ntddcdrm-_cdrom_toc_cd_text_data_block.md) | This structure contains CD text descriptor data used in conjunction with the data in the CDROM_TOC_CD_TEXT_DATA structure. |
| [_CDROM_TOC_FULL_TOC_DATA structure](ns-ntddcdrm-_cdrom_toc_full_toc_data.md) | Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_FULL_TOC return their output data in this structure optionally followed by a series of descriptors of type CDROM_TOC_FULL_TOC_DATA_BLOCK. |
| [_CDROM_TOC_FULL_TOC_DATA_BLOCK structure](ns-ntddcdrm-_cdrom_toc_full_toc_data_block.md) | The CDROM_TOC_FULL_TOC_DATA_BLOCK structure contains track descriptor data used in conjunction with the data from the CDROM_TOC_FULL_TOC_DATA structure. |
| [_CDROM_TOC_PMA_DATA structure](ns-ntddcdrm-_cdrom_toc_pma_data.md) | Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_PMA return their output data in this structure optionally followed by a series of descriptors of type CDROM_TOC_FULL_TOC_DATA_BLOCK. |
| [_CDROM_TOC_SESSION_DATA structure](ns-ntddcdrm-_cdrom_toc_session_data.md) | Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_SESSION return their output data in this structure followed by a series of TRACK_DATA structures. |
| [_CDROM_WRITE_SPEED_DESCRIPTOR structure](ns-ntddcdrm-_cdrom_write_speed_descriptor.md) | The CDROM_WRITE_SPEED_DESCRIPTOR structure is returned for the IOCTL_CDROM_GET_PERFORMANCE IOCTL when the request type is CdromWriteSpeedRequest. |
| [_CDROM_WRITE_SPEED_REQUEST structure](ns-ntddcdrm-_cdrom_write_speed_request.md) | The CDROM_WRITE_SPEED_REQUEST structure is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE IOCTL and for requesting write speed descriptors. |
| [_SUB_Q_CHANNEL_DATA structure](ns-ntddcdrm-_sub_q_channel_data.md) | Device control IRPs with a control code of IOCTL_CDROM_READ_Q_CHANNEL return their output data in this union. |
| [_SUB_Q_CURRENT_POSITION structure](ns-ntddcdrm-_sub_q_current_position.md) | The SUB_Q_CURRENT_POSITION structure contains position information and is used in conjunction with SUB_Q_CHANNEL_DATA. |
| [_SUB_Q_HEADER structure](ns-ntddcdrm-_sub_q_header.md) | The SUB_Q_HEADER structure contains audio status information and the length of the Q subchannel data being returned. This structure is used in conjunction with SUB_Q_CHANNEL_DATA. |
| [_SUB_Q_MEDIA_CATALOG_NUMBER structure](ns-ntddcdrm-_sub_q_media_catalog_number.md) | The SUB_Q_MEDIA_CATALOG_NUMBER structure contains position information and is used in conjunction with the SUB_Q_CHANNEL_DATA structure. |
| [_SUB_Q_TRACK_ISRC structure](ns-ntddcdrm-_sub_q_track_isrc.md) | The SUB_Q_TRACK_ISC contains position information and is used in conjunction with the SUB_Q_CHANNEL_DATA structure. |
| [_TRACK_DATA structure](ns-ntddcdrm-_track_data.md) | Track descriptor is used in conjunction with CDROM_TOC and CDROM_TOC_SESSION_DATA. |
| [_VOLUME_CONTROL structure](ns-ntddcdrm-_volume_control.md) | The VOLUME_CONTROL structure is used in conjunction with the IOCTL_CDROM_GET_VOLUME request to retrieve volume values for up to four audio ports. |
| [__RAW_READ_INFO structure](ns-ntddcdrm-__raw_read_info.md) | The RAW_READ_INFO structure is used in conjunction with the IOCTL_CDROM_RAW_READ request to read data from a CD-ROM in raw mode. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_CDROM_CHECK_VERIFY IOCTL](ni-ntddcdrm-ioctl_cdrom_check_verify.md) | In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by IOCTL_STORAGE_CHECK_VERIFY. The only difference between the two IOCTLs is the base value. |
| [IOCTL_CDROM_ENABLE_STREAMING IOCTL](ni-ntddcdrm-ioctl_cdrom_enable_streaming.md) | Enables or disables CDROM streaming mode on a per-handle basis for raw read and write requests. |
| [IOCTL_CDROM_EXCLUSIVE_ACCESS IOCTL](ni-ntddcdrm-ioctl_cdrom_exclusive_access.md) | The IOCTL_CDROM_EXCLUSIVE_ACCESS request instructs the CD-ROM class driver to |
| [IOCTL_CDROM_FIND_NEW_DEVICES IOCTL](ni-ntddcdrm-ioctl_cdrom_find_new_devices.md) | In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by IOCTL_STORAGE_FIND_NEW_DEVICES. The only difference between the two IOCTLs is the base value. |
| [IOCTL_CDROM_GET_CONFIGURATION IOCTL](ni-ntddcdrm-ioctl_cdrom_get_configuration.md) | Requests feature and profile information from a CD-ROM device. |
| [IOCTL_CDROM_GET_CONTROL IOCTL](ni-ntddcdrm-ioctl_cdrom_get_control.md) | This IOCTL request is obsolete. Do not use.Determines the current audio playback mode. |
| [IOCTL_CDROM_GET_DRIVE_GEOMETRY IOCTL](ni-ntddcdrm-ioctl_cdrom_get_drive_geometry.md) | Returns information about the CD-ROM's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector). |
| [IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX IOCTL](ni-ntddcdrm-ioctl_cdrom_get_drive_geometry_ex.md) | Returns information about a CD-ROM's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).The IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX request differs from the older IOCTL_CDROM_GET_DRIVE_GEOMETRY request. |
| [IOCTL_CDROM_GET_INQUIRY_DATA IOCTL](ni-ntddcdrm-ioctl_cdrom_get_inquiry_data.md) | Returns the SCSI inquiry data for the CD-ROM device. This IOCTL can be used when a device has been exclusively locked with IOCTL_CDROM_EXCLUSIVE_ACCESS. |
| [IOCTL_CDROM_GET_LAST_SESSION IOCTL](ni-ntddcdrm-ioctl_cdrom_get_last_session.md) | Queries the device for the first complete session number, the last complete session number, and the last complete session starting address. |
| [IOCTL_CDROM_GET_PERFORMANCE IOCTL](ni-ntddcdrm-ioctl_cdrom_get_performance.md) | Retrieves the supported speeds from the device. The IOCTL_CDROM_GET_PERFORMANCE I/O control request is a wrapper over the MMC command, GET PERFORMANCE. |
| [IOCTL_CDROM_GET_VOLUME IOCTL](ni-ntddcdrm-ioctl_cdrom_get_volume.md) | Determines the current volume for each of its device's audio ports. Obsolete, beginning with Windows Vista. |
| [IOCTL_CDROM_LOAD_MEDIA IOCTL](ni-ntddcdrm-ioctl_cdrom_load_media.md) | Draws a protruding CDROM tray back into the drive. |
| [IOCTL_CDROM_PAUSE_AUDIO IOCTL](ni-ntddcdrm-ioctl_cdrom_pause_audio.md) | Suspends audio play. Obsolete, beginning with Windows Vista. |
| [IOCTL_CDROM_PLAY_AUDIO_MSF IOCTL](ni-ntddcdrm-ioctl_cdrom_play_audio_msf.md) | Plays the specified range of the media. Obsolete, beginning with Windows Vista. |
| [IOCTL_CDROM_RAW_READ IOCTL](ni-ntddcdrm-ioctl_cdrom_raw_read.md) | Reads data from the CD-ROM in raw mode. |
| [IOCTL_CDROM_READ_Q_CHANNEL IOCTL](ni-ntddcdrm-ioctl_cdrom_read_q_channel.md) | Returns the current position, media catalog, or ISRC track data. Obsolete, beginning with Windows Vista. |
| [IOCTL_CDROM_READ_TOC IOCTL](ni-ntddcdrm-ioctl_cdrom_read_toc.md) | Returns the table of contents of the media. Obsolete, beginning with Windows Vista. |
| [IOCTL_CDROM_READ_TOC_EX IOCTL](ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md) | Queries the target device for the table of contents (TOC), the program memory area (PMA), and the absolute time in pregroove (ATIP). |
| [IOCTL_CDROM_RESUME_AUDIO IOCTL](ni-ntddcdrm-ioctl_cdrom_resume_audio.md) | Resumes a suspended audio operation. Obsolete, beginning with Windows Vista. |
| [IOCTL_CDROM_SEEK_AUDIO_MSF IOCTL](ni-ntddcdrm-ioctl_cdrom_seek_audio_msf.md) | Moves the heads to the specified MSF on the media. Obsolete, beginning with Windows Vista. |
| [IOCTL_CDROM_SEND_OPC_INFORMATION IOCTL](ni-ntddcdrm-ioctl_cdrom_send_opc_information.md) | The IOCTL_CDROM_SEND_OPC_INFORMATION control code can be used in file systems and other implementations that want to perform the Optimum Power Calibration (OPC) procedure in advance, so that the first streaming write does not have to wait for the procedure to finish. The optical drive performs the OPC procedure to determine the optimum power of the laser during write. The procedure is necessary to ensure quality, but it wears out the media and should not be performed too often. |
| [IOCTL_CDROM_SET_SPEED IOCTL](ni-ntddcdrm-ioctl_cdrom_set_speed.md) | Sets the spindle speed of the CD-ROM drive. |
| [IOCTL_CDROM_SET_VOLUME IOCTL](ni-ntddcdrm-ioctl_cdrom_set_volume.md) | Resets the volume for its device's audio ports. Obsolete, beginning with Windows Vista. |
| [IOCTL_CDROM_STOP_AUDIO IOCTL](ni-ntddcdrm-ioctl_cdrom_stop_audio.md) | Ends audio play. Obsolete, beginning with Windows Vista. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_CDROM_OPC_INFO_TYPE enumeration](ne-ntddcdrm-_cdrom_opc_info_type.md) | The CDROM_OPC_INFO_TYPE enumeration is a member of the CDROM_SIMPLE_OPC_INFO structure. It defines the Optimum Power Calibration (OPC) request that is used as input to the IOCTL_CDROM_SEND_OPC_INFORMATION I/O control request. |
| [_CDROM_PERFORMANCE_EXCEPTION_TYPE enumeration](ne-ntddcdrm-_cdrom_performance_exception_type.md) | The CDROM_PERFORMANCE_EXCEPTION_TYPE enumeration defines the exceptional conditions for performance data. |
| [_CDROM_PERFORMANCE_REQUEST_TYPE enumeration](ne-ntddcdrm-_cdrom_performance_request_type.md) | The CDROM_PERFORMANCE_REQUEST_TYPE enumeration defines the types of performance data requests. It is a member of the CDROM_PERFORMANCE_REQUEST structure, which is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE I/O control request. |
| [_CDROM_PERFORMANCE_TOLERANCE_TYPE enumeration](ne-ntddcdrm-_cdrom_performance_tolerance_type.md) | The CDROM_PERFORMANCE_TOLERANCE_TYPE enumeration defines the allowable tolerances for performance data. It is a member of the CDROM_PERFORMANCE_REQUEST structure, which is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE I/O control request. |
| [_CDROM_PERFORMANCE_TYPE enumeration](ne-ntddcdrm-_cdrom_performance_type.md) | The CDROM_PERFORMANCE_TYPE enumeration defines the read and write performance data requests. It is a member of the CDROM_PERFORMANCE_REQUEST structure, which is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE I/O control request. |
| [_CDROM_SPEED_REQUEST enumeration](ne-ntddcdrm-_cdrom_speed_request.md) | The CDROM_SPEED_REQUEST enumeration indicates which command that the CD-ROM class driver will use to set the spindle speed of a CD-ROM drive. |
| [_EXCLUSIVE_ACCESS_REQUEST_TYPE enumeration](ne-ntddcdrm-_exclusive_access_request_type.md) | The EXCLUSIVE_ACCESS_REQUEST_TYPE enumeration is used to report the exclusive access state of a CD-ROM device. |
| [_STREAMING_CONTROL_REQUEST_TYPE enumeration](ne-ntddcdrm-_streaming_control_request_type.md) | The STREAMING_CONTROL_REQUEST_TYPE enumeration defines the CDROM streaming modes. |
| [_TRACK_MODE_TYPE enumeration](ne-ntddcdrm-_track_mode_type.md) | The TRACK_MODE_TYPE enumeration type is used in conjunction with the IOCTL_CDROM_RAW_READ request and the RAW_READ_INFO structure to read data from a CD-ROM in raw mode. |
| [_WRITE_ROTATION enumeration](ne-ntddcdrm-_write_rotation.md) | The WRITE_ROTATION enumeration specifies whether a CD-ROM drive uses constant linear velocity (CLV) rotation or constant angular velocity (CAV) rotation when it writes to a CD. |
