---
UID: NS:ntddk._FILE_VALID_DATA_LENGTH_INFORMATION
title: "_FILE_VALID_DATA_LENGTH_INFORMATION"
author: windows-driver-content
description: The FILE_VALID_DATA_LENGTH_INFORMATION structure is used as an argument to ZwSetInformationFile.
old-location: kernel\file_valid_data_length_information.htm
tech.root: kernel
ms.assetid: 78badbac-9f77-4911-a42b-c0421be47f20
ms.date: 04/30/2018
ms.keywords: "*PFILE_VALID_DATA_LENGTH_INFORMATION, FILE_VALID_DATA_LENGTH_INFORMATION, FILE_VALID_DATA_LENGTH_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_VALID_DATA_LENGTH_INFORMATION, PFILE_VALID_DATA_LENGTH_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_VALID_DATA_LENGTH_INFORMATION, kernel.file_valid_data_length_information, kstruct_b_4db45831-d238-4274-b0f3-f1945e187eb5.xml, ntddk/FILE_VALID_DATA_LENGTH_INFORMATION, ntddk/PFILE_VALID_DATA_LENGTH_INFORMATION"
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows XP and later versions of the Windows operating system.
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
-	Ntddk.h
api_name:
-	FILE_VALID_DATA_LENGTH_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_VALID_DATA_LENGTH_INFORMATION, *PFILE_VALID_DATA_LENGTH_INFORMATION
---

# _FILE_VALID_DATA_LENGTH_INFORMATION structure


## -description


The <b>FILE_VALID_DATA_LENGTH_INFORMATION</b> structure is used as an argument to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>.


## -struct-fields




### -field ValidDataLength

Specifies the new valid data length for the file. This parameter must be a positive value that is greater than the current valid data length, but less than or equal to the current file size. 


## -remarks



The <b>FILE_VALID_DATA_LENGTH_INFORMATION</b> structure is used to set a new valid data length for a file on an NTFS volume. A file's <i>valid data length</i> is the length, in bytes, of the data that has been written to the file. This <i>valid data</i> extends from the beginning of the file to the last byte in the file that has not been zeroed or left uninitialized. 

Setting this information requires FILE_WRITE_DATA access to the file. In addition, nonadministrators and remote users must have <b>SeManageVolumePrivilege</b> (SE_MANAGE_VOLUME_PRIVILEGE) for the volume on which the file resides. 

File system filter drivers can find it useful to set a valid data length in the following scenarios: 

<ul>
<li>
When writing raw clusters directly to disk through a hardware channel. This allows the filter driver to inform the file system that this range contains valid data that can be returned to the user. 

</li>
<li>
When creating large files where performance is an issue. This avoids the time it takes to fill the file with zeros when the file is created or extended. 

</li>
<li>
When remotely extending a file and writing to disk on a served-metadata cluster file system. 

</li>
</ul>
The size of the <i>FileInformation</i> buffer passed to <b>ZwSetInformationFile</b> must be at least <b>sizeof</b>(<b>FILE_VALID_DATA_LENGTH_INFORMATION</b>). 

This structure must be aligned on a LONGLONG (8-byte) boundary. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>
 

 

