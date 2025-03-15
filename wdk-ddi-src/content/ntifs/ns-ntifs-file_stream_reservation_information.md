---
UID: NS:ntifs._FILE_STREAM_RESERVATION_INFORMATION
tech.root: ifsk
title: FILE_STREAM_RESERVATION_INFORMATION
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FILE_STREAM_RESERVATION_INFORMATION structure.
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
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: FILE_STREAM_RESERVATION_INFORMATION, *PFILE_STREAM_RESERVATION_INFORMATION
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
 - _FILE_STREAM_RESERVATION_INFORMATION
 - PFILE_STREAM_RESERVATION_INFORMATION
 - FILE_STREAM_RESERVATION_INFORMATION
f1_keywords:
 - _FILE_STREAM_RESERVATION_INFORMATION
 - ntifs/_FILE_STREAM_RESERVATION_INFORMATION
 - PFILE_STREAM_RESERVATION_INFORMATION
 - ntifs/PFILE_STREAM_RESERVATION_INFORMATION
 - FILE_STREAM_RESERVATION_INFORMATION
 - ntifs/FILE_STREAM_RESERVATION_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _FILE_STREAM_RESERVATION_INFORMATION
---

## -description

The **FILE_STREAM_RESERVATION_INFORMATION** structure contains information about the reservation of space for a file stream.

## -struct-fields

### -field TrackedReservation

Amount of storage space that is currently tracked as reserved for the file stream.

### -field EnforcedReservation

Amount of storage space that is currently enforced as reserved for the file stream.

## -remarks

## -see-also

[**FILE_INFORMATION_CLASS**](../wdm/ne-wdm-_file_information_class.md)

[**NtQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md)
