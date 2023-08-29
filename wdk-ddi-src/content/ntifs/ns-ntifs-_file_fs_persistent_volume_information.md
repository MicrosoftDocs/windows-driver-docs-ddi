---
UID: NS:ntifs._FILE_FS_PERSISTENT_VOLUME_INFORMATION
title: FILE_FS_PERSISTENT_VOLUME_INFORMATION (ntifs.h)
description: Learn more about the FILE_FS_PERSISTENT_VOLUME_INFORMATION structure.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["FILE_FS_PERSISTENT_VOLUME_INFORMATION structure"]
ms.keywords: "*PFILE_FS_PERSISTENT_VOLUME_INFORMATION, FILE_FS_PERSISTENT_VOLUME_INFORMATION, FILE_FS_PERSISTENT_VOLUME_INFORMATION structure [Installable File System Drivers], PERSISTENT_VOLUME_STATE_BACKED_BY_WIM, PERSISTENT_VOLUME_STATE_CONTAINS_BACKING_WIM, PERSISTENT_VOLUME_STATE_GLOBAL_METADATA_NO_SEEK_PENALTY, PERSISTENT_VOLUME_STATE_LOCAL_METADATA_NO_SEEK_PENALTY, PERSISTENT_VOLUME_STATE_NO_HEAT_GATHERING, PERSISTENT_VOLUME_STATE_SHORT_NAME_CREATION_DISABLED, PERSISTENT_VOLUME_STATE_VOLUME_SCRUB_DISABLED, PFILE_FS_PERSISTENT_VOLUME_INFORMATION, PFILE_FS_PERSISTENT_VOLUME_INFORMATION structure pointer [Installable File System Drivers], _FILE_FS_PERSISTENT_VOLUME_INFORMATION, fileinformationstructures_81dcbc8f-6b7e-455e-b1b2-b99e6fd4084d.xml, ifsk.file_fs_persistent_volume_information, ntifs/FILE_FS_PERSISTENT_VOLUME_INFORMATION, ntifs/PFILE_FS_PERSISTENT_VOLUME_INFORMATION"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
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
req.typenames: FILE_FS_PERSISTENT_VOLUME_INFORMATION, *PFILE_FS_PERSISTENT_VOLUME_INFORMATION
f1_keywords:
 - _FILE_FS_PERSISTENT_VOLUME_INFORMATION
 - ntifs/_FILE_FS_PERSISTENT_VOLUME_INFORMATION
 - PFILE_FS_PERSISTENT_VOLUME_INFORMATION
 - ntifs/PFILE_FS_PERSISTENT_VOLUME_INFORMATION
 - FILE_FS_PERSISTENT_VOLUME_INFORMATION
 - ntifs/FILE_FS_PERSISTENT_VOLUME_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_FS_PERSISTENT_VOLUME_INFORMATION
 - PFILE_FS_PERSISTENT_VOLUME_INFORMATION
 - FILE_FS_PERSISTENT_VOLUME_INFORMATION
---

# FILE_FS_PERSISTENT_VOLUME_INFORMATION structure

## -description

The **FILE_FS_PERSISTENT_VOLUME_INFORMATION** structure is used to control persistent settings for a file system volume. Persistent settings persist on a file system volume between reboots of the computer.

## -struct-fields

### -field VolumeFlags

The persistent state settings for a file system volume. This value is a bitwise OR combination of the following.

