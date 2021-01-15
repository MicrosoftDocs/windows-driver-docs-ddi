---
UID: NS:ntifs._FILE_ID_EXTD_BOTH_DIR_INFORMATION
title: _FILE_ID_EXTD_BOTH_DIR_INFORMATION (ntifs.h)
description: The FILE_ID_EXTD_BOTH_DIR_INFORMATION structure is used to query file reference number information for the files in a directory.
old-location: ifsk\file_id_extd_both_dir_information.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FILE_ID_EXTD_BOTH_DIR_INFORMATION structure"]
ms.keywords: "*PFILE_ID_EXTD_BOTH_DIR_INFORMATION, FILE_ID_EXTD_BOTH_DIR_INFORMATION, FILE_ID_EXTD_BOTH_DIR_INFORMATION structure [Installable File System Drivers], PFILE_ID_EXTD_BOTH_DIR_INFORMATION, PFILE_ID_EXTD_BOTH_DIR_INFORMATION structure pointer [Installable File System Drivers], _FILE_ID_EXTD_BOTH_DIR_INFORMATION, ifsk.file_id_extd_both_dir_information, ntifs/FILE_ID_EXTD_BOTH_DIR_INFORMATION, ntifs/PFILE_ID_EXTD_BOTH_DIR_INFORMATION"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1 Update.
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
req.typenames: FILE_ID_EXTD_BOTH_DIR_INFORMATION, *PFILE_ID_EXTD_BOTH_DIR_INFORMATION
f1_keywords:
 - _FILE_ID_EXTD_BOTH_DIR_INFORMATION
 - ntifs/_FILE_ID_EXTD_BOTH_DIR_INFORMATION
 - PFILE_ID_EXTD_BOTH_DIR_INFORMATION
 - ntifs/PFILE_ID_EXTD_BOTH_DIR_INFORMATION
 - FILE_ID_EXTD_BOTH_DIR_INFORMATION
 - ntifs/FILE_ID_EXTD_BOTH_DIR_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_ID_EXTD_BOTH_DIR_INFORMATION
 - PFILE_ID_EXTD_BOTH_DIR_INFORMATION
 - FILE_ID_EXTD_BOTH_DIR_INFORMATION
---

# FILE_ID_EXTD_BOTH_DIR_INFORMATION structure


## -description

The **FILE_ID_EXTD_BOTH_DIR_INFORMATION** structure is used to query file reference number information for the files in a directory.

## -struct-fields

### -field NextEntryOffset

Byte offset of the next **FILE_ID_EXTD_BOTH_DIR_INFORMATION** entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one.

### -field FileIndex

Byte offset of the file within the parent directory. This member is undefined for file systems, such as NTFS, in which the position of a file within the parent directory is not fixed and can be changed at any time to maintain sort order.

### -field CreationTime

Time when the file was created.

### -field LastAccessTime

Last time the file was accessed.

### -field LastWriteTime

Last time information was written to the file.

### -field ChangeTime

Last time the file was changed.

### -field EndOfFile

Absolute new end-of-file position as a byte offset from the start of the file. **EndOfFile** specifies the byte offset to the end of the file. Because this value is zero-based, it actually refers to the first free byte in the file. In other words, **EndOfFile** is the offset to the byte immediately following the last valid byte in the file.

### -field AllocationSize

File allocation size, in bytes. Usually, this value is a multiple of the sector or cluster size of the underlying physical device.

### -field FileAttributes

File attributes, which can be any valid combination of the following:

* FILE_ATTRIBUTE_READONLY
* FILE_ATTRIBUTE_HIDDEN
* FILE_ATTRIBUTE_SYSTEM
* FILE_ATTRIBUTE_DIRECTORY
* FILE_ATTRIBUTE_ARCHIVE
* FILE_ATTRIBUTE_NORMAL
* FILE_ATTRIBUTE_TEMPORARY
* FILE_ATTRIBUTE_COMPRESSED

### -field FileNameLength

Specifies the length of the file name string.

### -field EaSize

Combined length, in bytes, of the extended attributes (EA) for the file.

### -field ReparsePointTag

Tag value for the reparse point.

### -field FileId

The 128-byte file reference number for the file. This number is generated and assigned to the file by the file system.

### -field ShortNameLength

Specifies the length of the short file name string.

### -field ShortName

Unicode string containing the short (8.3) name for the file.

### -field FileName

Specifies the first character of the file name string. This is followed in memory by the remainder of the string.

## -remarks

This information can be queried in either of the following ways:

* Call [**ZwQueryDirectoryFile**](/previous-versions/ff567047(v=vs.85)), passing **FileIdExtdBothDirectoryInformation** as the value of **FileInformationClass** and passing a caller-allocated, FILE_ID_EXTD_BOTH_DIR_INFORMATION-structured buffer as the value of **FileInformation**.

* Create an IRP with major function code [IRP_MJ_DIRECTORY_CONTROL](/windows-hardware/drivers/ifs/irp-mj-directory-control) and minor function code IRP_MN_QUERY_DIRECTORY.

No specific access rights are required to query this information.

File reference numbers, also called file IDs, are guaranteed to be unique only within a static file system. They are not guaranteed to be unique over time, because file systems are free to reuse them. Nor are they guaranteed to remain constant. For example, the FAT file system generates the file reference number for a file from the byte offset of the file's directory entry record (DIRENT) on the disk. Defragmentation can change this byte offset. Thus a FAT file reference number can change over time.

All dates and times are in absolute system-time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601.

This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the **NextEntryOffset** value in each entry, except the last, falls on an 8-byte boundary.

## -see-also

[**FsRtlNotifyFullChangeDirectory**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullchangedirectory.md)

[IRP_MJ_DIRECTORY_CONTROL](/windows-hardware/drivers/ifs/irp-mj-directory-control)

[**ZwQueryDirectoryFile**](/previous-versions/ff567047(v=vs.85))

