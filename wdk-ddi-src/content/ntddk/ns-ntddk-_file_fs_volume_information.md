---
UID: NS:ntddk._FILE_FS_VOLUME_INFORMATION
title: "_FILE_FS_VOLUME_INFORMATION"
author: windows-driver-content
description: The FILE_FS_VOLUME_INFORMATION structure is used to query information about a volume on which a file system is mounted.
old-location: ifsk\file_fs_volume_information.htm
old-project: ifsk
ms.assetid: b0c6f733-2d8b-4140-bb2a-2a28212d3e69
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFILE_FS_VOLUME_INFORMATION, FILE_FS_VOLUME_INFORMATION, FILE_FS_VOLUME_INFORMATION structure [Installable File System Drivers], PFILE_FS_VOLUME_INFORMATION, PFILE_FS_VOLUME_INFORMATION structure pointer [Installable File System Drivers], _FILE_FS_VOLUME_INFORMATION, fileinformationstructures_97bfe785-4c25-4402-91be-0fd2bda36c5d.xml, ifsk.file_fs_volume_information, ntddk/FILE_FS_VOLUME_INFORMATION, ntddk/PFILE_FS_VOLUME_INFORMATION"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	FILE_FS_VOLUME_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_FS_VOLUME_INFORMATION, *PFILE_FS_VOLUME_INFORMATION
---

# _FILE_FS_VOLUME_INFORMATION structure


## -description


The FILE_FS_VOLUME_INFORMATION structure is used to query information about a volume on which a file system is mounted. 


## -struct-fields




### -field VolumeCreationTime

Time when the volume was created. 


### -field VolumeSerialNumber

Serial number of the volume. 


### -field VolumeLabelLength

Length, in bytes, of the name of the volume. 


### -field SupportsObjects

<b>TRUE</b> if the file system supports object-oriented file system objects, <b>FALSE</b> otherwise. 


### -field VolumeLabel

Name of the volume. 


## -remarks



This information can be queried in either of the following ways: 

<ul>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>, passing FileFsVolumeInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_FS_VOLUME_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code IRP_MJ_QUERY_VOLUME_INFORMATION. 

</li>
</ul>
No specific access rights are required to query this information. Thus this information is available as long as the volume is accessed through an open handle to the volume itself, or to a file or directory on the volume. 

All dates and times are in absolute system-time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a> must be at least <b>sizeof</b> (FILE_FS_VOLUME_INFORMATION). 

This structure must be aligned on a LONGLONG (8-byte) boundary. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>
 

 

