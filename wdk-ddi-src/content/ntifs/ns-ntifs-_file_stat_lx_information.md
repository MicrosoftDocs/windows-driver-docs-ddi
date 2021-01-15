---
UID: NS:ntifs._FILE_STAT_LX_INFORMATION
title: FILE_STAT_LX_INFORMATION (ntifs.h)
description: The FILE_STAT_LX_INFORMATION structure contains metadata about a file.
ms.date: 11/20/2020
tech.root: ifsk
keywords: ["FILE_STAT_LX_INFORMATION structure"]
ms.keywords: _FILE_STAT_LX_INFORMATION, FILE_STAT_LX_INFORMATION, *PFILE_STAT_LX_INFORMATION,
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: FILE_STAT_LX_INFORMATION, *PFILE_STAT_LX_INFORMATION
targetos: Windows
f1_keywords:
 - _FILE_STAT_LX_INFORMATION
 - ntifs/_FILE_STAT_LX_INFORMATION
 - PFILE_STAT_LX_INFORMATION
 - ntifs/PFILE_STAT_LX_INFORMATION
 - FILE_STAT_LX_INFORMATION
 - ntifs/FILE_STAT_LX_INFORMATION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_STAT_LX_INFORMATION
 - PFILE_STAT_LX_INFORMATION
 - FILE_STAT_LX_INFORMATION
---

# FILE_STAT_LX_INFORMATION structure


## -description

**FILE_STAT_LX_INFORMATION** contains Linux metadata extended attributes present on the file. This is used and created by the Windows Subsystem for Linux (WSL).

## -struct-fields

### -field FileId

Specifies the id of a file.

### -field CreationTime

Specifies the creation time of a file.

### -field LastAccessTime

Specifies the last time a file was accessed.

### -field LastWriteTime

Specifies the last time a file was written to.

### -field ChangeTime

Specifies the last time a file was changed.

### -field AllocationSize

File allocation size, in bytes. Usually this value is a multiple of the sector or cluster size of the underlying physical device.

### -field EndOfFile

Absolute new end-of-file position as a byte offset from the start of the file. **EndOfFile** specifies the byte offset to the end of the file. Because this value is zero-based, it actually refers to the first free byte in the file. In other words, **EndOfFile** is the offset to the byte immediately following the last valid byte in the file.

### -field FileAttributes

File attributes, which can be any valid combination of the following:

Attribute   |   Value
------------|------------
FILE_ATTRIBUTE_READONLY |0x00000001
FILE_ATTRIBUTE_HIDDEN   |0x00000002
FILE_ATTRIBUTE_SYSTEM   |0x00000004
FILE_ATTRIBUTE_DIRECTORY|0x00000010
FILE_ATTRIBUTE_ARCHIVE  |0x00000020
FILE_ATTRIBUTE_NORMAL   |0x00000080

### -field ReparseTag

Reparse point tag. See [About reparse points](/windows-hardware/drivers/ifs/reparse-points) for more information.

### -field NumberOfLinks

Specifies the number of links to the file.

### -field EffectiveAccess

Specifies the access rights of the file.

### -field LxFlags

The flags associated with **FILE_STAT_LX_INFORMATION** that specify which metadata fields were present in the file.

Flag|Value
----|-----
LX_FILE_METADATA_HAS_UID|x1
LX_FILE_METADATA_HAS_GID|x2
LX_FILE_METADATA_HAS_MODE|x4
LX_FILE_METADATA_HAS_DEVICE_ID|x8
LX_FILE_CASE_SENSITIVE_DIR|x10

### -field LxUid

Specifies the User id of the file.

### -field LxGid

Specifies the Group id of the file.

### -field LxMode

Specifies the Linux file type and file system permissions. These values are defined in sys/stat.h in the Windows SDK.

- S_IFLNK
- S_IFSOCK
- S_IFBLK

| Flag | Description|
|---|---|
|_S_IFMT   0xF000 |File type mask|
|_S_IFDIR  0x4000 | Directory|
|_S_IFCHR  0x2000 | Character special|
|_S_IFIFO  0x1000 | Pipe|
|_S_IFREG  0x8000 | Regular|
|_S_IREAD  0x0100 | Read permission, owner|
|_S_IWRITE 0x0080 | Write permission, owner|
|_S_IEXEC  0x0040 | Execute/search permission, owner|

### -field LxDeviceIdMajor

For device files (_S_IFCHR or S_IFBLK), specifies the device major number. For other file types, this field is not used.

### -field LxDeviceIdMinor

For device files (_S_IFCHR or S_IFBLK), specifies the device minor number. For other file types, this field is not used.

## -remarks

[**NtQueryInformationByName**](nf-ntifs-ntqueryinformationbyname.md) and [**NtQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md) return information in a **FILE_STAT_LX_INFORMATION** structure when their **FileInformationClass** parameter is FileStatLxInformation.

For more information about absolute and relative symbolic links, see Creating Symbolic Links in the Microsoft Windows SDK documentation.

## -see-also

[**NtQueryInformationByName**](nf-ntifs-ntqueryinformationbyname.md)

[**NtQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md)

