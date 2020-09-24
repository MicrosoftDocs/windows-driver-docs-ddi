---
UID: NS:ntifs._FILE_ZERO_DATA_INFORMATION
title: _FILE_ZERO_DATA_INFORMATION (ntifs.h)
description: Contains a range of a file to set to zeros.
old-location: ifsk\file_zero_data_information.htm
tech.root: ifsk
ms.assetid: 64F1A14F-2152-4095-A594-B2AE3B87C638
ms.date: 04/16/2018
keywords: ["FILE_ZERO_DATA_INFORMATION structure"]
ms.keywords: "*PFILE_ZERO_DATA_INFORMATION, FILE_ZERO_DATA_INFORMATION, FILE_ZERO_DATA_INFORMATION structure [Installable File System Drivers], PFILE_ZERO_DATA_INFORMATION, PFILE_ZERO_DATA_INFORMATION structure pointer [Installable File System Drivers], _FILE_ZERO_DATA_INFORMATION, ifsk.file_zero_data_information, ntifs/FILE_ZERO_DATA_INFORMATION, ntifs/PFILE_ZERO_DATA_INFORMATION"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
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
req.typenames: FILE_ZERO_DATA_INFORMATION, *PFILE_ZERO_DATA_INFORMATION
f1_keywords:
 - _FILE_ZERO_DATA_INFORMATION
 - ntifs/_FILE_ZERO_DATA_INFORMATION
 - PFILE_ZERO_DATA_INFORMATION
 - ntifs/PFILE_ZERO_DATA_INFORMATION
 - FILE_ZERO_DATA_INFORMATION
 - ntifs/FILE_ZERO_DATA_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FILE_ZERO_DATA_INFORMATION
---

# _FILE_ZERO_DATA_INFORMATION structure


## -description

Contains a range of a file to set to zeros. This structure is used by the 
<a href="/windows-hardware/drivers/ifs/fsctl-set-zero-data">FSCTL_SET_ZERO_DATA</a> control code.

## -struct-fields

### -field FileOffset

The file offset of the start of the range to set to zeros, in bytes.

### -field BeyondFinalZero

The byte offset of the first byte beyond the last zeroed byte.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_zero_data_information_ex">FILE_ZERO_DATA_INFORMATION_EX</a>



<a href="/windows-hardware/drivers/ifs/fsctl-set-zero-data">FSCTL_SET_ZERO_DATA</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfscontrolfile">FltFsControlFile</a>