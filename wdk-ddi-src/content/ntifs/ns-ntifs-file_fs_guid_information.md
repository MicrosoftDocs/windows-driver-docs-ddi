---
UID: NS:ntifs._FILE_FS_GUID_INFORMATION
tech.root: ifsk
title: FILE_FS_GUID_INFORMATION
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FILE_FS_GUID_INFORMATION structure.
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
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: FILE_FS_GUID_INFORMATION, *PFILE_FS_GUID_INFORMATION
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
 - _FILE_FS_GUID_INFORMATION
 - PFILE_FS_GUID_INFORMATION
 - FILE_FS_GUID_INFORMATION
f1_keywords:
 - _FILE_FS_GUID_INFORMATION
 - ntifs/_FILE_FS_GUID_INFORMATION
 - PFILE_FS_GUID_INFORMATION
 - ntifs/PFILE_FS_GUID_INFORMATION
 - FILE_FS_GUID_INFORMATION
 - ntifs/FILE_FS_GUID_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _FILE_FS_GUID_INFORMATION
---

## -description

The **FILE_FS_GUID_INFORMATION** structure contains GUID infomation.

## -struct-fields

### -field FsGuid

GUID that uniquely identifies the file system. This identifier can be used to distinguish between different file systems, even if they are of the same type, across various volumes or storage devices.

## -remarks

## -see-also

[**FS_INFORMATION_CLASS**](../wdm/ne-wdm-_fsinfoclass.md)

[**NtQueryVolumeInformationFile**](nf-ntifs-ntqueryvolumeinformationfile.md)
