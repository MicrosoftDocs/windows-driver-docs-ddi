---
UID: NF:ntifs.ZwQueryVolumeInformationFile
title: ZwQueryVolumeInformationFile function (ntifs.h)
description: The ZwQueryVolumeInformationFile routine retrieves information about the volume associated with a given file, directory, storage device, or volume.
old-location: kernel\zwqueryvolumeinformationfile.htm
tech.root: kernel
ms.assetid: f83b7171-e250-4c2c-b3cc-2924f58e406e
ms.date: 04/30/2018
ms.keywords: NtQueryVolumeInformationFile, ZwQueryVolumeInformationFile, ZwQueryVolumeInformationFile routine [Kernel-Mode Driver Architecture], k111_1ca2c72d-6eb1-4bfa-a1f9-06cc26643662.xml, kernel.zwqueryvolumeinformationfile, ntifs/NtQueryVolumeInformationFile, ntifs/ZwQueryVolumeInformationFile
ms.topic: function
f1_keywords:
 - "ntifs/ZwQueryVolumeInformationFile"
req.header: ntifs.h
req.include-header: Ntifs.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwQueryVolumeInformationFile
- NtQueryVolumeInformationFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwQueryVolumeInformationFile function


## -description


The <b>ZwQueryVolumeInformationFile</b> routine retrieves information about the volume associated with a given file, directory, storage device, or volume.


## -parameters




### -param FileHandle [in]

A handle to a file object returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntopenfile">ZwOpenFile</a> for an open file, directory, storage device, or volume for which volume information is being requested.


### -param IoStatusBlock [out]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the query operation. For successful calls that return data, the number of bytes written to the <i>FsInformation</i> buffer is returned in the structure's <b>Information</b> member.


### -param FsInformation [out]

A pointer to a caller-allocated buffer that receives the desired information about the volume. The structure of the information returned in the buffer is defined by the <i>FsInformationClass</i> parameter.


### -param Length [in]

Size in bytes of the buffer pointed to by <i>FsInformation</i>. The caller should set this parameter according to the given <i>FsInformationClass</i>.


### -param FsInformationClass [in]

Type of information to be returned about the volume. Set this member to one of the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_fsinfoclass">FS_INFORMATION_CLASS</a> enumeration values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FileFsAttributeInformation</b>

</td>
<td>
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_attribute_information">FILE_FS_ATTRIBUTE_INFORMATION</a> structure containing attribute information about the file system responsible for the volume.

</td>
</tr>
<tr>
<td>
<b>FileFsControlInformation</b>

</td>
<td>
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_control_information">FILE_FS_CONTROL_INFORMATION</a> structure containing file system control information about the volume.

</td>
</tr>
<tr>
<td>
<b>FileFsDeviceInformation</b>

</td>
<td>
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_fs_device_information">FILE_FS_DEVICE_INFORMATION</a> structure containing device information for the volume.

</td>
</tr>
<tr>
<td>
<b>FileFsDriverPathInformation</b>

</td>
<td>
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_driver_path_information">FILE_FS_DRIVER_PATH_INFORMATION</a> structure containing information about whether a specified driver is in the I/O path for the volume. The caller must store the name of the driver into the <b>FILE_FS_DRIVER_PATH_INFORMATION</b> structure before calling <b>ZwQueryVolumeInformationFile</b>.

</td>
</tr>
<tr>
<td>
<b>FileFsFullSizeInformation</b>

</td>
<td>
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_full_size_information">FILE_FS_FULL_SIZE_INFORMATION</a> structure containing information about the total amount of space available on the volume.

</td>
</tr>
<tr>
<td>
<b>FileFsObjectIdInformation</b>

</td>
<td>
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_objectid_information">FILE_FS_OBJECTID_INFORMATION</a> structure containing file system-specific object ID information for the volume. Note that this is not the same as the (GUID-based) unique volume name assigned by the operating system.

</td>
</tr>
<tr>
<td>
<b>FileFsSizeInformation</b>

</td>
<td>
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_size_information">FILE_FS_SIZE_INFORMATION</a> structure containing information about the amount of space on the volume that is available to the user associated with the calling thread.

</td>
</tr>
<tr>
<td>
<b>FileFsVolumeInformation</b>

</td>
<td>
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_volume_information">FILE_FS_VOLUME_INFORMATION</a> containing information about the volume such as the volume label, serial number, and creation time.

</td>
</tr>
<tr>
<td>
<b>FileFsSectorSizeInformation</b>

</td>
<td>
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_sector_size_information">FILE_FS_SECTOR_SIZE_INFORMATION</a> structure that contains information about the physical and logical sector sizes of a volume.

</td>
</tr>
</table>
 


## -returns



<b>ZwQueryVolumeInformationFile</b> returns STATUS_SUCCESS or an appropriate error status.




## -remarks



<b>ZwQueryVolumeInformationFile</b> retrieves information about the volume associated with a given file, directory, storage device, or volume.

If the <i>FileHandle</i> represents a direct device open, only <i>FileFsDeviceInformation</i> can be specified as the value of <i>FsInformationClass</i>.

<b>ZwQueryVolumeInformationFile</b> returns zero in any member of a <b>FILE_<i>XXX</i>_INFORMATION</b> structure that is not supported by the file system.

For information about other file information query routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">File Objects</a>.

Minifilters should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformationfile">FltQueryVolumeInformationFile</a> instead of <b>ZwQueryVolumeInformationFile</b>.

Callers of <b>ZwQueryVolumeInformationFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/disabling-apcs">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to the <b>ZwQueryVolumeInformationFile</b> function occurs in user mode, you should use the name "<b>NtQueryVolumeInformationFile</b>" instead of "<b>ZwQueryVolumeInformationFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_attribute_information">FILE_FS_ATTRIBUTE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_control_information">FILE_FS_CONTROL_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_fs_device_information">FILE_FS_DEVICE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_driver_path_information">FILE_FS_DRIVER_PATH_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_full_size_information">FILE_FS_FULL_SIZE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_objectid_information">FILE_FS_OBJECTID_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_size_information">FILE_FS_SIZE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_volume_information">FILE_FS_VOLUME_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformationfile">FltQueryVolumeInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-volume-information">IRP_MJ_QUERY_VOLUME_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-volume-information">IRP_MJ_SET_VOLUME_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntopenfile">ZwOpenFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567047">ZwQueryDirectoryFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567112">ZwSetVolumeInformationFile</a>
 

 

