---
UID: NF:wdm.ZwQueryInformationByName
tech.root: kernel
title: ZwQueryInformationByName function (wdm.h)
ms.date: 06/21/2021
targetos: Windows
description: ZwQueryInformationByName returns the requested information about a file specified by file name.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - ZwQueryInformationByName
f1_keywords:
 - ZwQueryInformationByName
 - wdm/ZwQueryInformationByName
dev_langs:
 - c++
---

## -description

**ZwQueryInformationByName** returns the requested information about a file specified by file name.

## -parameters

### -param ObjectAttributes

[in] Pointer to an [OBJECT_ATTRIBUTES](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure that contains the file's attributes, including file name.

### -param IoStatusBlock

[out] Pointer an [IO_STATUS_BLOCK](../wdm/ns-wdm-_io_status_block.md) structure containing the caller's I/O status.

### -param FileInformation

[out] Pointer to the caller-supplied buffer in which to return the requested information about the file. The structure of the buffer is determined by the *FileInformationClass* parameter.

### -param Length

[in] Length, in bytes, of the buffer that *FileInformation* points to.

### -param FileInformationClass

[in] A [FILE_INFORMATION_CLASS](../wdm/ne-wdm-_file_information_class.md) value that identifies the type of file information to return in the buffer that *FileInformation* points to. *FileInformationClass* can be one of the following values.

| FILE_INFORMATION_CLASS Value | Type of Information to Return |
| ---------------------------- | ----------------------------- |
| **FileStatInformation**   (68)       | [FILE_STAT_INFORMATION](./ns-ntifs-_file_stat_information.md). Available starting with Windows 10, version 1709. |
| **FileStatLxInformation**  (70)   | [FILE_STAT_LX_INFORMATION](./ns-ntifs-_file_stat_lx_information.md). Available starting with Windows 10 April 2018 Update. |
| **FileCaseSensitiveInformation** (71) | [FILE_CASE_SENSITIVE_INFORMATION](./ns-ntifs-_file_case_sensitive_information.md). Available starting with Windows 10 April 2018 Update. |

## -returns

**ZwQueryInformationByName** returns STATUS_SUCCESS upon successful completion; otherwise it returns an error code, such as one of the following.

| Error Code | Meaning |
| ---------- | ------- |
| STATUS_INVALID_PARAMETER | The *FileInformationClass* parameter contains an invalid value. |
| STATUS_INFO_LENGTH_MISMATCH | The buffer size specified by *Length* is not large enough to contain the requested information. |

## -remarks

**ZwQueryInformationByName** queries and returns the requested information about the file. It does so without opening the actual file, making it more efficient than [**ZwQueryInformationFile**](nf-wdm-zwqueryinformationfile.md), which requires a file open (and subsequent file close).

Callers of **ZwQueryInformationByName** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](/windows-hardware/drivers/kernel/disabling-apcs).

## -see-also

[FILE_CASE_SENSITIVE_INFORMATION](./ns-ntifs-_file_case_sensitive_information.md)

[FILE_INFORMATION_CLASS](../wdm/ne-wdm-_file_information_class.md)

[FILE_STAT_INFORMATION](./ns-ntifs-_file_stat_information.md)

[FILE_STAT_LX_INFORMATION](./ns-ntifs-_file_stat_lx_information.md)

[IO_STATUS_BLOCK](../wdm/ns-wdm-_io_status_block.md)

[OBJECT_ATTRIBUTES](/windows/win32/api/ntdef/ns-ntdef-_object_attributes)

[**ZwQueryInformationFile**](nf-wdm-zwqueryinformationfile.md)
