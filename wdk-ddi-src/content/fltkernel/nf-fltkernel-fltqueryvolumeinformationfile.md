---
UID: NF:fltkernel.FltQueryVolumeInformationFile
title: FltQueryVolumeInformationFile function
author: windows-driver-content
description: FltQueryVolumeInformationFile retrieves volume information for a given file, directory, storage device, or volume.
old-location: ifsk\fltqueryvolumeinformationfile.htm
old-project: ifsk
ms.assetid: 3f93ce0a-f1f0-4b5b-aaf3-ce6698eb5055
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltQueryVolumeInformationFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltQueryVolumeInformationFile
req.alt-loc: fltmgr.sys
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
req.typenames: EXpsFontRestriction
---

# FltQueryVolumeInformationFile function



## -description
<b>FltQueryVolumeInformationFile</b> retrieves volume information for a given file, directory, storage device, or volume. 



## -syntax

````
NTSTATUS FltQueryVolumeInformationFile(
  _In_      PFLT_INSTANCE        Instance,
  _In_      PFILE_OBJECT         FileObject,
  _Out_     PVOID                FsInformation,
  _In_      ULONG                Length,
  _In_      FS_INFORMATION_CLASS FsInformationClass,
  _Out_opt_ PULONG               LengthReturned
);
````


## -parameters

### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

File object pointer for an open file, directory, storage device, or volume. This parameter is required and cannot be <b>NULL</b>. 


### -param FsInformation [out]

Pointer to a caller-allocated buffer that receives information about the file. The <i>FsInformationClass</i> parameter specifies the type of information. This parameter is required and cannot be <b>NULL</b>. 


### -param Length [in]

Size, in bytes, of the <i>FsInformation</i> buffer. 


### -param FsInformationClass [in]

Type of volume information to be returned. One of the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param FileFsAttributeInformation

</td>
<td width="60%">
Return a <a href="..\ntifs\ns-ntifs-_file_fs_attribute_information.md">FILE_FS_ATTRIBUTE_INFORMATION</a> structure that contains attribute information about the file system responsible for the volume. 

</td>
</tr>
<tr>

### -param FileFsControlInformation

</td>
<td width="60%">
Return a <a href="..\ntifs\ns-ntifs-_file_fs_control_information.md">FILE_FS_CONTROL_INFORMATION</a> structure that contains file system control information about the volume. 

</td>
</tr>
<tr>

### -param FileFsDeviceInformation

</td>
<td width="60%">
Return a <a href="..\wdm\ns-wdm-_file_fs_device_information.md">FILE_FS_DEVICE_INFORMATION</a> structure that contains device information for the volume. 

</td>
</tr>
<tr>

### -param FileFsDriverPathInformation

</td>
<td width="60%">
Return a <a href="..\ntifs\ns-ntifs-_file_fs_driver_path_information.md">FILE_FS_DRIVER_PATH_INFORMATION</a> structure that contains information about whether a specified driver is in the I/O path for the volume. The caller must store the name of the driver into the <b>FILE_FS_DRIVER_PATH_INFORMATION</b> structure before calling <b>FltQueryVolumeInformationFile</b>. 

</td>
</tr>
<tr>

### -param FileFsFullSizeInformation

</td>
<td width="60%">
Return a <a href="..\ntddk\ns-ntddk-_file_fs_full_size_information.md">FILE_FS_FULL_SIZE_INFORMATION</a> structure that contains information about the total amount of space available on the volume. 

</td>
</tr>
<tr>

### -param FileFsObjectIdInformation

</td>
<td width="60%">
Return a <a href="..\ntddk\ns-ntddk-_file_fs_objectid_information.md">FILE_FS_OBJECTID_INFORMATION</a> structure that contains file-system-specific object ID information for the volume. Note that this is not the same as the (GUID-based) unique volume name that is assigned by the operating system. 

</td>
</tr>
<tr>

### -param FileFsSizeInformation

</td>
<td width="60%">
Return a <a href="..\ntddk\ns-ntddk-_file_fs_size_information.md">FILE_FS_SIZE_INFORMATION</a> structure containing information about the amount of space on the volume that is available to the user that is associated with the calling thread. 

</td>
</tr>
<tr>

### -param FileFsVolumeInformation

</td>
<td width="60%">
Return a <a href="..\ntddk\ns-ntddk-_file_fs_volume_information.md">FILE_FS_VOLUME_INFORMATION</a> that contains information about the volume such as the volume label, serial number, and creation time. 

</td>
</tr>
<tr>

### -param FileFsSectorSizeInformation

</td>
<td width="60%">
Return a <a href="..\ntifs\ns-ntifs-_file_fs_driver_path_information.md">FILE_FS_SECTOR_SIZE_INFORMATION</a> structure that contains information about the physical and logical sector sizes of a volume.

</td>
</tr>
</table>
 


### -param LengthReturned [out, optional]

Pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in the <i>FsInformation</i> buffer. This parameter is optional and can be <b>NULL</b>. 


## -returns
<b>FltQueryVolumeInformationFile</b> returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value such as the following: 
<dl>
<dt><b>STATUS_VOLUME_DISMOUNTED</b></dt>
</dl>The volume is not currently mounted. This is an error code. 

 


## -remarks
<b>FltQueryVolumeInformationFile</b> retrieves volume information for a given file, directory, storage device, or volume. 

If the <i>FileObject</i> represents a direct device open, only <i>FileFsDeviceInformation</i> can be specified as the value of <i>FsInformationClass</i>. 

<b>FltQueryVolumeInformationFile</b> returns zero in any member of a FILE_FS_<i>XXX</i>_INFORMATION structure that is not supported by a particular file system. 


## -see-also
<dl>
<dt>
<a href="..\ntifs\ns-ntifs-_file_fs_attribute_information.md">FILE_FS_ATTRIBUTE_INFORMATION</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_file_fs_control_information.md">FILE_FS_CONTROL_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_file_fs_device_information.md">FILE_FS_DEVICE_INFORMATION</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_file_fs_driver_path_information.md">FILE_FS_DRIVER_PATH_INFORMATION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_file_fs_full_size_information.md">FILE_FS_FULL_SIZE_INFORMATION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_file_fs_objectid_information.md">FILE_FS_OBJECTID_INFORMATION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_file_fs_size_information.md">FILE_FS_SIZE_INFORMATION</a>
</dt>
<dt><b>FILE_FS_SECTOR_SIZE_INFORMATION</b></dt>
<dt>
<a href="..\ntddk\ns-ntddk-_file_fs_volume_information.md">FILE_FS_VOLUME_INFORMATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltQueryVolumeInformationFile function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

