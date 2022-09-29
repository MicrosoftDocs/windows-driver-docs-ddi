---
UID: NF:ntifs.NtSetQuotaInformationFile
title: NtSetQuotaInformationFile function (ntifs.h)
description: The NtSetQuotaInformationFile routine changes quota entries for the volume associated with the FileHandle parameter.
old-location: kernel\zwsetquotainformationfile.htm
tech.root: kernel
ms.date: 07/26/2022
keywords: ["NtSetQuotaInformationFile function"]
ms.keywords: NtSetQuotaInformationFile, ZwSetQuotaInformationFile, ZwSetQuotaInformationFile routine [Kernel-Mode Driver Architecture], k111_87b6e79e-ecd9-47ff-8f0c-7502fc82b8af.xml, kernel.zwsetquotainformationfile, ntifs/NtSetQuotaInformationFile, ntifs/ZwSetQuotaInformationFile
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
 - NtSetQuotaInformationFile
 - ntifs/NtSetQuotaInformationFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtSetQuotaInformationFile
---

# NtSetQuotaInformationFile function

## -description

The **NtSetQuotaInformationFile** routine changes quota entries for the volume associated with the **FileHandle** parameter. All of the quota entries in the specified buffer are applied to the volume.

## -parameters

### -param FileHandle [in]

A handle for the file object that represents the file or volume for which the quota information is to be modified.

### -param IoStatusBlock [out]

The address of the caller's I/O status block.

### -param Buffer [in]

A buffer containing the new quota entries that should be applied to the volume. The quota information must be formatted as one or more [**FILE_QUOTA_INFORMATION**](ns-ntifs-_file_quota_information.md) structures. The **NextEntryOffset** field in the **FILE_QUOTA_INFORMATION** structure contains the offset, in bytes, of the next quota entry in the list. If there are no more entries after the current one, this member is zero.

### -param Length [in]

The length in bytes of the buffer.

## -returns

The **NtSetQuotaInformationFile** routine returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INSUFFICIENT_RESOURCES | There were insufficient resources to complete the operation. This is an error code. |
| STATUS_INVALID_DEVICE_REQUEST | Quotas are not enabled on the volume. This is an error code. |
| STATUS_MEDIA_WRITE_PROTECTED  | The volume is read only. This is an error code. |

## -remarks

The **NtSetQuotaInformationFile** routine applies all of the quota entries in the specified **Buffer** parameter to the volume.

The **IoCheckQuotaBufferValidity** function can check whether the specified quota buffer passed as the **Buffer** parameter is valid.

A call to **NtSetQuotaInformationFile** will result in an [**IRP_MJ_SET_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-set-quota) request being sent to the device object that is associated with the file object whose handle is stored in the **FileHandle** parameter.

If the underlying file system does not support quota information (FAT and CDFS file systems, for example), **NtSetQuotaInformationFile** will fail returning STATUS_INVALID_DEVICE_REQUEST.

> [!NOTE]
> If the call to the **NtSetQuotaInformationFile** function occurs in kernel mode, you should use the name "[**ZwSetQuotaInformationFile**](nf-ntifs-zwsetquotainformationfile.md" instead of "**NtSetQuotaInformationFile**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**FILE_GET_QUOTA_INFORMATION**](ns-ntifs-_file_get_quota_information.md)

[**FILE_QUOTA_INFORMATION**](ns-ntifs-_file_quota_information.md)

[**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md)

[**IRP_MJ_QUERY_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-query-quota)

[**IRP_MJ_SET_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-set-quota)

[**IoCheckQuotaBufferValidity**](nf-ntifs-iocheckquotabuffervalidity.md)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[**NtQueryQuotaInformationFile**](nf-ntifs-ntqueryquotainformationfile.md)
