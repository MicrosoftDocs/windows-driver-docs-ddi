---
UID: NS:wdm._FILE_STANDARD_INFORMATION
title: _FILE_STANDARD_INFORMATION (wdm.h)
description: The FILE_STANDARD_INFORMATION structure is used as an argument to routines that query or set file information.
old-location: kernel\file_standard_information.htm
tech.root: kernel
ms.assetid: 9ff7efec-4844-4abf-89c2-472afc959697
ms.date: 04/30/2018
keywords: ["_FILE_STANDARD_INFORMATION structure"]
ms.keywords: "*PFILE_STANDARD_INFORMATION, FILE_STANDARD_INFORMATION, FILE_STANDARD_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_STANDARD_INFORMATION, PFILE_STANDARD_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_STANDARD_INFORMATION, kernel.file_standard_information, kstruct_b_86abcab8-11e5-45de-983a-e78c6cb40a93.xml, wdm/FILE_STANDARD_INFORMATION, wdm/PFILE_STANDARD_INFORMATION"
f1_keywords:
 - "wdm/FILE_STANDARD_INFORMATION"
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
- wdm.h
api_name:
- FILE_STANDARD_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_STANDARD_INFORMATION, *PFILE_STANDARD_INFORMATION
---

# _FILE_STANDARD_INFORMATION structure


## -description


The <b>FILE_STANDARD_INFORMATION</b> structure is used as an argument to routines that query or set file information.


## -struct-fields




### -field AllocationSize

The file allocation size in bytes. Usually, this value is a multiple of the sector or cluster size of the underlying physical device. 


### -field EndOfFile

The end of file location as a byte offset.


### -field NumberOfLinks

The number of hard links to the file.


### -field DeletePending

The delete pending status. <b>TRUE</b> indicates that a file deletion has been requested.


### -field Directory

The file directory status. <b>TRUE</b> indicates the file object represents a directory. 


## -remarks



<b>EndOfFile</b> specifies the byte offset to the end of the file. Because this value is zero-based, it actually refers to the first free byte in the file; that is, it is the offset to the byte immediately following the last valid byte in the file. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>
 

 

