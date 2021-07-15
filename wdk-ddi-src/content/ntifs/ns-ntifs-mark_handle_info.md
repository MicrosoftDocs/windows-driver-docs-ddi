---
UID: NS:ntifs._MARK_HANDLE_INFO
tech.root: ifsk
title: MARK_HANDLE_INFO
ms.date: 07/14/2021
targetos: Windows
description: A MARK_HANDLE_INFO structure is passed as the input buffer during a FSCTL_MARK_HANDLE control code request.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.typenames: MARK_HANDLE_INFO, *PMARK_HANDLE_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _MARK_HANDLE_INFO
 - PMARK_HANDLE_INFO
 - MARK_HANDLE_INFO
f1_keywords:
 - _MARK_HANDLE_INFO
 - ntifs/_MARK_HANDLE_INFO
 - PMARK_HANDLE_INFO
 - ntifs/PMARK_HANDLE_INFO
 - MARK_HANDLE_INFO
 - ntifs/MARK_HANDLE_INFO
dev_langs:
 - c++
---

## -description

A **MARK_HANDLE_INFO** structure is passed as the input buffer during a [**FSCTL_MARK_HANDLE**](ni-ntifs-fsctl_mark_handle.md) control code request.

## -struct-fields

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.UsnSourceInfo

See **UsnSourceInfo** below.

### -field DUMMYUNIONNAME.CopyNumber

Identifies which copy of a file to read, when reading from a file that resides on redundant media.

### -field UsnSourceInfo

The optional update sequence number (USN) source info flags. To set any of these values, a volume DASD handle must be specified in the **VolumeHandle** field. Can be a combination of the following values:

| Flag | Meaning |
| ---- | ------- |
| **USN_SOURCE_DATA_MANAGEMENT** | Service is not modifying the external view of any part of the file. Typical case is HSM moving data to and from external storage. |
| **USN_SOURCE_AUXILIARY_DATA**  | Service is not modifying the external view of the file with regard to the application that created this file. Can be used to add private data streams to a file. |
| **USN_SOURCE_REPLICATION_MANAGEMENT** | Service is modifying a file to match the contents of the same file which exists in another member of the replica set. |
| **USN_SOURCE_CLIENT_REPLICATION_MANAGEMENT** | Replication is being performed on client systems either from the cloud or servers.  A volume handle is not required to set this value

### -field VolumeHandle

Volume handle for this operation.

### -field HandleInfo

Contains flags to identify the request. This field can be one of the following values:

| Flag | Meaning |
| ---- | ------- |
| **MARK_HANDLE_PROTECT_CLUSTERS**   | Do not allow any defragmenting (FSCTL_MOVE_FILE) until the handle is closed. |
| **MARK_HANDLE_TXF_SYSTEM_LOG**     | This stream is being used as the Txf log for a resource manager on the volume. Must be called in the kernel using IRP_MN_KERNEL_CALL. Available starting in Windows Vista. |
| **MARK_HANDLE_NOT_TXF_SYSTEM_LOG** | This component is no longer using this object as a TxF log file. Available starting in Windows Vista. |
| **MARK_HANDLE_REALTIME**           | Only supported by the UDFS file system. Marks the device to do realtime streaming of video. Available starting in Windows 7. |
| **MARK_HANDLE_NOT_REALTIME**       | Only supported by the UDFS file system. Marks the device to no longer do realtime streaming of video. Available starting in Windows 7. |
| **MARK_HANDLE_CLOUD_SYNC**         | Deprecated; do not use this flag. |
| **MARK_HANDLE_READ_COPY**          | The data must be read from the specified copy of data. Only supported for Storage Spaces redundant volumes. Available starting in Windows 8. |
| **MARK_HANDLE_NOT_READ_COPY**      | The data is no longer to be read from a specific copy. Only supported for Storage Spaces redundant volumes. Available starting in Windows 8. |
| **MARK_HANDLE_FILTER_METADATA**    | Reserved for internal Microsoft use only. |
| **MARK_HANDLE_RETURN_PURGE_FAILURE** | When intermixing memory mapped/cached IO with non-cached IO, and a non-cached IO is issued, the system attempts to purge memory mappings for the range of the non-cached IO. If these purges fail the system normally does not return the failure to the caller which can lead to corrupted state. This flag tells the system to return purge failures for the given handle so the application can better handle this situation. Available starting in Windows 8.1. |
| **MARK_HANDLE_DISABLE_FILE_METADATA_OPTIMIZATION** | Disables the File Replication Service (FRS) compaction feature on the given file. Available starting in Windows 10 version 1507. |
| **MARK_HANDLE_ENABLE_USN_SOURCE_ON_PAGING_IO** | Tells NTFS to set the given UsnSourceInfo value on Paging writes in the USN Journal.  Traditionally this was not done on paging writes since you did not know what thread made the given changes. This is an override. This only works if the FileObject that the Memory Manager is holding on to has this state associated with it. Available starting in Windows 10 version 1507. |
| **MARK_HANDLE_SKIP_COHERENCY_SYNC_DISALLOW_WRITES** | Tells the system that writes are not allowed on this file. If someone tries to open the file for write access, the operation is failed with STATUS_ACCESS_DENIED. If a write is seen the operation is failed with STATUS_MARKED_TO_DISALLOW_WRITES. Available starting in Windows 10 version 1507. |
| **MARK_HANDLE_ENABLE_CPU_CACHE** | Reserved for internal Microsoft use only. |
| **MARK_HANDLE_SUPPRESS_VOLUME_OPEN_FLUSH** | Normally, on the first read/write operation on a volume handle (DASD open), the file system flushes the volume. This can have performance consequences in certain scenarios.  If this flag is set on a volume handle it will suppress that flush on first IO. Available starting in Windows 11. |

## -remarks

**MARK_HANDLE_INFO** contains the information used to mark a specified file or directory, and its update sequence number (USN) change journal record with data about changes.

## -see-also

[**FSCTL_MARK_HANDLE**](ni-ntifs-fsctl_mark_handle.md)
