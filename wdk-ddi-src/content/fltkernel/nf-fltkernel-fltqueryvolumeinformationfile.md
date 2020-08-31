---
UID: NF:fltkernel.FltQueryVolumeInformationFile
title: FltQueryVolumeInformationFile function (fltkernel.h)
description: FltQueryVolumeInformationFile retrieves volume information for a given file, directory, storage device, or volume.
old-location: ifsk\fltqueryvolumeinformationfile.htm
tech.root: ifsk
ms.assetid: 3f93ce0a-f1f0-4b5b-aaf3-ce6698eb5055
ms.date: 04/16/2018
keywords: ["FltQueryVolumeInformationFile function"]
ms.keywords: FileFsAttributeInformation, FileFsControlInformation, FileFsDeviceInformation, FileFsDriverPathInformation, FileFsFullSizeInformation, FileFsObjectIdInformation, FileFsSectorSizeInformation, FileFsSizeInformation, FileFsVolumeInformation, FltApiRef_p_to_z_b2a51db8-6931-46c6-84ba-eb29097ac89e.xml, FltQueryVolumeInformationFile, FltQueryVolumeInformationFile function [Installable File System Drivers], fltkernel/FltQueryVolumeInformationFile, ifsk.fltqueryvolumeinformationfile
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltQueryVolumeInformationFile
 - fltkernel/FltQueryVolumeInformationFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltQueryVolumeInformationFile
---

# FltQueryVolumeInformationFile function


## -description

<b>FltQueryVolumeInformationFile</b> retrieves volume information for a given file, directory, storage device, or volume.

## -parameters

### -param Instance 

[in]
Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>.

### -param FileObject 

[in]
File object pointer for an open file, directory, storage device, or volume. This parameter is required and cannot be <b>NULL</b>.

### -param FsInformation 

[out]
Pointer to a caller-allocated buffer that receives information about the file. The <i>FsInformationClass</i> parameter specifies the type of information. This parameter is required and cannot be <b>NULL</b>.

### -param Length 

[in]
Size, in bytes, of the <i>FsInformation</i> buffer.

### -param FsInformationClass 

[in]
Type of volume information to be returned. One of the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="FileFsAttributeInformation"></a><a id="filefsattributeinformation"></a><a id="FILEFSATTRIBUTEINFORMATION"></a><dl>
<dt><b>FileFsAttributeInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_attribute_information">FILE_FS_ATTRIBUTE_INFORMATION</a> structure that contains attribute information about the file system responsible for the volume. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsControlInformation"></a><a id="filefscontrolinformation"></a><a id="FILEFSCONTROLINFORMATION"></a><dl>
<dt><b>FileFsControlInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_control_information">FILE_FS_CONTROL_INFORMATION</a> structure that contains file system control information about the volume. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsDeviceInformation"></a><a id="filefsdeviceinformation"></a><a id="FILEFSDEVICEINFORMATION"></a><dl>
<dt><b>FileFsDeviceInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_fs_device_information">FILE_FS_DEVICE_INFORMATION</a> structure that contains device information for the volume. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsDriverPathInformation"></a><a id="filefsdriverpathinformation"></a><a id="FILEFSDRIVERPATHINFORMATION"></a><dl>
<dt><b>FileFsDriverPathInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_driver_path_information">FILE_FS_DRIVER_PATH_INFORMATION</a> structure that contains information about whether a specified driver is in the I/O path for the volume. The caller must store the name of the driver into the <b>FILE_FS_DRIVER_PATH_INFORMATION</b> structure before calling <b>FltQueryVolumeInformationFile</b>. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsFullSizeInformation"></a><a id="filefsfullsizeinformation"></a><a id="FILEFSFULLSIZEINFORMATION"></a><dl>
<dt><b>FileFsFullSizeInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_full_size_information">FILE_FS_FULL_SIZE_INFORMATION</a> structure that contains information about the total amount of space available on the volume. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsObjectIdInformation"></a><a id="filefsobjectidinformation"></a><a id="FILEFSOBJECTIDINFORMATION"></a><dl>
<dt><b>FileFsObjectIdInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_objectid_information">FILE_FS_OBJECTID_INFORMATION</a> structure that contains file-system-specific object ID information for the volume. Note that this is not the same as the (GUID-based) unique volume name that is assigned by the operating system. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsSizeInformation"></a><a id="filefssizeinformation"></a><a id="FILEFSSIZEINFORMATION"></a><dl>
<dt><b>FileFsSizeInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_size_information">FILE_FS_SIZE_INFORMATION</a> structure containing information about the amount of space on the volume that is available to the user that is associated with the calling thread. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsVolumeInformation"></a><a id="filefsvolumeinformation"></a><a id="FILEFSVOLUMEINFORMATION"></a><dl>
<dt><b>FileFsVolumeInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_volume_information">FILE_FS_VOLUME_INFORMATION</a> that contains information about the volume such as the volume label, serial number, and creation time. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsSectorSizeInformation"></a><a id="filefssectorsizeinformation"></a><a id="FILEFSSECTORSIZEINFORMATION"></a><dl>
<dt><b>FileFsSectorSizeInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_sector_size_information">FILE_FS_SECTOR_SIZE_INFORMATION</a> structure that contains information about the physical and logical sector sizes of a volume.

</td>
</tr>
</table>

### -param LengthReturned 

[out, optional]
Pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in the <i>FsInformation</i> buffer. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>FltQueryVolumeInformationFile</b> returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_VOLUME_DISMOUNTED</b></dt>
</dl>
</td>
<td width="60%">
The volume is not currently mounted. This is an error code. 

</td>
</tr>
</table>

## -remarks

<b>FltQueryVolumeInformationFile</b> retrieves volume information for a given file, directory, storage device, or volume. 

If the <i>FileObject</i> represents a direct device open, only <i>FileFsDeviceInformation</i> can be specified as the value of <i>FsInformationClass</i>. 

<b>FltQueryVolumeInformationFile</b> returns zero in any member of a FILE_FS_<i>XXX</i>_INFORMATION structure that is not supported by a particular file system.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_attribute_information">FILE_FS_ATTRIBUTE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_control_information">FILE_FS_CONTROL_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_fs_device_information">FILE_FS_DEVICE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_driver_path_information">FILE_FS_DRIVER_PATH_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_full_size_information">FILE_FS_FULL_SIZE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_objectid_information">FILE_FS_OBJECTID_INFORMATION</a>



<b>FILE_FS_SECTOR_SIZE_INFORMATION</b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_size_information">FILE_FS_SIZE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_volume_information">FILE_FS_VOLUME_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetinformationfile">FltSetInformationFile</a>

