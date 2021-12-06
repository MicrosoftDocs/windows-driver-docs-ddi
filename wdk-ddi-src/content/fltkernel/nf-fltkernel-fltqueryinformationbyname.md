---
UID: NF:fltkernel.FltQueryInformationByName
title: FltQueryInformationByName function (fltkernel.h)
description: The FltQueryInformationByName routine returns the requested information about a named file.
tech.root: ifsk
ms.date: 03/11/2021
keywords: ["FltQueryInformationByName function"]
ms.keywords: FltQueryInformationByName
req.header: fltkernel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1706
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - FltQueryInformationByName
 - fltkernel/FltQueryInformationByName
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltQueryInformationByName
dev_langs:
 - c++
---

# FltQueryInformationByName function

## -description

The **FltQueryInformationByName** routine returns the requested information about a named file.

## -parameters

### -param Filter [in]

Specifies the filter that is initiating this operation.

### -param Instance [in, optional]

Specifies the instance towards which the create is targeted.

> [!IMPORTANT]
> **Instance** is not necessarily the initiating instance. It must match the instance towards which the create is targeted, if this parameter is non-**NULL**. If **Instance** is non-**NULL**, the current filter's pre-create callback is not called. The pre-callbacks start with the filter below the current filter.

### -param ObjectAttributes [in]

Pointer to an [**OBJECT_ATTRIBUTES**] structure with the attributes to be used for the file object (for example, its name, SECURITY_DESCRIPTOR, etc.).

### -param IoStatusBlock [out]

Pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure containing the caller's I/O status block.

### -param FileInformation [out]

Pointer to a structure that receives the requested information returned about the file. The type of structure is determined by **FileInformationClass**.

### -param Length [in]

The length, in bytes, of the **FileInformation** buffer.

### -param FileInformationClass [in]

A [**FILE_INFORMATION_CLASS**](../wdm/ne-wdm-_file_information_class.md) enum value that specifies the type of information to return about the file. Can be one of the following values:

| Value | Type of structure that **FileInformation** points to |
| ----- | ---------------------------------------------------- |
| FileStatInformation | [**FILE_STAT_INFORMATION**](../ntifs/ns-ntifs-_file_stat_information.md) |
| FileStatLxInformation | [**FILE_STAT_LX_INFORMATION](../ntifs/ns-ntifs-_file_stat_lx_information.md) |
| FileCaseSensitiveInformation | [**FILE_CASE_SENSITIVE_INFORMATION**](..//ntifs/ns-ntifs-_file_case_sensitive_information.md). The caller must have opened the file with the FILE_READ_ATTRIBUTES flag specified in the DesiredAccess parameter. This value is available starting with Windows 10, version 1803. |
| FileCaseSensitiveInformationForceAccessCheck | [**FILE_CASE_SENSITIVE_INFORMATION**](..//ntifs/ns-ntifs-_file_case_sensitive_information.md). This is a special version of the FileCaseSensitiveInformation operation that is used to force the IO Manager to perform access checks for the kernel-mode driver, similar to the checks that apply to a user-mode caller. This operation is only recognized by the IO Manager and a file system should never receive it. This value is available starting with Windows 10, version 1803. |

### -param DriverContext [in, optional]

A pointer to the driver's context space.

## -returns

Returns STATUS_SUCCESS if the operation is successful. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks

This function returns requested information about a file without opening the actual file. The information returned is determined by the **FileInformationClass** that is specified, and it is placed into the caller's **FileInformation** buffer.

If **Instance** is non-**NULL** then the create will be targeted to the specified instance, calling all filters below the current filter before sending the I/O down. If **Instance** is **NULL**, the I/O will be always sent to the top of the filter stack.

## -see-also

[**FILE_INFORMATION_CLASS**](../wdm/ne-wdm-_file_information_class.md)
