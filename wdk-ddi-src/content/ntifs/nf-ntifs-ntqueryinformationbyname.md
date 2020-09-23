---
UID: NF:ntifs.NtQueryInformationByName
title: NtQueryInformationByName function
description: NtQueryInformationByName returns the requested information about a file specified by file name.
tech.root: ifsk
ms.assetid: 6b55d547-df99-412a-ba4f-febadc9e4296
ms.author: windowsdriverdev
ms.date: 10/30/2019
ms.topic: function
ms.keywords: NtQueryInformationByName
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Available starting with Windows 10 version 1703.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - NtQueryInformationByName
 - ntifs/NtQueryInformationByName
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtQueryInformationByName
product:
 - Windows
---

# NtQueryInformationByName function


## -description

**NtQueryInformationByName** returns the requested information about a file specified by file name.

## -parameters

### -param ObjectAttributes

Pointer to an [OBJECT_ATTRIBUTES](https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure that contains the file's attributes, including file name.

### -param IoStatusBlock

Pointer an [IO_STATUS_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block) structure containing the caller's I/O status.

### -param FileInformation

Pointer to the caller-supplied buffer in which to return the requested information about the file. The structure of the buffer is determined by the *FileInformationClass* parameter.

### -param Length

Length, in bytes, of the buffer that *FileInformation* points to.

### -param FileInformationClass

A [FILE_INFORMATION_CLASS](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_file_information_class) value that identifies the type of file information to return in the buffer that *FileInformation* points to. *FileInformationClass* can be one of the following values.

| FILE_INFORMATION_CLASS Value | Type of Information to Return |
| ---------------------------- | ----------------------------- |
| FileStatLxInformation        | [FILE_STAT_LX_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_stat_lx_information) |
| FileStatInformation          | [FILE_STAT_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_stat_information) |
| FileCaseSensitiveInformation | [FILE_CASE_SENSITIVE_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_case_sensitive_information) |

## -returns

**NtQueryInformationByName** returns STATUS_SUCCESS upon successful completion; otherwise it returns an error code, such as one of the following.

| Error Code | Meaning |
| ---------- | ------- |
| STATUS_INVALID_PARAMETER | The *FileInformationClass* parameter contains an invalid value. |
| STATUS_INFO_LENGTH_MISMATCH | The buffer size specified by *Length* is not large enough to contain the requested information. |

## -remarks

**NtQueryInformationByName** queries and returns the requested information about the file. It does so without opening the actual file, making it more efficient than [**NtQueryInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile), which requires a file open (and subsequent file close) .

Callers of **NtQueryInformationByName** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](https://docs.microsoft.com/windows-hardware/drivers/kernel/disabling-apcs).

## -see-also

[FILE_CASE_SENSITIVE_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_case_sensitive_information)

[FILE_INFORMATION_CLASS](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_file_information_class)

[FILE_STAT_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_stat_information)

[FILE_STAT_LX_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_stat_lx_information)

[IO_STATUS_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block)

[**NtQueryInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile)

[OBJECT_ATTRIBUTES](https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_object_attributes)

