---
UID: NF:ntifs.ZwSetVolumeInformationFile
title: ZwSetVolumeInformationFile function (ntifs.h)
description: The ZwSetVolumeInformationFile routine modifies information about the volume associated with a given file, directory, storage device, or volume.
old-location: kernel\zwsetvolumeinformationfile.htm
tech.root: kernel
ms.assetid: 6afc3e8b-0be0-4728-b00f-deea5e60d27e
ms.date: 04/30/2018
ms.keywords: NtSetInformationFile, ZwSetVolumeInformationFile, ZwSetVolumeInformationFile routine [Kernel-Mode Driver Architecture], k111_580470b4-9769-4fec-9811-04f703473131.xml, kernel.zwsetvolumeinformationfile, ntifs/NtSetInformationFile, ntifs/ZwSetVolumeInformationFile
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
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
- ZwSetVolumeInformationFile
- NtSetInformationFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwSetVolumeInformationFile function


## -description


The <b>ZwSetVolumeInformationFile</b> routine modifies information about the volume associated with a given file, directory, storage device, or volume. 


## -parameters




### -param FileHandle [in]

Handle to a file object for an open file, directory, storage device, or volume whose volume information is to be modified. 


### -param IoStatusBlock [out]

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the operation. 


### -param FsInformation [in]

Pointer to a caller-allocated buffer containing the volume information to be modified. The structure of the information in this buffer depends on the value of <i>FsInformationClass</i>, as shown in the following table. 


### -param Length [in]

Size in bytes of the buffer pointed to by <i>FsInformation</i>. The caller should set this parameter according to the given <i>FsInformationClass</i>. 


### -param FsInformationClass [in]

Type of volume information to be set. One of the following: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FileFsControlInformation</b>

</td>
<td>
Set <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_file_fs_control_information">FILE_FS_CONTROL_INFORMATION</a> for the volume. 

</td>
</tr>
<tr>
<td>
<b>FileFsLabelInformation</b>

</td>
<td>
Set <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_file_fs_label_information">FILE_FS_LABEL_INFORMATION</a> for the volume. 

</td>
</tr>
<tr>
<td>
<b>FileFsObjectIdInformation</b>

</td>
<td>
Set <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_file_fs_objectid_information">FILE_FS_OBJECTID_INFORMATION</a> for the volume. 

</td>
</tr>
</table>
 


## -returns



<b>ZwSetVolumeInformationFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for <i>Length</i>. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567112">ZwSetVolumeInformationFile</a> encountered a pool allocation failure. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for <i>FsInformationClass</i>. This is an error code.

</td>
</tr>
</table>
 




## -remarks



To query volume information, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>. 

To change information about a file, call <b>ZwSetVolumeInformationFile</b>. 

Minifilters should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetinformationfile">FltSetInformationFile</a> instead of <b>ZwSetVolumeInformationFile</b>. 

<div class="alert"><b>Note</b>  If the call to the <b>ZwSetVolumeInformationFile</b>function occurs in user mode, you should use the name "<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntsetinformationfile">NtSetInformationFile</a>" instead of "<b>ZwSetVolumeInformationFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_file_fs_control_information">FILE_FS_CONTROL_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_file_fs_label_information">FILE_FS_LABEL_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_file_fs_objectid_information">FILE_FS_OBJECTID_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetinformationfile">FltSetInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-volume-information">IRP_MJ_SET_VOLUME_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>
 

 

