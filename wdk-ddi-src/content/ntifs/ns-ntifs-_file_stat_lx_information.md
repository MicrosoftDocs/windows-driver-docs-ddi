---
UID: NS:ntifs._FILE_STAT_LX_INFORMATION
title: _FILE_STAT_LX_INFORMATION
author: windows-driver-content
description: The _FILE_STAT_LX_INFORMATION structure contains metadata about a file.
ms.assetid: dc897c81-2268-44bc-943e-1f494eba4a68
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _FILE_STAT_LX_INFORMATION, FILE_STAT_LX_INFORMATION, *PFILE_STAT_LX_INFORMATION, 
req.header: ntifs.h
req.include-header:
req.target-type:
req.target- min-winverclnt: Windows 10 (Version 1803)
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: FILE_STAT_LX_INFORMATION, *PFILE_STAT_LX_INFORMATION
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ntifs.h
api_name: 
-	_FILE_STAT_LX_INFORMATION
product:
-	Windows
targetos: Windows
---

# _FILE_STAT_LX_INFORMATION structure

## -description
The _FILE_STAT_LX_INFORMATION structure contains metadata about a file.

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
 
Reparse point tag. Must be a Microsoft reparse point tag. (See the following <b>Remarks</b> section.) 

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

Specifies the User id of the file
### -field LxGid
 

Specifies the Group id of the file

### -field LxMode
 
### -field LxDeviceIdMajor
 
### -field LxDeviceIdMinor
 

## -remarks

The REPARSE_DATA_BUFFER structure is used by Microsoft file systems, filters, and minifilter drivers, as well as the I/O manager, to store data for a reparse point. 

This structure can only be used for Microsoft reparse points. Third-party reparse point owners must use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552014">REPARSE_GUID_DATA_BUFFER</a> structure instead. 

Microsoft reparse points can use the REPARSE_DATA_BUFFER structure or the REPARSE_GUID_DATA_BUFFER structure. 

For more information about reparse point tags, see the Microsoft Windows SDK documentation. 

For more information about absolute and relative symbolic links, see Creating Symbolic Links in the Microsoft Windows SDK documentation.

## -see-also