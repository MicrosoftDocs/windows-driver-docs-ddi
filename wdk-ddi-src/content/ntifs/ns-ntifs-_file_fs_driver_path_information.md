---
UID: NS:ntifs._FILE_FS_DRIVER_PATH_INFORMATION
title: "_FILE_FS_DRIVER_PATH_INFORMATION"
author: windows-driver-content
description: The FILE_FS_DRIVER_PATH_INFORMATION structure is used to query whether a given driver is in the I/O path for a file system volume.
old-location: ifsk\file_fs_driver_path_information.htm
old-project: ifsk
ms.assetid: 6149765b-cd2c-44f5-aa72-f4755e0b034c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILE_FS_DRIVER_PATH_INFORMATION, FILE_FS_DRIVER_PATH_INFORMATION, FILE_FS_DRIVER_PATH_INFORMATION structure [Installable File System Drivers], PFILE_FS_DRIVER_PATH_INFORMATION, PFILE_FS_DRIVER_PATH_INFORMATION structure pointer [Installable File System Drivers], _FILE_FS_DRIVER_PATH_INFORMATION, fileinformationstructures_9d09c9ee-18a0-4230-af6b-0cddadbac901.xml, ifsk.file_fs_driver_path_information, ntifs/FILE_FS_DRIVER_PATH_INFORMATION, ntifs/PFILE_FS_DRIVER_PATH_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FILE_FS_DRIVER_PATH_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_FS_DRIVER_PATH_INFORMATION, *PFILE_FS_DRIVER_PATH_INFORMATION
---

# _FILE_FS_DRIVER_PATH_INFORMATION structure


## -description


The FILE_FS_DRIVER_PATH_INFORMATION structure is used to query whether a given driver is in the I/O path for a file system volume. 


## -syntax


````
typedef struct _FILE_FS_DRIVER_PATH_INFORMATION {
  BOOLEAN DriverInPath;
  ULONG   DriverNameLength;
  WCHAR   DriverName[1];
} FILE_FS_DRIVER_PATH_INFORMATION, *PFILE_FS_DRIVER_PATH_INFORMATION;
````


## -struct-fields




### -field DriverInPath

Receives <b>TRUE</b> if the driver is in the I/O path for the file system volume, <b>FALSE</b> otherwise. 


### -field DriverNameLength

Caller-supplied length of the driver name string. 


### -field DriverName

Caller-supplied Unicode string containing the name of the driver. 


## -remarks



To perform this query, call <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a> or <a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a>, passing FileFsDriverPathInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_FS_DRIVER_PATH_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

This information is file system-independent. Thus the call to <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a> or <a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a> does not cause an IRP to be sent to the file system. 

No specific access rights are required to query this information. Thus this information is available as long as the volume is accessed through an open handle to the volume itself, or to a file or directory on the volume. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a> or <a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a> must be at least <b>sizeof</b> (FILE_FS_DRIVER_PATH_INFORMATION). 

This structure must be aligned on a LONGLONG (8-byte) boundary. 




## -see-also

<a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>



 

 


