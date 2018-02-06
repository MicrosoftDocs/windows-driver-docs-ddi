---
UID: NS:ntifs._FILE_FS_DRIVER_PATH_INFORMATION
title: "_FILE_FS_DRIVER_PATH_INFORMATION"
author: windows-driver-content
description: The FILE_FS_DRIVER_PATH_INFORMATION structure is used to query whether a given driver is in the I/O path for a file system volume.
old-location: ifsk\file_fs_driver_path_information.htm
old-project: ifsk
ms.assetid: 6149765b-cd2c-44f5-aa72-f4755e0b034c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "_FILE_FS_DRIVER_PATH_INFORMATION, FILE_FS_DRIVER_PATH_INFORMATION, fileinformationstructures_9d09c9ee-18a0-4230-af6b-0cddadbac901.xml, PFILE_FS_DRIVER_PATH_INFORMATION structure pointer [Installable File System Drivers], ifsk.file_fs_driver_path_information, FILE_FS_DRIVER_PATH_INFORMATION structure [Installable File System Drivers], PFILE_FS_DRIVER_PATH_INFORMATION, *PFILE_FS_DRIVER_PATH_INFORMATION, ntifs/FILE_FS_DRIVER_PATH_INFORMATION, ntifs/PFILE_FS_DRIVER_PATH_INFORMATION"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_FS_DRIVER_PATH_INFORMATION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

