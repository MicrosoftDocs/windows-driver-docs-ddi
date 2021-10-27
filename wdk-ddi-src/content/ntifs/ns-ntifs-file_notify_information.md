---
UID: NS:ntifs._FILE_NOTIFY_INFORMATION
tech.root: ifsk
title: FILE_NOTIFY_INFORMATION
ms.date: 10/26/2021
targetos: Windows
description: Learn more about the FILE_NOTIFY_INFORMATION structure.
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
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.target-type: 
req.typenames: FILE_NOTIFY_INFORMATION, *PFILE_NOTIFY_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_NOTIFY_INFORMATION
 - PFILE_NOTIFY_INFORMATION
 - FILE_NOTIFY_INFORMATION
f1_keywords:
 - _FILE_NOTIFY_INFORMATION
 - ntifs/_FILE_NOTIFY_INFORMATION
 - PFILE_NOTIFY_INFORMATION
 - ntifs/PFILE_NOTIFY_INFORMATION
 - FILE_NOTIFY_INFORMATION
 - ntifs/FILE_NOTIFY_INFORMATION
dev_langs:
 - c++
---

## -description

**FILE_NOTIFY_INFORMATION** describes the changes to a directory.

## -struct-fields

### -field NextEntryOffset

The number of bytes that must be skipped to get to the next record. A value of zero indicates that this is the last record.

### -field Action

The type of change that has occurred. This member can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| FILE_ACTION_ADDED (0x00000001) | The file was added to the directory. |
| FILE_ACTION_REMOVED (0x00000002) | The file was removed from the directory. |
| FILE_ACTION_MODIFIED (0x00000003) | The file was modified. This can be a change in the time stamp or attributes. |
| FILE_ACTION_RENAMED_OLD_NAME (0x00000004) | The file was renamed and this is the old name. |
| FILE_ACTION_RENAMED_NEW_NAME (0x00000005) | The file was renamed and this is the new name. |
| FILE_ACTION_ADDED_STREAM (0x00000006) | A named stream was added to the file. |
| FILE_ACTION_REMOVED_STREAM (0x00000007) | A named stream was removed from the file. |
| FILE_ACTION_MODIFIED_STREAM (0x00000008) | A named stream was modified. The modification can be a change to the data or attributes of the named stream. |
| FILE_ACTION_REMOVED_BY_DELETE (0x00000009) | An object ID was removed because the file the object ID referred to was deleted. This notification is only sent when the directory being monitored is the special directory "\$Extend\$ObjId:$O:$INDEX_ALLOCATION". |
| FILE_ACTION_ID_NOT_TUNNELLED (0x0000000A) | An attempt to tunnel object ID information to a file being created or renamed failed because the object ID is in use by another file on the same volume. This notification is only sent when the directory being monitored is the special directory "\$Extend\$ObjId:$O:$INDEX_ALLOCATION". |
| FILE_ACTION_TUNNELLED_ID_COLLISION (0x0000000B) | An attempt to tunnel object ID information to a file being renamed failed because the file already has an object ID. This notification is only sent when the directory being monitored is the special directory "\$Extend\$ObjId:$O:$INDEX_ALLOCATION". |

### -field FileNameLength

The size of the file name portion of the record, in bytes. This value does not include the terminating null character.

### -field FileName

A variable-length field that contains the file name relative to the directory handle. The file name is in the Unicode character format and is not null-terminated.

If there is both a short and long name for the file, only one of these names will be returned, but it is unspecified which one.

## -remarks

A **FILE_NOTIFY_INFORMATION** structure is returned in response to an [**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control) request with an **IRP_MN_NOTIFY_CHANGE_DIRECTORY** minor function code.

## -see-also

[**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control)
