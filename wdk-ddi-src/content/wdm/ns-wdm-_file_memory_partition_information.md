---
UID: NS:wdm._FILE_MEMORY_PARTITION_INFORMATION
title: _FILE_MEMORY_PARTITION_INFORMATION (wdm.h)
description: Stores information about memory partition. This structure is used by the ZwSetInformationFile function.
tech.root: ifsk
ms.date: 06/11/2021
author: lorihollasch
keywords: ["FILE_MEMORY_PARTITION_INFORMATION structure"]
ms.keywords: "*PFILE_MEMORY_PARTITION_INFORMATION, FILE_MEMORY_PARTITION_INFORMATION, FILE_MEMORY_PARTITION_INFORMATION structure [Kernel-Mode Driver Architecture], _FILE_MEMORY_PARTITION_INFORMATION, ifsk._file_memory_partition_information, wdm/FILE_MEMORY_PARTITION_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.typenames: FILE_MEMORY_PARTITION_INFORMATION, *PFILE_MEMORY_PARTITION_INFORMATION
f1_keywords:
 - _FILE_MEMORY_PARTITION_INFORMATION
 - wdm/_FILE_MEMORY_PARTITION_INFORMATION
 - PFILE_MEMORY_PARTITION_INFORMATION
 - wdm/PFILE_MEMORY_PARTITION_INFORMATION
 - FILE_MEMORY_PARTITION_INFORMATION
 - wdm/FILE_MEMORY_PARTITION_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _FILE_MEMORY_PARTITION_INFORMATION
 - PFILE_MEMORY_PARTITION_INFORMATION
 - FILE_MEMORY_PARTITION_INFORMATION
---

# _FILE_MEMORY_PARTITION_INFORMATION structure

## -description

Stores information about memory partition. This structure is used by the **ZwSetInformationFile** function.

## -struct-fields

### -field OwnerPartitionHandle

Handle to the specified partition.

### -field Flags

### -field Flags.DUMMYSTRUCTNAME

### -field Flags.DUMMYSTRUCTNAME.NoCrossPartitionAccess

Determines whether cross-partition access is allowed.

### -field Flags.DUMMYSTRUCTNAME.Spare

### -field Flags.AllFlags

Bitwise of all flags.