| Value | Meaning |
| ----- | ------- |
| PERSISTENT_VOLUME_STATE_SHORT_NAME_CREATION_DISABLED 0x00000001    | A 0 for this bit indicates that the creation of 8.3 short names is enabled, and a 1 indicates that short name creation is disabled. 8.3 short file names have at most eight characters, followed by a period "." and a file name extension of at most three characters. |
| PERSISTENT_VOLUME_STATE_VOLUME_SCRUB_DISABLED 0x00000002           | When set, this flag indicates that the volume scrub is disabled for the volume. Valid starting with Windows 8. |
| PERSISTENT_VOLUME_STATE_GLOBAL_METADATA_NO_SEEK_PENALTY 0x00000004 | Global no seek penalty is enabled for a tiered volume. Valid starting with Windows 8.1. |
| PERSISTENT_VOLUME_STATE_LOCAL_METADATA_NO_SEEK_PENALTY 0x00000008  | Local no seek penalty is enabled for a tiered volume. Valid starting with Windows 8.1. |
| PERSISTENT_VOLUME_STATE_NO_HEAT_GATHERING 0x00000010               | When set, heat gathering is not enabled for the tiered volume. Valid starting with Windows 8.1. |
| PERSISTENT_VOLUME_STATE_CONTAINS_BACKING_WIM 0x00000020            | Indicates that this volume is backing the system volume with files  from a Windows Image Format (WIM) file. Valid starting with Windows 8.1 Update. |
| PERSISTENT_VOLUME_STATE_BACKED_BY_WIM 0x00000040                   | Indicates that this volume is dependent on another volume to provide system critical boot files. The other  volume contains a WIM file that backs the files on this volume. This flag is read only. Valid starting with Windows 8.1 Update. |
| PERSISTENT_VOLUME_STATE_DEV_VOLUME 0x00002000                      | Indicates that this volume is formatted as a developer volume.  This can be used by the file system and other system components to enable optimizations that does not require an administrator to trust the volume on a given machine. Valid starting with Windows 11, version 22H2 September Update. |
| PERSISTENT_VOLUME_STATE_TRUSTED_VOLUME 0x00004000                  | Indicates that an adminstrator on a given machine had trust this volume and is willing to enable optimizations like not having anti-virus filters attach to the volume. This information is persisted in the registry on a given machine. This can be used by the file system and other system components to enable optimizations that require an administrator to trust the volume on a given machine. Valid starting with Windows 11, version 22H2 September Update.|

### -field FlagMask

A mask value for the valid flags that can appear in **VolumeFlags**. This is a bitwise OR combination of the desired flags described for **VolumeFlags**.

### -field Version

The version number of this structure. Set to 1.

### -field Reserved

Reserved. Set to 0;

## -remarks

The **FILE_FS_PERSISTENT_VOLUME_INFORMATION** structure is used with the [FSCTL_SET_PERSISTENT_VOLUME_STATE](/windows-hardware/drivers/ifs/fsctl-set-persistent-volume-state) and [FSCTL_QUERY_PERSISTENT_VOLUME_STATE](/windows-hardware/drivers/ifs/fsctl-query-persistent-volume-state) control codes.

To query the state flags, **FlagMask** is set to a combination of flags to check for. For example, if the only the seek penalty flags are of interest, **FlagMask** = PERSISTENT_VOLUME_STATE_GLOBAL_METADATA_NO_SEEK_PENALTY | PERSISTENT_VOLUME_STATE_LOCAL_METADATA_NO_SEEK_PENALTY. Also, if only short name support is queried, then set **FlagMask** = PERSISTENT_VOLUME_STATE_SHORT_NAME_CREATION_DISABLED.

When setting or clearing the persistent volume state flags, using [FSCTL_SET_PERSISTENT_VOLUME_STATE](/windows-hardware/drivers/ifs/fsctl-set-persistent-volume-state), **FlagMask** is set to all of the flags in **VolumeFlags** that will be affected for the volume. **VolumeFlags** contains the actual persistent state flags to set for the volume. The following example shows how to set the members of **FILE_FS_PERSISTENT_VOLUME_INFORMATION** to enable short name creation for a volume.

```cpp
IO_STATUS_BLOCK IoStatus;
FILE_FS_PERSISTENT_VOLUME_INFORMATION PersistVolInfo;
NTSTATUS status;

PersistVolInfo.VolumeFlags = 0;    // enable shortname creation on this volume
PersistVolInfo.FlagMask    = PERSISTENT_VOLUME_STATE_SHORT_NAME_CREATION_DISABLED;
PersistVolInfo.Version     = 1;
PersistVolInfo.Reserved    = 0;

// issue the request to the file system to set the enable state
//
status = ZwFsControlFile( VolumeHandle,
                          NULL,
                          NULL,
                          NULL,
                          &IoStatus,
                          FSCTL_SET_PERSISTENT_VOLUME_STATE,
                          &PersistVolInfo,
                          sizeof(FILE_FS_PERSISTENT_VOLUME_INFORMATION),
                          NULL,
                          0 );
```

The **Version** member must be set to the current version of 1 for both a query and  a set  request.

## -see-also

[FSCTL_QUERY_PERSISTENT_VOLUME_STATE](/windows-hardware/drivers/ifs/fsctl-query-persistent-volume-state)

[FSCTL_SET_PERSISTENT_VOLUME_STATE](/windows-hardware/drivers/ifs/fsctl-set-persistent-volume-state)
