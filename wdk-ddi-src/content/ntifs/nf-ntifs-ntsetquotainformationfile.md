---
UID: NF:ntifs.NtSetQuotaInformationFile
title: NtSetQuotaInformationFile function (ntifs.h)
description: The ZwSetQuotaInformationFile routine changes quota entries for the volume associated with the FileHandle parameter. All of the quota entries in the specified buffer are applied to the volume.
old-location: kernel\zwsetquotainformationfile.htm
tech.root: kernel
ms.assetid: 40c7a74c-eace-4d01-8a55-2c3c8bace8fb
ms.date: 04/30/2018
ms.keywords: NtSetQuotaInformationFile, ZwSetQuotaInformationFile, ZwSetQuotaInformationFile routine [Kernel-Mode Driver Architecture], k111_87b6e79e-ecd9-47ff-8f0c-7502fc82b8af.xml, kernel.zwsetquotainformationfile, ntifs/NtSetQuotaInformationFile, ntifs/ZwSetQuotaInformationFile
ms.topic: function
f1_keywords:
 - "ntifs/ZwSetQuotaInformationFile"
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwSetQuotaInformationFile
- NtSetQuotaInformationFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtSetQuotaInformationFile function


## -description


The <b>NtSetQuotaInformationFile</b> routine changes quota entries for the volume associated with the <i>FileHandle</i> parameter. All of the quota entries in the specified buffer are applied to the volume. 


## -parameters




### -param FileHandle [in]

A handle for the file object that represents the file or volume for which the quota information is to be modified.


### -param IoStatusBlock [out]

The address of the caller's I/O status block.


### -param Buffer [in]

A buffer containing the new quota entries that should be applied to the volume. The quota information must be formatted as one or more <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_file_quota_information">FILE_QUOTA_INFORMATION</a> structures. The <b>NextEntryOffset</b> field in the <b>FILE_QUOTA_INFORMATION</b> structure contains the offset, in bytes, of the next quota entry in the list. If there are no more entries after the current one, this member is zero.


### -param Length [in]

The length in bytes of the buffer. 


## -returns



The <b>NtSetQuotaInformationFile</b> routine returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES </b></dt>
</dl>
</td>
<td width="60%">
There were insufficient resources to complete the operation. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Quotas are not enabled on the volume. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MEDIA_WRITE_PROTECTED</b></dt>
</dl>
</td>
<td width="60%">
The volume is read only. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



The <b>NtSetQuotaInformationFile</b> routine applies all of the quota entries in the specified <i>Buffer</i> parameter to the volume.

The <b>IoCheckQuotaBufferValidity</b> function can check whether the specified quota buffer passed as the <i>Buffer</i> parameter is valid.

A call to <b>NtSetQuotaInformationFile</b> will result in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-quota">IRP_MJ_SET_QUOTA</a> request being sent to the device object that is associated with the file object whose handle is stored in the <i>FileHandle</i> parameter.

If the underlying file system does not support quota information (FAT and CDFS file systems, for example), <b>NtSetQuotaInformationFile</b> will fail returning STATUS_INVALID_DEVICE_REQUEST.

<div class="alert"><b>Note</b>  If the call to the <b>NtSetQuotaInformationFile</b> function occurs in user mode, you should use the name "<a href="https://msdn.microsoft.com/library/windows/hardware/ff567105">NtSetQuotaInformationFile</a>" instead of "<b>ZwSetQuotaInformationFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_file_get_quota_information">FILE_GET_QUOTA_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_file_quota_information">FILE_QUOTA_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-quota">IRP_MJ_QUERY_QUOTA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-quota">IRP_MJ_SET_QUOTA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-iocheckquotabuffervalidity">IoCheckQuotaBufferValidity</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567064">NtQueryQuotaInformationFile</a>
 

 

