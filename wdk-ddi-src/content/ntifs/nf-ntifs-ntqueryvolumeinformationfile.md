---
UID: NF:ntifs.NtQueryVolumeInformationFile
title: NtQueryVolumeInformationFile function
author: windows-driver-content
description: The ZwQueryVolumeInformationFile routine retrieves information about the volume associated with a given file, directory, storage device, or volume.
old-location: kernel\zwqueryvolumeinformationfile.htm
old-project: kernel
ms.assetid: f83b7171-e250-4c2c-b3cc-2924f58e406e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: NtQueryVolumeInformationFile, ZwQueryVolumeInformationFile, ZwQueryVolumeInformationFile routine [Kernel-Mode Driver Architecture], k111_1ca2c72d-6eb1-4bfa-a1f9-06cc26643662.xml, kernel.zwqueryvolumeinformationfile, ntifs/NtQueryVolumeInformationFile, ntifs/ZwQueryVolumeInformationFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwQueryVolumeInformationFile
-	NtQueryVolumeInformationFile
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# NtQueryVolumeInformationFile function


## -description


The <b>ZwQueryVolumeInformationFile</b> routine retrieves information about the volume associated with a given file, directory, storage device, or volume.


## -syntax


````
NTSTATUS ZwQueryVolumeInformationFile(
  _In_  HANDLE               FileHandle,
  _Out_ PIO_STATUS_BLOCK     IoStatusBlock,
  _Out_ PVOID                FsInformation,
  _In_  ULONG                Length,
  _In_  FS_INFORMATION_CLASS FsInformationClass
);
````


## -parameters




### -param FileHandle [in]

A handle to a file object returned by <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a> or <a href="..\wdm\nf-wdm-zwopenfile.md">ZwOpenFile</a> for an open file, directory, storage device, or volume for which volume information is being requested.


### -param IoStatusBlock [out]

A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the query operation. For successful calls that return data, the number of bytes written to the <i>FsInformation</i> buffer is returned in the structure's <b>Information</b> member.


### -param FsInformation [out]

A pointer to a caller-allocated buffer that receives the desired information about the volume. The structure of the information returned in the buffer is defined by the <i>FsInformationClass</i> parameter.


### -param Length [in]

Size in bytes of the buffer pointed to by <i>FsInformation</i>. The caller should set this parameter according to the given <i>FsInformationClass</i>.


### -param FsInformationClass [in]

Type of information to be returned about the volume. Set this member to one of the following <a href="..\wdm\ne-wdm-_fsinfoclass.md">FS_INFORMATION_CLASS</a> enumeration values.

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
Return a <a href="..\ntifs\ns-ntifs-_file_fs_attribute_information.md">FILE_FS_ATTRIBUTE_INFORMATION</a> structure containing attribute information about the file system responsible for the volume.

</td>
</tr>
<tr>
<td>
<b>FileFsControlInformation</b>

</td>
<td>
Return a <a href="..\ntifs\ns-ntifs-_file_fs_control_information.md">FILE_FS_CONTROL_INFORMATION</a> structure containing file system control information about the volume.

</td>
</tr>
<tr>
<td>
<b>FileFsDeviceInformation</b>

</td>
<td>
Return a <a href="..\wdm\ns-wdm-_file_fs_device_information.md">FILE_FS_DEVICE_INFORMATION</a> structure containing device information for the volume.

</td>
</tr>
<tr>
<td>
<b>FileFsDriverPathInformation</b>

</td>
<td>
Return a <a href="..\ntifs\ns-ntifs-_file_fs_driver_path_information.md">FILE_FS_DRIVER_PATH_INFORMATION</a> structure containing information about whether a specified driver is in the I/O path for the volume. The caller must store the name of the driver into the <b>FILE_FS_DRIVER_PATH_INFORMATION</b> structure before calling <b>ZwQueryVolumeInformationFile</b>.

</td>
</tr>
<tr>
<td>
<b>FileFsFullSizeInformation</b>

