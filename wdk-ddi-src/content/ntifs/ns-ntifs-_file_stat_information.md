---
UID: NS:ntifs._FILE_STAT_INFORMATION
title: _FILE_STAT_INFORMATION (ntifs.h)
description: Contains metadata about a file.
ms.assetid: b2ab854f-2c03-4ee3-ab6b-4480d6a379a3
ms.date: 10/19/2018
tech.root: ifsk
keywords: ["_FILE_STAT_INFORMATION structure"]
f1_keywords:
 - "ntifs/_FILE_STAT_INFORMATION"
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ntifs.h
api_name: 
- _FILE_STAT_INFORMATION
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: RS5
---

# _FILE_STAT_INFORMATION structure

## -description
Contains metadata about a file.

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
 

## -remarks

## -see-also
