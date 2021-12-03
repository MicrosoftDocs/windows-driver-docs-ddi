---
UID: NS:ntifs._FILE_REPARSE_POINT_INFORMATION
title: FILE_REPARSE_POINT_INFORMATION (ntifs.h)
description: The FILE_REPARSE_POINT_INFORMATION structure is used to query for information about a reparse point.
old-location: ifsk\file_reparse_point_information.htm
tech.root: ifsk
ms.date: 12/01/2021
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
 - _FILE_REPARSE_POINT_INFORMATION
 - PFILE_REPARSE_POINT_INFORMATION
 - FILE_REPARSE_POINT_INFORMATION
---

# FILE_REPARSE_POINT_INFORMATION structure

## -description

The **FILE_REPARSE_POINT_INFORMATION** structure is used to query for information about a reparse point.

## -struct-fields

### -field FileReference

The 8-byte file reference number for the file. NTFS generates this number and assigns it to the file automatically when the file is created.

### -field Tag

The reparse point tag that indicates the structure of the reparse data. See [About reparse points](/windows-hardware/drivers/ifs/reparse-points) for more information about reparse point tags.

## -remarks

This information can be queried in either of the following ways:

* Call [**ZwQueryDirectoryFileEx**](nf-ntifs-zwquerydirectoryfileex.md), passing **FileReparsePointInformation** as the value of **FileInformationClass** and passing a caller-allocated, **FILE_REPARSE_POINT_INFORMATION**-structured buffer as the value of **FileInformation**.

* Create an IRP with major function code [**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control) and minor function code IRP_MN_QUERY_DIRECTORY.

No specific access rights are required to query this information.

This structure must be LONG-aligned.

See [About reparse points](/windows-hardware/drivers/ifs/reparse-points) for more information about reparse points.

## -see-also

[**FltTagFileEx**](../fltkernel/nf-fltkernel-flttagfileex.md)

[**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control)

[**ZwQueryDirectoryFileEx**](nf-ntifs-zwquerydirectoryfileex.md)
