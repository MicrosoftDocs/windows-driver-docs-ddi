---
UID: NF:ntifs.NtQueryQuotaInformationFile
title: NtQueryQuotaInformationFile function (ntifs.h)
description: The NtQueryQuotaInformationFile routine retrieves quota entries associated with the volume specified by the FileHandle parameter.
old-location: kernel\zwqueryquotainformationfile.htm
tech.root: kernel
ms.date: 07/26/2022
keywords: ["NtQueryQuotaInformationFile function"]
ms.keywords: NtQueryQuotaInformationFile, ZwQueryQuotaInformationFile, ZwQueryQuotaInformationFile routine [Kernel-Mode Driver Architecture], k111_226a807c-d14d-403f-bbef-f5b4e6491039.xml, kernel.zwqueryquotainformationfile, ntifs/NtQueryQuotaInformationFile, ntifs/ZwQueryQuotaInformationFile
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows 7
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NtQueryQuotaInformationFile
 - ntifs/NtQueryQuotaInformationFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtQueryQuotaInformationFile
---

# NtQueryQuotaInformationFile function

## -description

The **NtQueryQuotaInformationFile** routine retrieves quota entries associated with the volume specified by the **FileHandle** parameter.

## -parameters

### -param FileHandle [in]

A handle for the file object that represents the file or volume for which the quota information is requested.

### -param IoStatusBlock [out]

The address of the caller's I/O status block.

### -param Buffer [out]

A buffer to receive the quota information for the volume. The quota information is formatted as one or more [**FILE_QUOTA_INFORMATION**](ns-ntifs-_file_quota_information.md) structures. The **NextEntryOffset** field in the **FILE_QUOTA_INFORMATION** structure contains the offset, in bytes, of the next quota entry in the list. If there are no more entries after the current one, this member is zero.

### -param Length [in]

The length in bytes of the buffer.

### -param ReturnSingleEntry [in]

A Boolean value that indicates if only a single entry should be returned rather than filling the buffer with as many entries as possible.

### -param SidList [in, optional]

An optional list of SIDs whose quota information is to be returned. Each entry in the list is a [**FILE_GET_QUOTA_INFORMATION**](ns-ntifs-_file_get_quota_information.md) structure. The **NextEntryOffset** field in the **FILE_GET_QUOTA_INFORMATION** structure contains the offset, in bytes, of the next quota entry in the list. If there are no more entries after the current one, this member is zero.

### -param SidListLength [in]

The length in bytes of the **SID** list, if one was specified.

### -param StartSid [in, optional]

An optional pointer to the **SID** of the entry at which to begin scanning the quota information. This parameter should be set if the returned information is to start with an entry other than the first SID. This parameter is ignored if a **SidList** parameter is specified.

### -param RestartScan [in]

A Boolean value that indicates whether the scan of the quota information is to be restarted from the beginning. Set this parameter to **TRUE** if the scan of the quota information is to start at the first entry in the volume's quota information list. Set to **FALSE** if resuming the scan from a previous call to **NtQueryQuotaInformationFile**. The caller must set this parameter to **TRUE** when calling **NtQueryQuotaInformationFile** for the first time.

## -returns

The **NtQueryQuotaInformationFile** routine returns STATUS_SUCCESS if at least one [**FILE_QUOTA_INFORMATION**](ns-ntifs-_file_quota_information.md) structure is returned in the **Buffer** parameter or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INSUFFICIENT_RESOURCES  | There were insufficient resources to complete the operation. This is an error code. |
| STATUS_INVALID_DEVICE_REQUEST  | Quotas are not enabled on the volume. This is an error code. |
| STATUS_INVALID_SID             | The **StartSid** parameter did not contain a valid **SID**. This is an error code. |
| STATUS_QUOTA_LIST_INCONSISTENT | The **SidList** parameter did not contain a valid, properly formed list. This is an error code. |

## -remarks

The amount of information returned by **NtQueryQuotaInformationFile** is based on the size of the quota information associated with the volume, the size of the buffer, and whether a specific set of entries has been requested.

A call to **NtQueryQuotaInformationFile** will result in an [**IRP_MJ_SET_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-set-quota) request being sent to the device object that is associated with the file object whose handle is stored in the **FileHandle** parameter.

If the underlying file system does not support quota information (FAT and CDFS file systems, for example), **NtQueryQuotaInformationFile** will fail returning STATUS_INVALID_DEVICE_REQUEST.

> [!NOTE]
> If the call to the **NtQueryQuotaInformationFile** function occurs in kernel mode, you should use the name "[**ZwQueryQuotaInformationFile**](nf-ntifs-zwqueryquotainformationfile.md)" instead of "**NtQueryQuotaInformationFile**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**FILE_GET_QUOTA_INFORMATION**](ns-ntifs-_file_get_quota_information.md)

[**FILE_QUOTA_INFORMATION**](ns-ntifs-_file_quota_information.md)

[**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md)

[**IRP_MJ_QUERY_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-query-quota)

[**IRP_MJ_SET_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-set-quota)

[**IoCheckQuotaBufferValidity**](nf-ntifs-iocheckquotabuffervalidity.md)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[**NtSetQuotaInformationFile **](nf-ntifs-ntsetquotainformationfile.md)
