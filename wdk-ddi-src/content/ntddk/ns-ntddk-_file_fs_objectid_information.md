---
UID: NS:ntddk._FILE_FS_OBJECTID_INFORMATION
title: "_FILE_FS_OBJECTID_INFORMATION"
author: windows-driver-content
description: The FILE_FS_OBJECTID_INFORMATION structure is used to query or set the object ID for a file system volume.
old-location: ifsk\file_fs_objectid_information.htm
old-project: ifsk
ms.assetid: 37da9699-2edb-4a32-a865-2bf3b1cef157
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "_FILE_FS_OBJECTID_INFORMATION, fileinformationstructures_6a17f2c2-0aae-44a7-a65c-02c1ed2a9ed4.xml, PFILE_FS_OBJECTID_INFORMATION, *PFILE_FS_OBJECTID_INFORMATION, ifsk.file_fs_objectid_information, PFILE_FS_OBJECTID_INFORMATION structure pointer [Installable File System Drivers], FILE_FS_OBJECTID_INFORMATION structure [Installable File System Drivers], ntddk/PFILE_FS_OBJECTID_INFORMATION, FILE_FS_OBJECTID_INFORMATION, ntddk/FILE_FS_OBJECTID_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	FILE_FS_OBJECTID_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_FS_OBJECTID_INFORMATION, *PFILE_FS_OBJECTID_INFORMATION
---

# _FILE_FS_OBJECTID_INFORMATION structure


## -description


The FILE_FS_OBJECTID_INFORMATION structure is used to query or set the object ID for a file system volume. 


## -syntax


````
typedef struct _FILE_FS_OBJECTID_INFORMATION {
  UCHAR ObjectId[16];
  UCHAR ExtendedInfo[48];
} FILE_FS_OBJECTID_INFORMATION, *PFILE_FS_OBJECTID_INFORMATION;
````


## -struct-fields




### -field ObjectId

Object ID for the file system volume. 


### -field ExtendedInfo

Additional information about the file system volume. 


## -remarks



This information can be queried in either of the following ways: 

<ul>
<li>
Call <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a> or <a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a>, passing FileFsObjectIdInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_FS_OBJECTID_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code IRP_MJ_QUERY_VOLUME_INFORMATION. 

</li>
</ul>
No specific access rights are required to query this information. Thus this information is available as long as the volume is accessed through an open handle to the volume itself, or to a file or directory on the volume. 

This information can be set in either of the following ways: 

<ul>
<li>
Call <a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a> or <b>FltSetVolumeInformation</b>, passing FileFsObjectIdInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_FS_OBJECTID_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code IRP_MJ_SET_VOLUME_INFORMATION. 

</li>
</ul>
FILE_WRITE_DATA access to the volume is required to set this information. 

Support for volume object IDs is file-system-specific. In NTFS, volume object IDs are used extensively by the distributed link tracking service. 

It is important to note that the volume object ID is not the same as the volume GUID. The <i>volume object ID</i> is assigned to the file system volume by the file system. The <i>volume GUID</i>, or <i>unique volume name</i>, is file system-independent; it is assigned to the underlying storage volume by the Volume Mount Manager. 

To get the volume GUID for a volume, use the Win32 <b>GetVolumeNameForVolumeMountPoint</b> function or the <a href="..\fltkernel\nf-fltkernel-fltgetvolumeguidname.md">FltGetVolumeGuidName</a> routine. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>, <a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a>, <a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a>, or <a href="..\ntifs\nf-ntifs-zwsetvolumeinformationfile.md">ZwSetVolumeInformationFile</a> must be at least <b>sizeof</b> (FILE_FS_OBJECTID_INFORMATION). 

This structure must be aligned on a LONGLONG (8-byte) boundary. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549415">IRP_MJ_SET_VOLUME_INFORMATION</a>



<a href="..\ntifs\nf-ntifs-zwsetvolumeinformationfile.md">ZwSetVolumeInformationFile</a>



<a href="..\fltkernel\nf-fltkernel-fltgetvolumeguidname.md">FltGetVolumeGuidName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a>



<a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_FS_OBJECTID_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

