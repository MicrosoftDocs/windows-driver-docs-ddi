---
UID: NS:ntddk._FILE_FS_FULL_SIZE_INFORMATION
title: _FILE_FS_FULL_SIZE_INFORMATION (ntddk.h)
description: The FILE_FS_FULL_SIZE_INFORMATION structure is used to query sector size information for a file system volume.
old-location: ifsk\file_fs_full_size_information.htm
tech.root: ifsk
ms.assetid: 4a37bfed-cf8e-4c97-a9fe-a44d910bed92
ms.date: 04/16/2018
ms.keywords: "*PFILE_FS_FULL_SIZE_INFORMATION, FILE_FS_FULL_SIZE_INFORMATION, FILE_FS_FULL_SIZE_INFORMATION structure [Installable File System Drivers], PFILE_FS_FULL_SIZE_INFORMATION, PFILE_FS_FULL_SIZE_INFORMATION structure pointer [Installable File System Drivers], _FILE_FS_FULL_SIZE_INFORMATION, fileinformationstructures_7ba05d64-c04e-48cf-84f1-48ad8de5d35b.xml, ifsk.file_fs_full_size_information, ntddk/FILE_FS_FULL_SIZE_INFORMATION, ntddk/PFILE_FS_FULL_SIZE_INFORMATION"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- FILE_FS_FULL_SIZE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_FS_FULL_SIZE_INFORMATION, *PFILE_FS_FULL_SIZE_INFORMATION
---

# _FILE_FS_FULL_SIZE_INFORMATION structure


## -description


The FILE_FS_FULL_SIZE_INFORMATION structure is used to query sector size information for a file system volume. 


## -struct-fields




### -field TotalAllocationUnits

Total number of allocation units on the volume that are available to the user associated with the calling thread. 

<b>Microsoft Windows 2000 and later:</b> If per-user quotas are in use, this value may be less than the total number of allocation units on the disk. 


### -field CallerAvailableAllocationUnits

Total number of free allocation units on the volume that are available to the user associated with the calling thread. 

<b>Windows 2000 and later:</b> If per-user quotas are in use, this value may be less than the total number of free allocation units on the disk. 


### -field ActualAvailableAllocationUnits

Total number of free allocation units on the volume. 


### -field SectorsPerAllocationUnit

Number of sectors in each allocation unit. 


### -field BytesPerSector

Number of bytes in each sector. 


## -remarks



This information can be queried in either of the following ways: 

<ul>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>, passing FileFsFullSizeInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_FS_FULL_SIZE_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code IRP_MJ_QUERY_VOLUME_INFORMATION. 

</li>
</ul>
No specific access rights are required to query this information. Thus this information is available as long as the volume is accessed through an open handle to the volume itself, or to a file or directory on the volume. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a> must be at least <b>sizeof</b> (FILE_FS_FULL_SIZE_INFORMATION). 

This structure must be aligned on a LONGLONG (8-byte) boundary. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-volume-information">IRP_MJ_QUERY_VOLUME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>
 

 

