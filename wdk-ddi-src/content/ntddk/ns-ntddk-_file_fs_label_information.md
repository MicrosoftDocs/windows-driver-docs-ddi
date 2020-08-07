---
UID: NS:ntddk._FILE_FS_LABEL_INFORMATION
title: _FILE_FS_LABEL_INFORMATION (ntddk.h)
description: The FILE_FS_LABEL_INFORMATION structure is used to set the label for a file system volume.
old-location: ifsk\file_fs_label_information.htm
tech.root: ifsk
ms.assetid: cad48019-3777-4f1c-9872-c837604f47bc
ms.date: 04/16/2018
keywords: ["FILE_FS_LABEL_INFORMATION structure"]
ms.keywords: "*PFILE_FS_LABEL_INFORMATION, FILE_FS_LABEL_INFORMATION, FILE_FS_LABEL_INFORMATION structure [Installable File System Drivers], PFILE_FS_LABEL_INFORMATION, PFILE_FS_LABEL_INFORMATION structure pointer [Installable File System Drivers], _FILE_FS_LABEL_INFORMATION, fileinformationstructures_ac9398f2-2488-43b4-8fdb-76ae1f84066c.xml, ifsk.file_fs_label_information, ntddk/FILE_FS_LABEL_INFORMATION, ntddk/PFILE_FS_LABEL_INFORMATION"
f1_keywords:
 - "ntddk/FILE_FS_LABEL_INFORMATION"
 - "FILE_FS_LABEL_INFORMATION"
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
- FILE_FS_LABEL_INFORMATION
targetos: Windows
req.typenames: FILE_FS_LABEL_INFORMATION, *PFILE_FS_LABEL_INFORMATION
---

# _FILE_FS_LABEL_INFORMATION structure


## -description


The FILE_FS_LABEL_INFORMATION structure is used to set the label for a file system volume. 


## -struct-fields




### -field VolumeLabelLength

Length, in bytes, of the name for the volume. 


### -field VolumeLabel

Name for the volume. 


## -remarks



This information can be set in either of the following ways: 

<ul>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetvolumeinformation">FltSetVolumeInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567112">ZwSetVolumeInformationFile</a>, passing FileFsLabelInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_FS_LABEL_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code IRP_MJ_SET_VOLUME_INFORMATION. 

</li>
</ul>
FILE_WRITE_DATA access to the volume is required to set this information. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetvolumeinformation">FltSetVolumeInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567112">ZwSetVolumeInformationFile</a> must be at least <b>sizeof</b> (FILE_FS_LABEL_INFORMATION). 

This structure must be aligned on a LONG (4-byte) boundary. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetvolumeinformation">FltSetVolumeInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-volume-information">IRP_MJ_SET_VOLUME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567112">ZwSetVolumeInformationFile</a>
 

 

