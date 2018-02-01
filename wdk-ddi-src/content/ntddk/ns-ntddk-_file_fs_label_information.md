---
UID: NS:ntddk._FILE_FS_LABEL_INFORMATION
title: "_FILE_FS_LABEL_INFORMATION"
author: windows-driver-content
description: The FILE_FS_LABEL_INFORMATION structure is used to set the label for a file system volume.
old-location: ifsk\file_fs_label_information.htm
old-project: ifsk
ms.assetid: cad48019-3777-4f1c-9872-c837604f47bc
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PFILE_FS_LABEL_INFORMATION, ifsk.file_fs_label_information, FILE_FS_LABEL_INFORMATION structure [Installable File System Drivers], _FILE_FS_LABEL_INFORMATION, ntddk/FILE_FS_LABEL_INFORMATION, ntddk/PFILE_FS_LABEL_INFORMATION, fileinformationstructures_ac9398f2-2488-43b4-8fdb-76ae1f84066c.xml, *PFILE_FS_LABEL_INFORMATION, PFILE_FS_LABEL_INFORMATION structure pointer [Installable File System Drivers], FILE_FS_LABEL_INFORMATION
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
-	FILE_FS_LABEL_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PFILE_FS_LABEL_INFORMATION, FILE_FS_LABEL_INFORMATION"
---

# _FILE_FS_LABEL_INFORMATION structure


## -description


The FILE_FS_LABEL_INFORMATION structure is used to set the label for a file system volume. 


## -syntax


````
typedef struct _FILE_FS_LABEL_INFORMATION {
  ULONG VolumeLabelLength;
  WCHAR VolumeLabel[1];
} FILE_FS_LABEL_INFORMATION, *PFILE_FS_LABEL_INFORMATION;
````


## -struct-fields




### -field VolumeLabelLength

Length, in bytes, of the name for the volume. 


### -field VolumeLabel

Name for the volume. 


## -remarks


This information can be set in either of the following ways: 
<ul>
<li>
Call <a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a> or <a href="..\ntifs\nf-ntifs-zwsetvolumeinformationfile.md">ZwSetVolumeInformationFile</a>, passing FileFsLabelInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_FS_LABEL_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code IRP_MJ_SET_VOLUME_INFORMATION. 

</li>
</ul>FILE_WRITE_DATA access to the volume is required to set this information. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a> or <a href="..\ntifs\nf-ntifs-zwsetvolumeinformationfile.md">ZwSetVolumeInformationFile</a> must be at least <b>sizeof</b> (FILE_FS_LABEL_INFORMATION). 

This structure must be aligned on a LONG (4-byte) boundary. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549415">IRP_MJ_SET_VOLUME_INFORMATION</a>

<a href="..\ntifs\nf-ntifs-zwsetvolumeinformationfile.md">ZwSetVolumeInformationFile</a>

<a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_FS_LABEL_INFORMATION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

