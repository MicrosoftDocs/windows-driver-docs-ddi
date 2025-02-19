---
UID: NS:ntifs.READ_FILE_USN_DATA
tech.root: ifsk
title: READ_FILE_USN_DATA
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the READ_FILE_USN_DATA structure.
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
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.typenames: READ_FILE_USN_DATA, *PREAD_FILE_USN_DATA
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - READ_FILE_USN_DATA
 - PREAD_FILE_USN_DATA
f1_keywords:
 - READ_FILE_USN_DATA
 - ntifs/READ_FILE_USN_DATA
 - PREAD_FILE_USN_DATA
 - ntifs/PREAD_FILE_USN_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - READ_FILE_USN_DATA
---

## -description

The **READ_FILE_USN_DATA** structure specifies the versions of the update sequence number (USN) change journal supported by the caller. This structure is the input structure to the [**FSCTL_READ_FILE_USN_DATA**](ni-ntifs-fsctl_read_file_usn_data.md) control code.

## -struct-fields

### -field MinMajorVersion

The lowest version of the USN change journal accepted by the application. If the input buffer is not specified this defaults to 2.

### -field MaxMajorVersion

The highest version of the USN change journal accepted by the application. If the input buffer is not specified this defaults to 2. To support 128-bit file identifiers used by ReFS this must be 3 or higher.

## -see-also

[**FSCTL_READ_FILE_USN_DATA**](ni-ntifs-fsctl_read_file_usn_data.md)
