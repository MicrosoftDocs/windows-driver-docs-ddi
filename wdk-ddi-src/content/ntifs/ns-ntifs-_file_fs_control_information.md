---
UID: NS:ntifs._FILE_FS_CONTROL_INFORMATION
title: FILE_FS_CONTROL_INFORMATION (ntifs.h)
description: Learn more about the FILE_FS_CONTROL_INFORMATION structure.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FILE_FS_CONTROL_INFORMATION structure"]
ms.keywords: "*PFILE_FS_CONTROL_INFORMATION, FILE_FS_CONTROL_INFORMATION, FILE_FS_CONTROL_INFORMATION structure [Installable File System Drivers], PFILE_FS_CONTROL_INFORMATION, PFILE_FS_CONTROL_INFORMATION structure pointer [Installable File System Drivers], _FILE_FS_CONTROL_INFORMATION, fileinformationstructures_387e4fd0-c3a2-4472-b29d-79f8a5d876f8.xml, ifsk.file_fs_control_information, ntifs/FILE_FS_CONTROL_INFORMATION, ntifs/PFILE_FS_CONTROL_INFORMATION"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
req.typenames: FILE_FS_CONTROL_INFORMATION, *PFILE_FS_CONTROL_INFORMATION
f1_keywords:
 - _FILE_FS_CONTROL_INFORMATION
 - ntifs/_FILE_FS_CONTROL_INFORMATION
 - PFILE_FS_CONTROL_INFORMATION
 - ntifs/PFILE_FS_CONTROL_INFORMATION
 - FILE_FS_CONTROL_INFORMATION
 - ntifs/FILE_FS_CONTROL_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_FS_CONTROL_INFORMATION
 - PFILE_FS_CONTROL_INFORMATION
 - FILE_FS_CONTROL_INFORMATION
---

# FILE_FS_CONTROL_INFORMATION structure

## -description

The **FILE_FS_CONTROL_INFORMATION** structure is used to query or set control information for the files in a directory.

## -struct-fields

### -field FreeSpaceStartFiltering

Minimum amount of free disk space, in bytes, that is required for the Content-Indexing daemon to begin document filtering.

### -field FreeSpaceThreshold

Minimum amount of free disk space, in bytes, required for the Indexing Service to continue to filter documents and merge word lists. If the amount of free disk space falls below this threshold, a warning message is written to the Microsoft Windows application event log. Filtering and merging are halted until space is freed.

### -field FreeSpaceStopFiltering

Minimum amount of free disk space, in bytes, that is required for the Content-Indexing daemon to continue document filtering. If the amount of free disk space falls below this threshold, document filtering is halted.

### -field DefaultQuotaThreshold

Default per-user disk quota warning threshold for the volume.

### -field DefaultQuotaLimit

Default per-user disk quota limit for the volume.

### -field FileSystemControlFlags

Bitmask of flags that control quota enforcement and logging of user-related quota events on the volume. Logging makes an entry in the Windows application event log. Compatible combination of one or more of the following:

| File System Control Flag | Meaning |
| ------------------------ | ------- |
| FILE_VC_CONTENT_INDEX_DISABLED | If set, content indexing is disabled. |
| FILE_VC_LOG_QUOTA_LIMIT | If set, an event log entry will be created when the user exceeds his or her assigned disk quota limit. |
| FILE_VC_LOG_QUOTA_THRESHOLD | If set, an event log entry will be created when the user exceeds his or her assigned quota warning threshold. |
| FILE_VC_LOG_VOLUME_LIMIT | If set, an event log entry will be created when the volume's free space limit is exceeded. |
| FILE_VC_LOG_VOLUME_THRESHOLD | If set, an event log entry will be created when the volume's free space threshold is exceeded. |
| FILE_VC_QUOTA_ENFORCE | If set, quotas are enforced on the volume. |
| FILE_VC_QUOTA_TRACK | If set, quotas are tracked on the volume. |
| FILE_VC_QUOTAS_INCOMPLETE | If set, the quota information for the volume is incomplete. |
| FILE_VC_QUOTAS_REBUILDING | If set, the file system is rebuilding the quota information for the volume. |

In addition, the following flag masks are defined. These are useful for testing flag values.

| Mask | Value |
| ---- | ----- |
|FILE_VC_QUOTA_MASK | FILE_VC_QUOTA_ENFORCE \| FILE_VC_QUOTA_TRACK |
| FILE_VC_QUOTA_NONE | ~FILE_VC_QUOTA_ENFORCE & ~FILE_VC_QUOTA_TRACK |
| FILE_VC_VALID_MASK | ORed combination of all flags in the above table. |

## -remarks

This information can be queried in either of the following ways:

* Call [**FltQueryVolumeInformation**](../fltkernel/nf-fltkernel-fltqueryvolumeinformation.md) or [**ZwQueryVolumeInformationFile**](nf-ntifs-zwqueryvolumeinformationfile.md), passing FileFsControlInformation as the value of **FileInformationClass** and passing a caller-allocated, FILE_FS_CONTROL_INFORMATION-structured buffer as the value of **FileInformation**.

* Create an IRP with major function code IRP_MJ_QUERY_VOLUME_INFORMATION.

FILE_READ_DATA access to the volume is required to query this information.

This information can be set in either of the following ways:

* Call [**FltSetVolumeInformation**](../fltkernel/nf-fltkernel-fltsetvolumeinformation.md) or [**ZwSetVolumeInformationFile**](nf-ntifs-zwsetvolumeinformationfile.md), passing FileFsControlInformation as the value of **FileInformationClass** and passing a caller-allocated, FILE_FS_CONTROL_INFORMATION-structured buffer as the value of **FileInformation**.
* Create an IRP with major function code IRP_MJ_SET_VOLUME_INFORMATION.

FILE_WRITE_DATA access to the volume is required to set this information.

The size of the buffer passed in the **FileInformation** parameter to [**FltQueryVolumeInformation**](../fltkernel/nf-fltkernel-fltqueryvolumeinformation.md), [**FltSetVolumeInformation**](../fltkernel/nf-fltkernel-fltsetvolumeinformation.md), [**ZwQueryVolumeInformationFile**](nf-ntifs-zwqueryvolumeinformationfile.md), or **ZwSetVolumeInformationFile** must be at least **sizeof** (FILE_FS_CONTROL_INFORMATION).

This structure must be aligned on a LONGLONG (8-byte) boundary.

## -see-also

[**FltQueryVolumeInformation**](../fltkernel/nf-fltkernel-fltqueryvolumeinformation.md)

[**FltSetVolumeInformation**](../fltkernel/nf-fltkernel-fltsetvolumeinformation.md)

[**IRP_MJ_QUERY_VOLUME_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-query-volume-information)

[**IRP_MJ_SET_VOLUME_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-set-volume-information)

[**ZwQueryVolumeInformationFile**](nf-ntifs-zwqueryvolumeinformationfile.md)

[**ZwSetVolumeInformationFile**](nf-ntifs-zwsetvolumeinformationfile.md)
