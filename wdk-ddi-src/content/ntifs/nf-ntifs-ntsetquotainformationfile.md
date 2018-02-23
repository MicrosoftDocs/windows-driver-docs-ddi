---
UID: NF:ntifs.NtSetQuotaInformationFile
title: NtSetQuotaInformationFile function
author: windows-driver-content
description: The ZwSetQuotaInformationFile routine changes quota entries for the volume associated with the FileHandle parameter. All of the quota entries in the specified buffer are applied to the volume.
old-location: kernel\zwsetquotainformationfile.htm
old-project: kernel
ms.assetid: 40c7a74c-eace-4d01-8a55-2c3c8bace8fb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntifs/ZwSetQuotaInformationFile, ntifs/NtSetQuotaInformationFile, k111_87b6e79e-ecd9-47ff-8f0c-7502fc82b8af.xml, kernel.zwsetquotainformationfile, NtSetQuotaInformationFile, ZwSetQuotaInformationFile, ZwSetQuotaInformationFile routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwSetQuotaInformationFile
-	NtSetQuotaInformationFile
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# NtSetQuotaInformationFile function


## -description


The <b>ZwSetQuotaInformationFile</b> routine changes quota entries for the volume associated with the <i>FileHandle</i> parameter. All of the quota entries in the specified buffer are applied to the volume. 


## -syntax


````
NTSTATUS ZwSetQuotaInformationFile(
  _In_  HANDLE           FileHandle,
  _Out_ PIO_STATUS_BLOCK IoStatusBlock,
  _In_  PVOID            Buffer,
  _In_  ULONG            Length
);
````


## -parameters




### -param FileHandle [in]

A handle for the file object that represents the file or volume for which the quota information is to be modified.


### -param IoStatusBlock [out]

The address of the caller's I/O status block.


### -param Buffer [in]

A buffer containing the new quota entries that should be applied to the volume. The quota information must be formatted as one or more <a href="..\ntifs\ns-ntifs-_file_quota_information.md">FILE_QUOTA_INFORMATION</a> structures. The <b>NextEntryOffset</b> field in the <b>FILE_QUOTA_INFORMATION</b> structure contains the offset, in bytes, of the next quota entry in the list. If there are no more entries after the current one, this member is zero.


### -param Length [in]

The length in bytes of the buffer. 


## -returns



The <b>ZwSetQuotaInformationFile</b> routine returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

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



The <b>ZwSetQuotaInformationFile</b> routine applies all of the quota entries in the specified <i>Buffer</i> parameter to the volume.

The <b>IoCheckQuotaBufferValidity</b> function can check whether the specified quota buffer passed as the <i>Buffer</i> parameter is valid.

A call to <b>ZwSetQuotaInformationFile</b> will result in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a> request being sent to the device object that is associated with the file object whose handle is stored in the <i>FileHandle</i> parameter.

If the underlying file system does not support quota information (FAT and CDFS file systems, for example), <b>ZwSetQuotaInformationFile</b> will fail returning STATUS_INVALID_DEVICE_REQUEST.

<div class="alert"><b>Note</b>  If the call to the <b>ZwSetQuotaInformationFile</b> function occurs in user mode, you should use the name "<a href="https://msdn.microsoft.com/library/windows/hardware/ff557684">NtSetQuotaInformationFile</a>" instead of "<b>ZwSetQuotaInformationFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a>



<a href="..\ntifs\ns-ntifs-_file_quota_information.md">FILE_QUOTA_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_get_quota_information.md">FILE_GET_QUOTA_INFORMATION</a>



<a href="..\wudfwdm\ns-wudfwdm-_io_status_block.md">IO_STATUS_BLOCK</a>



<a href="..\ntifs\nf-ntifs-zwqueryquotainformationfile.md">ZwQueryQuotaInformationFile</a>



<a href="..\ntifs\nf-ntifs-iocheckquotabuffervalidity.md">IoCheckQuotaBufferValidity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549293">IRP_MJ_QUERY_QUOTA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwSetQuotaInformationFile routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

