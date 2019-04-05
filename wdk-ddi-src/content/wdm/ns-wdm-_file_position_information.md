---
UID: NS:wdm._FILE_POSITION_INFORMATION
title: _FILE_POSITION_INFORMATION (wdm.h)
description: The FILE_POSITION_INFORMATION structure is used as an argument to routines that query or set file information.
old-location: kernel\file_position_information.htm
tech.root: kernel
ms.assetid: 04f01faf-599e-4c62-82ce-c147b4820c8f
ms.date: 04/30/2018
ms.keywords: "*PFILE_POSITION_INFORMATION, FILE_POSITION_INFORMATION, FILE_POSITION_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_POSITION_INFORMATION, PFILE_POSITION_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_POSITION_INFORMATION, kernel.file_position_information, kstruct_b_5edd5ea9-9229-4764-86aa-24054a1ec9b9.xml, wdm/FILE_POSITION_INFORMATION, wdm/PFILE_POSITION_INFORMATION"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
- Wdm.h
api_name:
- FILE_POSITION_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_POSITION_INFORMATION, *PFILE_POSITION_INFORMATION
---

# _FILE_POSITION_INFORMATION structure


## -description


The <b>FILE_POSITION_INFORMATION</b> structure is used as an argument to routines that query or set file information.


## -struct-fields




### -field CurrentByteOffset

The byte offset of the current file pointer.


## -remarks



FILE_READ_DATA or FILE_WRITE_DATA access to the file is required to change this information about the file, and the file must be opened for synchronous I/O.

If the file was opened or created with the FILE_NO_INTERMEDIATE_BUFFERING option, the value of <b>CurrentByteOffset</b> must be an integral multiple of the sector size of the underlying device.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>
 

 

