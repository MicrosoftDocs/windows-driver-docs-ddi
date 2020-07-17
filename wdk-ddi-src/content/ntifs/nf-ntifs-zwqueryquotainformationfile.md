---
UID: NF:ntifs.ZwQueryQuotaInformationFile
title: ZwQueryQuotaInformationFile function (ntifs.h)
description: The ZwQueryQuotaInformationFile routine retrieves quota entries associated with the volume specified by the FileHandle parameter.
old-location: kernel\zwqueryquotainformationfile.htm
tech.root: kernel
ms.assetid: 572477c7-8588-415e-b66f-adab977ab373
ms.date: 04/30/2018
keywords: ["ZwQueryQuotaInformationFile function"]
ms.keywords: NtQueryQuotaInformationFile, ZwQueryQuotaInformationFile, ZwQueryQuotaInformationFile routine [Kernel-Mode Driver Architecture], k111_226a807c-d14d-403f-bbef-f5b4e6491039.xml, kernel.zwqueryquotainformationfile, ntifs/NtQueryQuotaInformationFile, ntifs/ZwQueryQuotaInformationFile
f1_keywords:
 - "ntifs/ZwQueryQuotaInformationFile"
 - "ZwQueryQuotaInformationFile"
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
- ZwQueryQuotaInformationFile
- NtQueryQuotaInformationFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwQueryQuotaInformationFile function


## -description


The <b>ZwQueryQuotaInformationFile</b> routine retrieves quota entries associated with the volume specified by the <i>FileHandle</i> parameter. 


## -parameters




### -param FileHandle [in]

A handle for the file object that represents the file or volume for which the quota information is requested.


### -param IoStatusBlock [out]

The address of the caller's I/O status block.


### -param Buffer [out]

A buffer to receive the quota information for the volume. The quota information is formatted as one or more <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_quota_information">FILE_QUOTA_INFORMATION</a> structures. The <b>NextEntryOffset</b> field in the <b>FILE_QUOTA_INFORMATION</b> structure contains the offset, in bytes, of the next quota entry in the list. If there are no more entries after the current one, this member is zero.


### -param Length [in]

The length in bytes of the buffer.


### -param ReturnSingleEntry [in]

A Boolean value that indicates if only a single entry should be returned rather than filling the buffer with as many entries as possible.


### -param SidList [in, optional]

An optional list of SIDs whose quota information is to be returned. Each entry in the list is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_get_quota_information">FILE_GET_QUOTA_INFORMATION</a> structure. The <b>NextEntryOffset</b> field in the <b>FILE_GET_QUOTA_INFORMATION</b> structure contains the offset, in bytes, of the next quota entry in the list. If there are no more entries after the current one, this member is zero.


### -param SidListLength [in]

The length in bytes of the <b>SID</b> list, if one was specified.


### -param StartSid [in, optional]

An optional pointer to the <b>SID</b> of the entry at which to begin scanning the quota information. This parameter should be set if the returned information is to start with an entry other than the first SID. This parameter is ignored if a <i>SidList</i> parameter is specified. 


### -param RestartScan [in]

A Boolean value that indicates whether the scan of the quota information is to be restarted from the beginning. Set this parameter to <b>TRUE</b> if the scan of the quota information is to start at the first entry in the volume's quota information list. Set to <b>FALSE</b> if resuming the scan from a previous call to <b>ZwQueryQuotaInformationFile</b>. The caller must set this parameter to <b>TRUE</b> when calling <b>ZwQueryQuotaInformationFile</b> for the first time.


## -returns



The <b>ZwQueryQuotaInformationFile</b> routine returns STATUS_SUCCESS if at least one <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_quota_information">FILE_QUOTA_INFORMATION</a> structure is returned in the <i>Buffer</i> parameter or an appropriate NTSTATUS value such as one of the following:

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
<dt><b>STATUS_INVALID_SID</b></dt>
</dl>
</td>
<td width="60%">
The<i> StartSid</i> parameter did not contain a valid <b>SID</b>. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_QUOTA_LIST_INCONSISTENT</b></dt>
</dl>
</td>
<td width="60%">
The<i> SidList</i> parameter did not contain a valid, properly formed list. This is an error code.

</td>
</tr>
</table>
 




## -remarks



The amount of information returned by <b>ZwQueryQuotaInformationFile</b> is based on the size of the quota information associated with the volume, the size of the buffer, and whether a specific set of entries has been requested.

A call to <b>ZwQueryQuotaInformationFile</b> will result in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-quota">IRP_MJ_QUERY_QUOTA</a> request being sent to the device object that is associated with the file object whose handle is stored in the <i>FileHandle</i> parameter.

If the underlying file system does not support quota information (FAT and CDFS file systems, for example), <b>ZwQueryQuotaInformationFile</b> will fail returning STATUS_INVALID_DEVICE_REQUEST.

<div class="alert"><b>Note</b>  If the call to the <b>ZwQueryQuotaInformationFile</b> function occurs in user mode, you should use the name "<b>NtQueryQuotaInformationFile</b>" instead of "<b>ZwQueryQuotaInformationFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_get_quota_information">FILE_GET_QUOTA_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_quota_information">FILE_QUOTA_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-quota">IRP_MJ_QUERY_QUOTA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-quota">IRP_MJ_SET_QUOTA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iocheckquotabuffervalidity">IoCheckQuotaBufferValidity</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567105">ZwSetQuotaInformationFile</a>
 

 

