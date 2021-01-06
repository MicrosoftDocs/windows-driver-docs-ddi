---
UID: NS:ntifs._FILE_REPARSE_POINT_INFORMATION
title: _FILE_REPARSE_POINT_INFORMATION (ntifs.h)
description: The FILE_REPARSE_POINT_INFORMATION structure is used to query for information about a reparse point.
old-location: ifsk\file_reparse_point_information.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FILE_REPARSE_POINT_INFORMATION structure"]
ms.keywords: "*PFILE_REPARSE_POINT_INFORMATION, FILE_REPARSE_POINT_INFORMATION, FILE_REPARSE_POINT_INFORMATION structure [Installable File System Drivers], PFILE_REPARSE_POINT_INFORMATION, PFILE_REPARSE_POINT_INFORMATION structure pointer [Installable File System Drivers], _FILE_REPARSE_POINT_INFORMATION, fileinformationstructures_5e939a71-0fcc-41e9-be0f-c2c1b5327239.xml, ifsk.file_reparse_point_information, ntifs/FILE_REPARSE_POINT_INFORMATION, ntifs/PFILE_REPARSE_POINT_INFORMATION"
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
targetos: Windows
req.typenames: FILE_REPARSE_POINT_INFORMATION, *PFILE_REPARSE_POINT_INFORMATION
f1_keywords:
 - _FILE_REPARSE_POINT_INFORMATION
 - ntifs/_FILE_REPARSE_POINT_INFORMATION
 - PFILE_REPARSE_POINT_INFORMATION
 - ntifs/PFILE_REPARSE_POINT_INFORMATION
 - FILE_REPARSE_POINT_INFORMATION
 - ntifs/FILE_REPARSE_POINT_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FILE_REPARSE_POINT_INFORMATION
---

# _FILE_REPARSE_POINT_INFORMATION structure


## -description

The FILE_REPARSE_POINT_INFORMATION structure is used to query for information about a reparse point.

## -struct-fields

### -field FileReference

The 8-byte file reference number for the file. This number is generated and assigned to the file by the NTFS file system. (Note that the <i>FileId</i> is not the same as the 16-byte "file object ID" that was added to NTFS for Microsoft Windows 2000.)

### -field Tag

Reparse point tag. The <b>ReparseTag</b> member indicates the structure of the user-defined reparse data. For more information about reparse point tags, see the Microsoft Windows SDK documentation.

## -remarks

This information can be queried in either of the following ways: 

<ul>
<li>
Call <a href="/previous-versions/ff567047(v=vs.85)">ZwQueryDirectoryFile</a>, passing FileReparsePointInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_REPARSE_POINT_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code <a href="/windows-hardware/drivers/ifs/irp-mj-directory-control">IRP_MJ_DIRECTORY_CONTROL</a> and minor function code IRP_MN_QUERY_DIRECTORY. 

</li>
</ul>
For more information about reparse points, see the Windows SDK documentation. 

No specific access rights are required to query this information. 

This structure must be LONG-aligned.

## -see-also

<a href="/windows-hardware/drivers/ifs/irp-mj-directory-control">IRP_MJ_DIRECTORY_CONTROL</a>



<a href="/previous-versions/ff567047(v=vs.85)">ZwQueryDirectoryFile</a>
