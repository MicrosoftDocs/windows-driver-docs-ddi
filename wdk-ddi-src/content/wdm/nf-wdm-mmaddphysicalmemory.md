---
UID: NF:wdm.MmAddPhysicalMemory
tech.root: kernel
title: MmAddPhysicalMemory
ms.date: 10/20/2023
targetos: Windows
description: The MmAddPhysicalMemory function adds a range of physical memory to the system.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: <= APC_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr:
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - MmAddPhysicalMemory
f1_keywords:
 - MmAddPhysicalMemory
 - wdm/MmAddPhysicalMemory
dev_langs:
 - c++
---

## -description

The **MmAddPhysicalMemory** function adds a range of physical memory to the system.

## -parameters

### -param StartAddress [in]

Supplies the starting physical address of the range to be added.

### -param NumberOfBytes [in]

Supplies the size, in bytes, of the memory range to be added.

## -returns

Returns an NTSTATUS code.

## -remarks

Memory added by **MmAddPhysicalMemory** can be immediately used to satisfy memory allocations from arbitrary threads.
