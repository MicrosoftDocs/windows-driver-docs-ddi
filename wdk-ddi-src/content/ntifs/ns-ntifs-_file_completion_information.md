---
UID: NS:ntifs._FILE_COMPLETION_INFORMATION
title: _FILE_COMPLETION_INFORMATION (ntifs.h)
description: The FILE_COMPLETION_INFORMATION structure contains the port handle and key for an I/O completion port created for a file handle.
old-location: ifsk\file_completion_information.htm
tech.root: ifsk
ms.assetid: 8C3C1A62-A838-436E-B8CC-ACE70FEAE8EA
ms.date: 04/16/2018
ms.keywords: "*PFILE_COMPLETION_INFORMATION, FILE_COMPLETION_INFORMATION, FILE_COMPLETION_INFORMATION structure [Installable File System Drivers], PFILE_COMPLETION_INFORMATION, PFILE_COMPLETION_INFORMATION structure pointer [Installable File System Drivers], _FILE_COMPLETION_INFORMATION, ifsk.file_completion_information, ntifs/FILE_COMPLETION_INFORMATION, ntifs/PFILE_COMPLETION_INFORMATION"
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows 8.1.
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
- FILE_COMPLETION_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_COMPLETION_INFORMATION, *PFILE_COMPLETION_INFORMATION
---

# _FILE_COMPLETION_INFORMATION structure


## -description


The <b>FILE_COMPLETION_INFORMATION</b> structure contains the port handle and key for an I/O completion port created for a file handle.


## -struct-fields




### -field Port

The handle to the completion port created for an associated file handle.


### -field Key

An custom defined value which is included in every I/O completion packet for <b>Port</b>.


## -remarks



The <b>FILE_COMPLETION_INFORMATION</b> structure is used to replace the completion information for a port handle set in <b>Port</b>. Completion information is replaced with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a> routine with the <i>FileInformationClass</i> parameter set to <b>FileReplaceCompletionInformation</b>.   The <b>Port</b> and <b>Key</b> members of <b>FILE_COMPLETION_INFORMATION</b> are set to their new values. To remove an existing completion port for a file handle, <b>Port</b> is set to NULL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>
 

 

