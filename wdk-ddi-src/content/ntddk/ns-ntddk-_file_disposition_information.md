---
UID: NS:ntddk._FILE_DISPOSITION_INFORMATION
title: _FILE_DISPOSITION_INFORMATION (ntddk.h)
description: The FILE_DISPOSITION_INFORMATION structure is used as an argument to the ZwSetInformationFile routine.
old-location: kernel\file_disposition_information.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["FILE_DISPOSITION_INFORMATION structure"]
ms.keywords: "*PFILE_DISPOSITION_INFORMATION, FILE_DISPOSITION_INFORMATION, FILE_DISPOSITION_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_DISPOSITION_INFORMATION, PFILE_DISPOSITION_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_DISPOSITION_INFORMATION, kernel.file_disposition_information, kstruct_b_3796aa61-042a-435d-bfa9-c77c6a0dff98.xml, ntddk/FILE_DISPOSITION_INFORMATION, ntddk/PFILE_DISPOSITION_INFORMATION"
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
targetos: Windows
req.typenames: FILE_DISPOSITION_INFORMATION, *PFILE_DISPOSITION_INFORMATION
f1_keywords:
 - _FILE_DISPOSITION_INFORMATION
 - ntddk/_FILE_DISPOSITION_INFORMATION
 - PFILE_DISPOSITION_INFORMATION
 - ntddk/PFILE_DISPOSITION_INFORMATION
 - FILE_DISPOSITION_INFORMATION
 - ntddk/FILE_DISPOSITION_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddk.h
api_name:
 - FILE_DISPOSITION_INFORMATION
---

# _FILE_DISPOSITION_INFORMATION structure


## -description

The <b>FILE_DISPOSITION_INFORMATION</b> structure is used as an argument to the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a> routine.

## -struct-fields

### -field DeleteFile

Indicates whether the operating system file should delete the file when the file is closed. Set this member to <b>TRUE</b> to delete the file when it is closed. Otherwise, set to <b>FALSE</b>. Setting this member to <b>FALSE</b> has no effect if the handle was opened with FILE_FLAG_DELETE_ON_CLOSE.

## -remarks

The caller must have DELETE access to a given file in order to call <b>ZwSetInformationFile</b> with <b>DeleteFile</b> set to <b>TRUE</b> in this structure. Subsequently, the only legal operation by such a caller is to close the open file handle. 

A file marked for deletion is not actually deleted until all open handles for the file object have been closed and the link count for the file is zero.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>
