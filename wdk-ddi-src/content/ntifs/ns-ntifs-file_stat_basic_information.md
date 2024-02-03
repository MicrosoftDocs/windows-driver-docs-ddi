---
UID: NS:ntifs._FILE_STAT_BASIC_INFORMATION
tech.root: ifsk
title: FILE_STAT_BASIC_INFORMATION
ms.date: 02/02/2024
targetos: Windows
description: Learn more about FILE_STAT_BASIC_INFORMATION structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, build 26048
req.target-min-winversvr: 
req.target-type: 
req.typenames: FILE_STAT_BASIC_INFORMATION, *PFILE_STAT_BASIC_INFORMATION
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_STAT_BASIC_INFORMATION
 - PFILE_STAT_BASIC_INFORMATION
 - FILE_STAT_BASIC_INFORMATION
f1_keywords:
 - _FILE_STAT_BASIC_INFORMATION
 - ntifs/_FILE_STAT_BASIC_INFORMATION
 - PFILE_STAT_BASIC_INFORMATION
 - ntifs/PFILE_STAT_BASIC_INFORMATION
 - FILE_STAT_BASIC_INFORMATION
 - ntifs/FILE_STAT_BASIC_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _FILE_STAT_BASIC_INFORMATION
---

## -description

**FILE_STAT_BASIC_INFORMATION** contains basic metadata about a file.

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

### -field DeviceType

Set when a driver calls [**IoCreateDevice**](../wdm/nf-wdm-iocreatedevice.md) as appropriate for the type of underlying device. For more information, see [Specifying Device Types](/windows-hardware/drivers/kernel/specifying-device-types).

### -field DeviceCharacteristics

The device characteristics. For a description of relevant values, see [**DEVICE_OBJECT**](../wdm/ns-wdm-_device_object.md).

### -field Reserved

Reserved for system use.

### -field VolumeSerialNumber

Serial number of the volume where the file is located.

### -field FileId128

The 128-byte file reference number for the file. This number is generated and assigned to the file by the file system.

## -remarks

[**NtQueryInformationByName**](nf-ntifs-ntqueryinformationbyname.md) returns information in a **FILE_STAT_BASIC_INFORMATION** structure when the **FileInformationClass** parameter is FileStatBasicInformation.

## -see-also

[**NtQueryInformationByName**](nf-ntifs-ntqueryinformationbyname.md)
