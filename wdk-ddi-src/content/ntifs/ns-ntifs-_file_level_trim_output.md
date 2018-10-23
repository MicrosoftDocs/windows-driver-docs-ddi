---
UID: NS:ntifs._FILE_LEVEL_TRIM_OUTPUT
title: "_FILE_LEVEL_TRIM_OUTPUT"
author: windows-driver-content
description: The FILE_LEVEL_TRIM_OUTPUT structure contains the results of a trim operation performed by an FSCTL_FILE_LEVEL_TRIM request.
old-location: ifsk\file_level_trim_output.htm
tech.root: ifsk
ms.assetid: 28CCE967-E752-4E0E-94D9-3A4243266684
ms.date: 04/16/2018
ms.keywords: "*PFILE_LEVEL_TRIM_OUTPUT, FILE_LEVEL_TRIM_OUTPUT, FILE_LEVEL_TRIM_OUTPUT structure [Installable File System Drivers], FILE_LEVEL_TRIM_RANGE_OUTPUT, FILE_LEVEL_TRIM_RANGE_OUTPUT structure [Installable File System Drivers], PFILE_LEVEL_TRIM_RANGE_OUTPUT, PFILE_LEVEL_TRIM_RANGE_OUTPUT structure pointer [Installable File System Drivers], _FILE_LEVEL_TRIM_OUTPUT, ifsk.file_level_trim_output, ntifs/FILE_LEVEL_TRIM_RANGE, ntifs/PFILE_LEVEL_TRIM_RANGE_OUTPUT"
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
-	ntifs.h
api_name:
-	FILE_LEVEL_TRIM_RANGE_OUTPUT
product:
- Windows
targetos: Windows
req.typenames: FILE_LEVEL_TRIM_OUTPUT, *PFILE_LEVEL_TRIM_OUTPUT
---

# _FILE_LEVEL_TRIM_OUTPUT structure


## -description


The <b>FILE_LEVEL_TRIM_OUTPUT</b> structure contains the results of a trim operation performed by an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451098">FSCTL_FILE_LEVEL_TRIM</a> request.


## -struct-fields




### -field NumRangesProcessed

The number or trim ranges processed.


## -remarks



This structure is optionally included as the output buffer for an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451098">FSCTL_FILE_LEVEL_TRIM</a> request. <b>NumRangesProcessed</b> indicates how many ranges of the in the array given in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406398">FILE_LEVEL_TRIM</a> were processed.

All trim ranges in the array in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406398">FILE_LEVEL_TRIM</a> were successfully processed if  <b>NumRangesProcessed</b> is equivalent to the <b>NumRanges</b> member of <b>FILE_LEVEL_TRIM</b>. Otherwise, the value in <b>NumRangesProcessed</b> is the starting index of the trim ranges that were not processed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451098">FSCTL_FILE_LEVEL_TRIM</a>
 

 

