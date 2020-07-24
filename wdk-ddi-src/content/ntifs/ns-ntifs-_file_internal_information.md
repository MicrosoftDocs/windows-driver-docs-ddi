---
UID: NS:ntifs._FILE_INTERNAL_INFORMATION
title: _FILE_INTERNAL_INFORMATION (ntifs.h)
description: The FILE_INTERNAL_INFORMATION structure is used to query for the file system's 8-byte file reference number for a file.
old-location: ifsk\file_internal_information.htm
tech.root: ifsk
ms.assetid: b82bc943-d9f0-451f-a8ac-f89936e866eb
ms.date: 04/16/2018
keywords: ["_FILE_INTERNAL_INFORMATION structure"]
ms.keywords: "*PFILE_INTERNAL_INFORMATION, FILE_INTERNAL_INFORMATION, FILE_INTERNAL_INFORMATION structure [Installable File System Drivers], PFILE_INTERNAL_INFORMATION, PFILE_INTERNAL_INFORMATION structure pointer [Installable File System Drivers], _FILE_INTERNAL_INFORMATION, fileinformationstructures_7be724e0-06ec-4555-bcce-14926b7d92df.xml, ifsk.file_internal_information, ntifs/FILE_INTERNAL_INFORMATION, ntifs/PFILE_INTERNAL_INFORMATION"
f1_keywords:
 - "ntifs/FILE_INTERNAL_INFORMATION"
 - "FILE_INTERNAL_INFORMATION"
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
- FILE_INTERNAL_INFORMATION
targetos: Windows
req.typenames: FILE_INTERNAL_INFORMATION, *PFILE_INTERNAL_INFORMATION
---

# _FILE_INTERNAL_INFORMATION structure


## -description


The FILE_INTERNAL_INFORMATION structure is used to query for the file system's 8-byte file reference number for a file. 


## -struct-fields




### -field IndexNumber

The 8-byte file reference number for the file. This number is assigned by the file system and is file-system-specific. (Note that this is not the same as the 16-byte "file object ID" that was added to NTFS for Microsoft Windows 2000.) 


## -remarks



This information can be queried in either of the following ways: 

<ul>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryinformationfile">FltQueryInformationFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>, passing FileInternalInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_INTERNAL_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-information">IRP_MJ_QUERY_INFORMATION</a>. 

</li>
</ul>
No specific access rights are required to query this information. 

The <b>IndexNumber</b> member of the FILE_INTERNAL_INFORMATION structure is the same as the <b>FileId</b> member of the FILE_ID_BOTH_DIR_INFORMATION and FILE_ID_FULL_DIR_INFORMATION structures. 

File reference numbers, also called file IDs, are guaranteed to be unique only within a static file system. They are not guaranteed to be unique over time, because file systems are free to reuse them. Nor are they guaranteed to remain constant. For example, the FAT file system generates the file reference number for a file from the byte offset of the file's directory entry record (DIRENT) on the disk. Defragmentation can change this byte offset. Thus a FAT file reference number can change over time. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryinformationfile">FltQueryInformationFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a> must be at least <b>sizeof</b> (FILE_INTERNAL_INFORMATION). 

This structure must be aligned on a LONGLONG (8-byte) boundary. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_id_both_dir_information">FILE_ID_BOTH_DIR_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_id_full_dir_information">FILE_ID_FULL_DIR_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_objectid_information">FILE_OBJECTID_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryinformationfile">FltQueryInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>
 

 

