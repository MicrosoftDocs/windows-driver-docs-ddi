---
UID: NF:fltkernel.FltQueryVolumeInformation
title: FltQueryVolumeInformation function
author: windows-driver-content
description: The FltQueryVolumeInformation routine retrieves information about the volume that the given instance is attached to.
old-location: ifsk\fltqueryvolumeinformation.htm
old-project: ifsk
ms.assetid: 57b65e87-7f2d-44fc-84b9-e029c8075be3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltQueryVolumeInformation, FileFsAttributeInformation, FileFsControlInformation, FileFsFullSizeInformation, ifsk.fltqueryvolumeinformation, FileFsDriverPathInformation, FileFsDeviceInformation, FileFsObjectIdInformation, FileFsSizeInformation, FltApiRef_p_to_z_1b2db9a1-36d0-4503-bd97-7f24b68ad513.xml, FileFsVolumeInformation, FltQueryVolumeInformation routine [Installable File System Drivers], FileFsSectorSizeInformation, fltkernel/FltQueryVolumeInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available and supported in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP with Service Pack 2 (SP2), Windows Server 2003 SP1 and later  Windows operating systems. Not available or supported in Windows 2000 SP4 and earlier Windows operating systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltQueryVolumeInformation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltQueryVolumeInformation function


## -description


The <b>FltQueryVolumeInformation</b> routine retrieves information about the volume that the given instance is attached to. 


## -syntax


````
NTSTATUS FltQueryVolumeInformation(
  _In_  PFLT_INSTANCE        Instance,
  _Out_ PIO_STATUS_BLOCK     Iosb,
  _Out_ PVOID                FsInformation,
  _In_  ULONG                Length,
  _In_  FS_INFORMATION_CLASS FsInformationClass
);
````


## -parameters




### -param Instance [in]

An opaque instance pointer for a minifilter driver instance that is attached to the volume. 


### -param Iosb [out]

A pointer to caller-allocated IO_STATUS_BLOCK structure that receives the final completion status and information about the query operation. For successful calls that return data, the number of bytes written to the <i>FsInformation</i> buffer is returned in the structure's <b>Information</b> member. 


### -param FsInformation [out]

A pointer to a caller-allocated buffer that receives the desired information about the volume. The structure of the information returned in the buffer is defined by the <i>FsInformationClass</i> parameter. 


### -param Length [in]

The size in bytes of the buffer that <i>FsInformation</i> points to. The caller should set this parameter according to the given <i>FsInformationClass</i>. For example, if the value of <i>FsInformationClass</i> is FileFsControlInformation, <i>Length</i> must be at least <b>sizeof</b>(FILE_FS_CONTROL_INFORMATION). 


### -param FsInformationClass [in]

The type of information requested. One of the following value. 

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
Return a <a href="..\ntifs\ns-ntifs-_file_fs_attribute_information.md">FILE_FS_ATTRIBUTE_INFORMATION</a> structure containing attribute information about the file system responsible for the volume. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsControlInformation"></a><a id="filefscontrolinformation"></a><a id="FILEFSCONTROLINFORMATION"></a><dl>
<dt><b>FileFsControlInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="..\ntifs\ns-ntifs-_file_fs_control_information.md">FILE_FS_CONTROL_INFORMATION</a> structure containing file system control information about the volume. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsDeviceInformation"></a><a id="filefsdeviceinformation"></a><a id="FILEFSDEVICEINFORMATION"></a><dl>
<dt><b>FileFsDeviceInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="..\wdm\ns-wdm-_file_fs_device_information.md">FILE_FS_DEVICE_INFORMATION</a> structure containing device information for the volume. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsDriverPathInformation"></a><a id="filefsdriverpathinformation"></a><a id="FILEFSDRIVERPATHINFORMATION"></a><dl>
<dt><b>FileFsDriverPathInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="..\ntifs\ns-ntifs-_file_fs_driver_path_information.md">FILE_FS_DRIVER_PATH_INFORMATION</a> structure containing information about whether a specified driver is in the I/O path for the volume. The caller must store the name of the driver into the <b>FILE_FS_DRIVER_PATH_INFORMATION</b> structure before calling <b>FltQueryVolumeInformation</b>. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsFullSizeInformation"></a><a id="filefsfullsizeinformation"></a><a id="FILEFSFULLSIZEINFORMATION"></a><dl>
<dt><b>FileFsFullSizeInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="..\ntddk\ns-ntddk-_file_fs_full_size_information.md">FILE_FS_FULL_SIZE_INFORMATION</a> structure containing information about the total amount of space available on the volume. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsObjectIdInformation"></a><a id="filefsobjectidinformation"></a><a id="FILEFSOBJECTIDINFORMATION"></a><dl>
<dt><b>FileFsObjectIdInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="..\ntddk\ns-ntddk-_file_fs_objectid_information.md">FILE_FS_OBJECTID_INFORMATION</a> structure containing file system-specific object ID information for the volume. Be aware that this is not the same as the (GUID-based) unique volume name assigned by the operating system. <div class="alert"><b>Note</b>  This value is not valid for snapshot volumes.</div>
<div> </div>


