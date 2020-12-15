---
UID: NS:ntifs._FILE_STAT_INFORMATION
title: FILE_STAT_INFORMATION (ntifs.h)
description: The FILE_STAT_INFORMATION structure contains metadata about a file.
ms.date: 11/20/2020
tech.root: ifsk
keywords: ["FILE_STAT_INFORMATION structure"]
ms.keywords: _FILE_STAT_INFORMATION, FILE_STAT_INFORMATION, *PFILE_STAT_INFORMATION,
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: FILE_STAT_INFORMATION, *PFILE_STAT_INFORMATION
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _FILE_STAT_INFORMATION
 - ntifs/_FILE_STAT_INFORMATION
 - PFILE_STAT_INFORMATION
 - ntifs/PFILE_STAT_INFORMATION
 - FILE_STAT_INFORMATION
 - ntifs/FILE_STAT_INFORMATION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_STAT_INFORMATION
dev_langs:
 - c++
---

# FILE_STAT_INFORMATION structure

## -description

**FILE_STAT_INFORMATION** contains metadata about a file.

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

## -remarks

[**NtQueryInformationByName**](nf-ntifs-ntqueryinformationbyname.md) and [**NtQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md) return information in a **FILE_STAT_INFORMATION** structure when their **FileInformationClass** parameter is FileStatInformation.

## -see-also

[**NtQueryInformationByName**](nf-ntifs-ntqueryinformationbyname.md)

[**NtQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md)
