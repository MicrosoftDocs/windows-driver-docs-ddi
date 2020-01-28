---
UID: NS:ntifs._FILE_ALLOCATION_INFORMATION
title: _FILE_ALLOCATION_INFORMATION (ntifs.h)
description: The FILE_ALLOCATION_INFORMATION structure is used to set the allocation size for a file.
old-location: ifsk\file_allocation_information.htm
tech.root: ifsk
ms.assetid: 52c62e52-3bf7-40eb-80ff-df14c50c86e1
ms.date: 04/16/2018
ms.keywords: "*PFILE_ALLOCATION_INFORMATION, FILE_ALLOCATION_INFORMATION, FILE_ALLOCATION_INFORMATION structure [Installable File System Drivers], PFILE_ALLOCATION_INFORMATION, PFILE_ALLOCATION_INFORMATION structure pointer [Installable File System Drivers], _FILE_ALLOCATION_INFORMATION, fileinformationstructures_79d60e3b-f403-46d8-b600-62aeddcb88e0.xml, ifsk.file_allocation_information, ntifs/FILE_ALLOCATION_INFORMATION, ntifs/PFILE_ALLOCATION_INFORMATION"
f1_keywords:
 - "ntifs/FILE_ALLOCATION_INFORMATION"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- FILE_ALLOCATION_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_ALLOCATION_INFORMATION, *PFILE_ALLOCATION_INFORMATION
---

# _FILE_ALLOCATION_INFORMATION structure


## -description


The FILE_ALLOCATION_INFORMATION structure is used to set the allocation size for a file. 


## -struct-fields




### -field AllocationSize

File allocation size, in bytes. Usually this value is a multiple of the sector or cluster size of the underlying physical device. 


## -remarks



This operation can be performed in either of the following ways: 

<ul>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetinformationfile">FltSetInformationFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>, passing FileAllocationInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_ALLOCATION_INFORMATION-structured buffer as the value of <i>FileInformation</i>. The <i>FileHandle</i> parameter specifies the file whose allocation size is to be set. 

</li>
<li>
Create an IRP with major function code IRP_MJ_SET_INFORMATION. 

</li>
</ul>
This operation is valid only for files. It is undefined for directories. 

File system minifilters must use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetinformationfile">FltSetInformationFile</a>, not <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>, to set the allocation size for a file. 

FILE_WRITE_DATA access is required to set this information. 

A file's allocation size and end-of-file position are independent of each other, with the following exception: The end-of-file position must always be less than or equal to the allocation size. If the allocation size is set to a value that is less than the end-of-file position, the end-of-file position is automatically adjusted to match the allocation size. 

The size of the <i>FileInformation</i> buffer passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetinformationfile">FltSetInformationFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a> must be >= <b>sizeof</b>(FILE_ALLOCATION_INFORMATION). 

This structure must be aligned on a LONGLONG (8-byte) boundary. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_end_of_file_information">FILE_END_OF_FILE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetinformationfile">FltSetInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-information">IRP_MJ_SET_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>
 

 