</td>
</tr>
<tr>
<td width="40%"><a id="FileFsSizeInformation"></a><a id="filefssizeinformation"></a><a id="FILEFSSIZEINFORMATION"></a><dl>
<dt><b>FileFsSizeInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="..\ntddk\ns-ntddk-_file_fs_size_information.md">FILE_FS_SIZE_INFORMATION</a> structure containing information about the amount of space on the volume that is available to the user associated with the calling thread. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsVolumeInformation"></a><a id="filefsvolumeinformation"></a><a id="FILEFSVOLUMEINFORMATION"></a><dl>
<dt><b>FileFsVolumeInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="..\ntddk\ns-ntddk-_file_fs_volume_information.md">FILE_FS_VOLUME_INFORMATION</a> containing information about the volume such as the volume label, serial number, and creation time. 

</td>
</tr>
<tr>
<td width="40%"><a id="FileFsSectorSizeInformation"></a><a id="filefssectorsizeinformation"></a><a id="FILEFSSECTORSIZEINFORMATION"></a><dl>
<dt><b>FileFsSectorSizeInformation</b></dt>
</dl>
</td>
<td width="60%">
Return a <a href="..\ntddk\ns-ntddk-_file_fs_sector_size_information.md">FILE_FS_SECTOR_SIZE_INFORMATION</a> structure that contains information about the physical and logical sector sizes of a volume.

</td>
</tr>
</table>
 


## -returns



The <b>FltQueryVolumeInformation</b> routine returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a> encountered a pool allocation failure. This is an error code. 

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>Instance</i> is attached to a network volume. <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a> cannot be used to query network volume information. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



Fields in the FILE_<i>XXX</i>_INFORMATION structure that are not supported by the underlying file system are set to zero. 

To change information about a volume, call <a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a>. 

To get volume property information for the given volume, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumeproperties.md">FltGetVolumeProperties</a>. 

To get the volume name for a given volume, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumename.md">FltGetVolumeName</a>. 

To get the volume GUID name for a given volume, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumeguidname.md">FltGetVolumeGuidName</a>. 




## -see-also

<a href="..\ntddk\ns-ntddk-_file_fs_volume_information.md">FILE_FS_VOLUME_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_fs_control_information.md">FILE_FS_CONTROL_INFORMATION</a>



<a href="..\wdm\ns-wdm-_file_fs_device_information.md">FILE_FS_DEVICE_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_fs_attribute_information.md">FILE_FS_ATTRIBUTE_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltgetvolumeproperties.md">FltGetVolumeProperties</a>



<a href="..\fltkernel\nf-fltkernel-fltgetvolumename.md">FltGetVolumeName</a>



<a href="..\ntddk\ns-ntddk-_file_fs_full_size_information.md">FILE_FS_FULL_SIZE_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a>



<b>FILE_FS_SECTOR_SIZE_INFORMATION</b>



<a href="..\fltkernel\nf-fltkernel-fltgetvolumeguidname.md">FltGetVolumeGuidName</a>



<a href="..\ntifs\ns-ntifs-_file_fs_driver_path_information.md">FILE_FS_DRIVER_PATH_INFORMATION</a>



<a href="..\ntddk\ns-ntddk-_file_fs_size_information.md">FILE_FS_SIZE_INFORMATION</a>



<a href="..\ntddk\ns-ntddk-_file_fs_objectid_information.md">FILE_FS_OBJECTID_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltQueryVolumeInformation routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

