---
UID: NA:ntdddisk
ms.assetid: 2395b2bc-8867-39af-9b0d-1b0147c01cac
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntdddisk.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Ntdddisk.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_CREATE_DISK structure](ns-ntdddisk-_create_disk.md) | The CREATE_DISK structure is used with the IOCTL_DISK_CREATE_DISK IOCTL to initialize a disk with an empty partition table. The partition table styles are master boot record (MBR) or GUID partition table (GPT). |
| [_CREATE_DISK_GPT structure](ns-ntdddisk-_create_disk_gpt.md) | The CREATE_DISK_GPT structure is used with the IOCTL IOCTL_DISK_CREATE_DISK to initialize a disk with an empty GPT partition table. |
| [_CREATE_DISK_MBR structure](ns-ntdddisk-_create_disk_mbr.md) | The CREATE_DISK_MBR structure is used with the IOCTL IOCTL_DISK_CREATE_DISK to initialize a disk with an empty MBR partition table. |
| [_DISK_CACHE_INFORMATION structure](ns-ntdddisk-_disk_cache_information.md) | The DISK_CACHE_INFORMATION structure is used with the IOCTL_DISK_GET_CACHE_INFORMATION request to retrieve cache information. |
| [_DISK_CONTROLLER_NUMBER structure](ns-ntdddisk-_disk_controller_number.md) | DISK_CONTROLLER_NUMBER is used with IOCTL_DISK_CONTROLLER_NUMBER to retrieve the controller number and disk number of an IDE disk. |
| [_DISK_COPY_DATA_PARAMETERS structure](ns-ntdddisk-_disk_copy_data_parameters.md) | DISK_COPY_DATA_PARAMETERS is used with IOCTL_DISK_COPY_DATA to copy data from one area of the disk to another. |
| [_DISK_DETECTION_INFO structure](ns-ntdddisk-_disk_detection_info.md) | The DISK_DETECTION_INFO structure contains the detected drive parameters that are supplied by an x86 PC BIOS on boot. |
| [_DISK_EX_INT13_INFO structure](ns-ntdddisk-_disk_ex_int13_info.md) | The DISK_EX_INT13_INFO structure is used by the BIOS to report disk detection data for a partition with an extended INT13 format. |
| [_DISK_GEOMETRY structure](ns-ntdddisk-_disk_geometry.md) | The DISK_GEOMETRY structure is obsolete and provided only to support existing drivers. |
| [_DISK_GEOMETRY_EX structure](ns-ntdddisk-_disk_geometry_ex.md) | The DISK_GEOMETRY_EX structure is a variable-length structure composed of a DISK_GEOMETRY structure followed by a DISK_PARTITION_INFO structure followed, in turn, by a DISK_DETECTION_INFO structure. |
| [_DISK_GROW_PARTITION structure](ns-ntdddisk-_disk_grow_partition.md) | The DISK_GROW_PARTITION structure is used in conjunction with the IOCTL_DISK_GROW_PARTITION request to enlarge a partition. |
| [_DISK_INT13_INFO structure](ns-ntdddisk-_disk_int13_info.md) | The DISK_INT13_INFO structure is used by the BIOS to report disk detection data for a partition with an INT13 format. |
| [_DISK_PARTITION_INFO structure](ns-ntdddisk-_disk_partition_info.md) | The DISK_PARTITION_INFO structure is used to report information about the disk's partition table. |
| [_DISK_PERFORMANCE structure](ns-ntdddisk-_disk_performance.md) | The DISK_PERFORMANCE structure is used in conjunction with the IOCTL_DISK_PERFORMANCE request to collect summary disk statistics for purposes of measuring disk performance. |
| [_DRIVERSTATUS structure](ns-ntdddisk-_driverstatus.md) | The DRIVERSTATUS structure is used in conjunction with the SENDCMDOUTPARAMS structure and the SMART_SEND_DRIVE_COMMAND request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command. |
| [_DRIVE_LAYOUT_INFORMATION structure](ns-ntdddisk-_drive_layout_information.md) | The DRIVE_LAYOUT_INFORMATION structure is obsolete and is provided only to support existing drivers. |
| [_DRIVE_LAYOUT_INFORMATION_EX structure](ns-ntdddisk-_drive_layout_information_ex.md) | The DRIVE_LAYOUT_INFORMATION_EX structure is used to report information about the driver layout. |
| [_DRIVE_LAYOUT_INFORMATION_GPT structure](ns-ntdddisk-_drive_layout_information_gpt.md) | The DRIVE_LAYOUT_INFORMATION_GPT structure reports the drive signature for a GUID Partition Table partition. |
| [_DRIVE_LAYOUT_INFORMATION_MBR structure](ns-ntdddisk-_drive_layout_information_mbr.md) | The DRIVE_LAYOUT_INFORMATION_MBR structure reports the drive signature for a Master Boot Record partition. |
| [_FORMAT_EX_PARAMETERS structure](ns-ntdddisk-_format_ex_parameters.md) | The FORMAT_EX_PARAMETERS structure is used in conjunction with the IOCTL_DISK_FORMAT_TRACKS_EX request to format the specified set of contiguous tracks on the disk. |
| [_FORMAT_PARAMETERS structure](ns-ntdddisk-_format_parameters.md) | The FORMAT_PARAMETERS structure is used in conjunction with the IOCTL_DISK_FORMAT_TRACKS request to format the specified set of contiguous tracks on the disk. |
| [_GETVERSIONINPARAMS structure](ns-ntdddisk-_getversioninparams.md) | The GETVERSIONINPARAMS structure is used in conjunction with the SMART_GET_VERSION request to retrieve version information, a capabilities mask, and a bitmask for the indicated device. |
| [_GET_LENGTH_INFORMATION structure](ns-ntdddisk-_get_length_information.md) | The GET_LENGTH_INFORMATION structure is used with the IOCTL_DISK_GET_LENGTH_INFO to obtain the length, in bytes, of a disk, partition, or volume. |
| [_IDEREGS structure](ns-ntdddisk-_ideregs.md) | The IDEREGS structure is used to report the contents of the IDE controller registers. |
| [_PARTITION_INFORMATION structure](ns-ntdddisk-_partition_information.md) | The PARTITION_INFORMATION structure contains partition information for a partition with a traditional AT-style Master Boot Record (MBR). |
| [_PARTITION_INFORMATION_EX structure](ns-ntdddisk-_partition_information_ex.md) | PARTITION_INFORMATION_EX is the extended version of the PARTITION_INFORMATION structure. It holds information both for partitions with a Master Boot Record and for partitions with a GUID Partition Table. |
| [_PARTITION_INFORMATION_GPT structure](ns-ntdddisk-_partition_information_gpt.md) | PARTITION_INFORMATION_GPT contains information for a GUID Partition Table partition that is not held in common with a Master Boot Record partition. |
| [_PARTITION_INFORMATION_MBR structure](ns-ntdddisk-_partition_information_mbr.md) | PARTITION_INFORMATION_MBR contains information for a Master Boot Record partition that is not held in common with a GUID Partition Table partition. |
| [_REASSIGN_BLOCKS structure](ns-ntdddisk-_reassign_blocks.md) | The REASSIGN_BLOCKS structure is used in conjunction with the IOCTL_DISK_REASSIGN_BLOCKS request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks. |
| [_REASSIGN_BLOCKS_EX structure](ns-ntdddisk-_reassign_blocks_ex.md) | The REASSIGN_BLOCKS_EX structure is used in conjunction with the IOCTL_DISK_REASSIGN_BLOCKS_EX request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks. |
| [_SENDCMDINPARAMS structure](ns-ntdddisk-_sendcmdinparams.md) | The SENDCMDINPARAMS structure contains the input parameters for the SMART_SEND_DRIVE_COMMAND request. |
| [_SENDCMDOUTPARAMS structure](ns-ntdddisk-_sendcmdoutparams.md) | The SENDCMDOUTPARAMS structure is used in conjunction with the SMART_SEND_DRIVE_COMMAND request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command. |
| [_SET_PARTITION_INFORMATION structure](ns-ntdddisk-_set_partition_information.md) | SET_PARTITION_INFORMATION is used with IOCTL_DISK_SET_PARTITION_INFO to change the partition type of a specified Master Boot Record (MBR) disk partition. |
| [_SET_PARTITION_INFORMATION_EX structure](ns-ntdddisk-_set_partition_information_ex.md) | SET_PARTITION_INFORMATION_EX is used with the IOCTL IOCTL_DISK_SET_PARTITION_INFO_EX to set information for a specific partition. |
| [_VERIFY_INFORMATION structure](ns-ntdddisk-_verify_information.md) | The VERIFY_INFORMATION structure provides information used to verify the existence of a disk extent. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_DISK_CHECK_VERIFY IOCTL](ni-ntdddisk-ioctl_disk_check_verify.md) | In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by IOCTL_STORAGE_CHECK_VERIFY. The only difference between the two IOCTLs is the base value. |
| [IOCTL_DISK_CONTROLLER_NUMBER IOCTL](ni-ntdddisk-ioctl_disk_controller_number.md) | Retrieves the controller number and disk number for an IDE disk. |
| [IOCTL_DISK_COPY_DATA IOCTL](ni-ntdddisk-ioctl_disk_copy_data.md) | This IOCTL_DISK_COPY_DATA IOCTL is used to copy data from one area of the disk to another. |
| [IOCTL_DISK_CREATE_DISK IOCTL](ni-ntdddisk-ioctl_disk_create_disk.md) | Creates an empty partition for the device object. |
| [IOCTL_DISK_DELETE_DRIVE_LAYOUT IOCTL](ni-ntdddisk-ioctl_disk_delete_drive_layout.md) | Removes partition information from the disk. |
| [IOCTL_DISK_FIND_NEW_DEVICES IOCTL](ni-ntdddisk-ioctl_disk_find_new_devices.md) | In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by IOCTL_STORAGE_FIND_NEW_DEVICES. The only difference between the two IOCTLs is the base value. |
| [IOCTL_DISK_FORMAT_TRACKS IOCTL](ni-ntdddisk-ioctl_disk_format_tracks.md) | Formats the specified set of contiguous tracks on the disk. |
| [IOCTL_DISK_FORMAT_TRACKS_EX IOCTL](ni-ntdddisk-ioctl_disk_format_tracks_ex.md) | Is similar to IOCTL_DISK_FORMAT_TRACKS, except that it allows the caller to specify several more parameters. |
| [IOCTL_DISK_GET_CACHE_INFORMATION IOCTL](ni-ntdddisk-ioctl_disk_get_cache_information.md) | Returns disk cache configuration data. |
| [IOCTL_DISK_GET_DRIVE_GEOMETRY IOCTL](ni-ntdddisk-ioctl_disk_get_drive_geometry.md) | Returns information about the physical disk's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector). |
| [IOCTL_DISK_GET_DRIVE_GEOMETRY_EX IOCTL](ni-ntdddisk-ioctl_disk_get_drive_geometry_ex.md) | Returns information about the physical disk's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).The difference between IOCTL_DISK_GET_DRIVE_GEOMETRY_EX and the older IOCTL_DISK_GET_DRIVE_GEOMETRY request is that IOCTL_DISK_GET_DRIVE_GEOMETRY_EX can retrieve information from both Master Boot Record (MBR) and GUID Partition Table (GPT)-type partitioned media, whereas IOCTL_DISK_GET_DRIVE_GEOMETRY can only read MBR-style media. |
| [IOCTL_DISK_GET_DRIVE_LAYOUT IOCTL](ni-ntdddisk-ioctl_disk_get_drive_layout.md) | Returns information about the number of partitions, disk signature, and features of each partition on a disk. (Floppy drivers need not handle this request.). |
| [IOCTL_DISK_GET_DRIVE_LAYOUT_EX IOCTL](ni-ntdddisk-ioctl_disk_get_drive_layout_ex.md) | Returns information about the number of partitions, disk signature, and features of each partition on a disk. (Floppy drivers need not handle this request.). |
| [IOCTL_DISK_GET_LENGTH_INFO IOCTL](ni-ntdddisk-ioctl_disk_get_length_info.md) | Returns the length, in bytes, of the disk, partition, or volume associated with the device object that is the target of the request. |
| [IOCTL_DISK_GET_MEDIA_TYPES IOCTL](ni-ntdddisk-ioctl_disk_get_media_types.md) | In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by IOCTL_STORAGE_GET_MEDIA_TYPES. The only difference between the two IOCTLs is the base value. |
| [IOCTL_DISK_GET_PARTITION_INFO IOCTL](ni-ntdddisk-ioctl_disk_get_partition_info.md) | Returns information about the type, size, and nature of a disk partition. (Floppy drivers need not handle this request.). |
| [IOCTL_DISK_GET_PARTITION_INFO_EX IOCTL](ni-ntdddisk-ioctl_disk_get_partition_info_ex.md) | Returns information about the type, size, and nature of a disk partition. (Floppy drivers need not handle this request.). |
| [IOCTL_DISK_GROW_PARTITION IOCTL](ni-ntdddisk-ioctl_disk_grow_partition.md) | Increases the size of an existing partition. |
| [IOCTL_DISK_INTERNAL_CLEAR_VERIFY IOCTL](ni-ntdddisk-ioctl_disk_internal_clear_verify.md) | Allows a driver to clear the verify bit on a disk device object, if the mode of the caller is kernel mode. |
| [IOCTL_DISK_INTERNAL_SET_VERIFY IOCTL](ni-ntdddisk-ioctl_disk_internal_set_verify.md) | Allows a driver to set the verify bit on a disk device object if the mode of the caller is kernel mode. |
| [IOCTL_DISK_IS_CLUSTERED IOCTL](ni-ntdddisk-ioctl_disk_is_clustered.md) | Allows a driver or application to determine if a disk is clustered. |
| [IOCTL_DISK_IS_WRITABLE IOCTL](ni-ntdddisk-ioctl_disk_is_writable.md) | Determines whether a disk is writable. |
| [IOCTL_DISK_PERFORMANCE IOCTL](ni-ntdddisk-ioctl_disk_performance.md) | Increments a reference counter that enables the collection of disk performance statistics, such as the numbers of bytes read and written since the driver last processed this request, for a corresponding disk monitoring application. |
| [IOCTL_DISK_PERFORMANCE_OFF IOCTL](ni-ntdddisk-ioctl_disk_performance_off.md) | Disables the counters that were enabled by previous calls to IOCTL_DISK_PERFORMANCE. This request is available in Windows XP and later operating systems. Caller must be running at IRQL = PASSIVE_LEVEL. |
| [IOCTL_DISK_REASSIGN_BLOCKS IOCTL](ni-ntdddisk-ioctl_disk_reassign_blocks.md) | Maps defective blocks to new location on disk. This request instructs the device to reassign the bad block address to a good block from its spare-block pool. |
| [IOCTL_DISK_REASSIGN_BLOCKS_EX IOCTL](ni-ntdddisk-ioctl_disk_reassign_blocks_ex.md) | Maps defective blocks to a new location on disk. This request instructs the device to reassign the bad block address to a good block from its spare-block pool. |
| [IOCTL_DISK_RESET_SNAPSHOT_INFO IOCTL](ni-ntdddisk-ioctl_disk_reset_snapshot_info.md) | Clears all volume shadow copy service (VSS) hardware-based snapshot information from the disk. |
| [IOCTL_DISK_SET_CACHE_INFORMATION IOCTL](ni-ntdddisk-ioctl_disk_set_cache_information.md) | Sets disk cache configuration data. |
| [IOCTL_DISK_SET_DRIVE_LAYOUT IOCTL](ni-ntdddisk-ioctl_disk_set_drive_layout.md) | Repartitions a disk as specified. (Floppy drivers need not handle this request.). |
| [IOCTL_DISK_SET_DRIVE_LAYOUT_EX IOCTL](ni-ntdddisk-ioctl_disk_set_drive_layout_ex.md) | Repartitions a disk as specified. (Floppy drivers need not handle this request.). |
| [IOCTL_DISK_SET_PARTITION_INFO IOCTL](ni-ntdddisk-ioctl_disk_set_partition_info.md) | Changes the partition type of the specified disk partition. (Floppy drivers need not handle this request.). |
| [IOCTL_DISK_SET_PARTITION_INFO_EX IOCTL](ni-ntdddisk-ioctl_disk_set_partition_info_ex.md) | Changes the partition type of the specified disk partition. (Floppy drivers need not handle this request.). |
| [IOCTL_DISK_UPDATE_DRIVE_SIZE IOCTL](ni-ntdddisk-ioctl_disk_update_drive_size.md) | Updates device extension with drive size information for current media. |
| [IOCTL_DISK_VERIFY IOCTL](ni-ntdddisk-ioctl_disk_verify.md) | Performs verification for a specified extent on a disk. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [DISK_CACHE_RETENTION_PRIORITY enumeration](ne-ntdddisk-disk_cache_retention_priority.md) | The DISK_CACHE_RETENTION_PRIORITY enumeration is used in conjunction with the IOCTL_DISK_GET_CACHE_INFORMATION request and the structure DISK_CACHE_INFORMATION to indicate which kinds data are to be held in the cache on a preferential basis. |
| [_DETECTION_TYPE enumeration](ne-ntdddisk-_detection_type.md) | The DETECTION_TYPE enumeration type is used in conjunction with the IOCTL_DISK_GET_DRIVE_GEOMETRY_EX request and the DISK_GEOMETRY_EX structure to determine the type of formatting used by the BIOS to record the disk geometry. |