</td>
<td>
Return a <a href="..\ntddk\ns-ntddk-_file_fs_full_size_information.md">FILE_FS_FULL_SIZE_INFORMATION</a> structure containing information about the total amount of space available on the volume.

</td>
</tr>
<tr>
<td>
<b>FileFsObjectIdInformation</b>

</td>
<td>
Return a <a href="..\ntddk\ns-ntddk-_file_fs_objectid_information.md">FILE_FS_OBJECTID_INFORMATION</a> structure containing file system-specific object ID information for the volume. Note that this is not the same as the (GUID-based) unique volume name assigned by the operating system.

</td>
</tr>
<tr>
<td>
<b>FileFsSizeInformation</b>

</td>
<td>
Return a <a href="..\ntddk\ns-ntddk-_file_fs_size_information.md">FILE_FS_SIZE_INFORMATION</a> structure containing information about the amount of space on the volume that is available to the user associated with the calling thread.

</td>
</tr>
<tr>
<td>
<b>FileFsVolumeInformation</b>

</td>
<td>
Return a <a href="..\ntddk\ns-ntddk-_file_fs_volume_information.md">FILE_FS_VOLUME_INFORMATION</a> containing information about the volume such as the volume label, serial number, and creation time.

</td>
</tr>
<tr>
<td>
<b>FileFsSectorSizeInformation</b>

</td>
<td>
Return a <a href="..\ntddk\ns-ntddk-_file_fs_sector_size_information.md">FILE_FS_SECTOR_SIZE_INFORMATION</a> structure that contains information about the physical and logical sector sizes of a volume.

</td>
</tr>
</table>
 


## -returns



<b>ZwQueryVolumeInformationFile</b> returns STATUS_SUCCESS or an appropriate error status.




## -remarks



<b>ZwQueryVolumeInformationFile</b> retrieves information about the volume associated with a given file, directory, storage device, or volume.

If the <i>FileHandle</i> represents a direct device open, only <i>FileFsDeviceInformation</i> can be specified as the value of <i>FsInformationClass</i>.

<b>ZwQueryVolumeInformationFile</b> returns zero in any member of a <b>FILE_<i>XXX</i>_INFORMATION</b> structure that is not supported by the file system.

For information about other file information query routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545843">File Objects</a>.

Minifilters should use <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformationfile.md">FltQueryVolumeInformationFile</a> instead of <b>ZwQueryVolumeInformationFile</b>.

Callers of <b>ZwQueryVolumeInformationFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to the <b>ZwQueryVolumeInformationFile</b> function occurs in user mode, you should use the name "<b>NtQueryVolumeInformationFile</b>" instead of "<b>ZwQueryVolumeInformationFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549415">IRP_MJ_SET_VOLUME_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformationfile.md">FltQueryVolumeInformationFile</a>



<a href="..\wdm\ns-wdm-_file_fs_device_information.md">FILE_FS_DEVICE_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>



<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>



<a href="..\wdm\nf-wdm-zwopenfile.md">ZwOpenFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="..\ntddk\ns-ntddk-_file_fs_objectid_information.md">FILE_FS_OBJECTID_INFORMATION</a>



<a href="..\ntddk\ns-ntddk-_file_fs_full_size_information.md">FILE_FS_FULL_SIZE_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_fs_control_information.md">FILE_FS_CONTROL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a>



<a href="..\ntddk\ns-ntddk-_file_fs_volume_information.md">FILE_FS_VOLUME_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_fs_driver_path_information.md">FILE_FS_DRIVER_PATH_INFORMATION</a>



<a href="..\ntddk\ns-ntddk-_file_fs_size_information.md">FILE_FS_SIZE_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_fs_attribute_information.md">FILE_FS_ATTRIBUTE_INFORMATION</a>



<a href="..\ntifs\nf-ntifs-zwsetvolumeinformationfile.md">ZwSetVolumeInformationFile</a>



<a href="..\ntifs\nf-ntifs-zwquerydirectoryfile.md">ZwQueryDirectoryFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQueryVolumeInformationFile routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

