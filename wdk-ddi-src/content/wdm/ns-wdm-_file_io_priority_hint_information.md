---
UID: NS:wdm._FILE_IO_PRIORITY_HINT_INFORMATION
title: _FILE_IO_PRIORITY_HINT_INFORMATION (wdm.h)
description: The FILE_IO_PRIORITY_HINT_INFORMATION structure is used by the ZwQueryInformationFile and ZwSetInformationFile routines to query and set the default IRP priority hint for requests on the specified file handle.
old-location: kernel\file_io_priority_hint_information.htm
tech.root: kernel
ms.assetid: 55f88d42-8411-49f0-bc40-7ccc268b3cc5
ms.date: 04/30/2018
keywords: ["FILE_IO_PRIORITY_HINT_INFORMATION structure"]
ms.keywords: "*PFILE_IO_PRIORITY_HINT_INFORMATION, FILE_IO_PRIORITY_HINT_INFORMATION, FILE_IO_PRIORITY_HINT_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_IO_PRIORITY_HINT_INFORMATION, PFILE_IO_PRIORITY_HINT_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_IO_PRIORITY_HINT_INFORMATION, kernel.file_io_priority_hint_information, kstruct_b_babd0cbe-1870-4d71-86c5-06c438691202.xml, wdm/FILE_IO_PRIORITY_HINT_INFORMATION, wdm/PFILE_IO_PRIORITY_HINT_INFORMATION"
f1_keywords:
 - "wdm/FILE_IO_PRIORITY_HINT_INFORMATION"
 - "FILE_IO_PRIORITY_HINT_INFORMATION"
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
- Wdm.h
api_name:
- FILE_IO_PRIORITY_HINT_INFORMATION
targetos: Windows
req.typenames: FILE_IO_PRIORITY_HINT_INFORMATION, *PFILE_IO_PRIORITY_HINT_INFORMATION
---

# _FILE_IO_PRIORITY_HINT_INFORMATION structure


## -description


The <b>FILE_IO_PRIORITY_HINT_INFORMATION</b> structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a> routines to query and set the default IRP <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-irp-priority-hints">priority hint</a> for requests on the specified file handle.


## -struct-fields




### -field PriorityHint

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_priority_hint">IO_PRIORITY_HINT</a> value that indicates the priority hint for a file handle.


## -remarks



For more information about priority hints, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-irp-priority-hints">Using IRP Priority Hints</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_priority_hint">IO_PRIORITY_HINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>
 

 

