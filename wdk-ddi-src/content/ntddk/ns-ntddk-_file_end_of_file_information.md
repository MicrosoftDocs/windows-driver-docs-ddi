---
UID: NS:ntddk._FILE_END_OF_FILE_INFORMATION
title: "_FILE_END_OF_FILE_INFORMATION" (ntddk.h)
description: The FILE_END_OF_FILE_INFORMATION structure is used as an argument to the ZwSetInformationFile routine.
old-location: kernel\file_end_of_file_information.htm
tech.root: kernel
ms.assetid: 9af172d9-2309-4731-82bf-55ec99c475a6
ms.date: 04/30/2018
ms.keywords: "*PFILE_END_OF_FILE_INFORMATION, FILE_END_OF_FILE_INFORMATION, FILE_END_OF_FILE_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_END_OF_FILE_INFORMATION, PFILE_END_OF_FILE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_END_OF_FILE_INFORMATION, kernel.file_end_of_file_information, kstruct_b_6c41bbd0-64be-4765-b79c-09e2dd86fa6f.xml, ntddk/FILE_END_OF_FILE_INFORMATION, ntddk/PFILE_END_OF_FILE_INFORMATION"
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
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
-	Ntddk.h
api_name:
-	FILE_END_OF_FILE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_END_OF_FILE_INFORMATION, *PFILE_END_OF_FILE_INFORMATION
---

# _FILE_END_OF_FILE_INFORMATION structure


## -description


The <b>FILE_END_OF_FILE_INFORMATION</b> structure is used as an argument to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a> routine.


## -struct-fields




### -field EndOfFile

The absolute new end of file position as a byte offset from the start of the file. 


## -remarks



<b>EndOfFile</b> specifies the byte offset to the end of the file. Because this value is zero-based, it actually refers to the first free byte in the file: that is, it is the offset to the byte immediately following the last valid byte in the file. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>
 

 

