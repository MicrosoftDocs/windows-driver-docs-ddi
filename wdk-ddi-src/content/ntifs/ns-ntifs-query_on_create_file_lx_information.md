---
UID: NS:ntifs._QUERY_ON_CREATE_FILE_LX_INFORMATION
tech.root: ifsk
title: QUERY_ON_CREATE_FILE_LX_INFORMATION
ms.date: 03/11/2021
targetos: Windows
description: The QUERY_ON_CREATE_FILE_LX_INFORMATION structure is used to write a file's Linux metadata extended attributes when FltRequestFileInfoOnCreateCompletion is called with the QoCFileLxInformation flag set in the InfoClassFlags parameter.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.target-type: 
req.typenames: QUERY_ON_CREATE_FILE_LX_INFORMATION, *PQUERY_ON_CREATE_FILE_LX_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _QUERY_ON_CREATE_FILE_LX_INFORMATION
 - PQUERY_ON_CREATE_FILE_LX_INFORMATION
 - QUERY_ON_CREATE_FILE_LX_INFORMATION
f1_keywords:
 - _QUERY_ON_CREATE_FILE_LX_INFORMATION
 - ntifs/_QUERY_ON_CREATE_FILE_LX_INFORMATION
 - PQUERY_ON_CREATE_FILE_LX_INFORMATION
 - ntifs/PQUERY_ON_CREATE_FILE_LX_INFORMATION
 - QUERY_ON_CREATE_FILE_LX_INFORMATION
 - ntifs/QUERY_ON_CREATE_FILE_LX_INFORMATION
dev_langs:
 - c++
---

## -description

The **QUERY_ON_CREATE_FILE_LX_INFORMATION** structure is used to write a file's Linux metadata extended attributes when [**FltRequestFileInfoOnCreateCompletion**](../fltkernel/nf-fltkernel-fltrequestfileinfooncreatecompletion.md) is called with the **QoCFileLxInformation** flag set in the **InfoClassFlags** parameter.

## -struct-fields

### -field EffectiveAccess

The access rights of the file.

### -field LxFlags

The flags associated with FILE_STAT_LX_INFORMATION that specify which metadata fields are present in the file. Can be a bit mask of the following values:

| Flag | Value |
| ---- | ----- |
| LX_FILE_METADATA_HAS_UID (0x1) | The file has a user ID. |
| LX_FILE_METADATA_HAS_GID (0x2) | The file has a group ID. |
| LX_FILE_METADATA_HAS_MODE (0x4) | The file has mode information. |
| LX_FILE_METADATA_HAS_DEVICE_ID (0x8) | The file has a device ID. |
| LX_FILE_CASE_SENSITIVE_DIR (0x10) | The directory has case sensitivity information. |

### -field LxUid

The user ID of the file.

### -field LxGid

The group ID of the file.

### -field LxMode

The Linux file type and file system permissions. These values are defined in sys/stat.h in the Windows SDK. See [**FILE_STAT_LX_INFORMATION**](ns-ntifs-_file_stat_lx_information.md) for more information.

### -field LxDeviceIdMajor

For device files (_S_IFCHR or S_IFBLK), specifies the device major number. For other file types, this field is not used.

### -field LxDeviceIdMinor

For device files (_S_IFCHR or S_IFBLK), specifies the device minor number. For other file types, this field is not used.

## -remarks

The file system allocates this structure and fills in the requested information, if supported, while it processes a file create. Filter Manager will free the allocated structure.

## -see-also

[**FILE_STAT_LX_INFORMATION**](ns-ntifs-_file_stat_lx_information.md)

[**FltRequestFileInfoOnCreateCompletion**](../fltkernel/nf-fltkernel-fltrequestfileinfooncreatecompletion.md)

[**FltRetrieveFileInfoOnCreateCompletionEx**](../fltkernel/nf-fltkernel-fltretrievefileinfooncreatecompletionex.md)
