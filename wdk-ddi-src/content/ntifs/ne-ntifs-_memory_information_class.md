---
UID: NE:ntifs._MEMORY_INFORMATION_CLASS
title: _MEMORY_INFORMATION_CLASS (ntifs.h)
description: Defines classes of memory information that can be retrieved by using the ZwQueryVirtualMemory function.
old-location: kernel\memory_information_class.htm
tech.root: kernel
ms.assetid: 7E3B531F-935C-41D6-94F7-DB18F82B9109
ms.date: 04/30/2018
keywords: ["MEMORY_INFORMATION_CLASS enumeration"]
ms.keywords: MEMORY_INFORMATION_CLASS, MEMORY_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], MemoryBasicInformation, _MEMORY_INFORMATION_CLASS, kernel.memory_information_class, ntifs/MEMORY_INFORMATION_CLASS, ntifs/MemoryBasicInformation
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
req.typenames: MEMORY_INFORMATION_CLASS
f1_keywords:
 - _MEMORY_INFORMATION_CLASS
 - ntifs/_MEMORY_INFORMATION_CLASS
 - MEMORY_INFORMATION_CLASS
 - ntifs/MEMORY_INFORMATION_CLASS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - MEMORY_INFORMATION_CLASS
---

# _MEMORY_INFORMATION_CLASS enumeration


## -description

Defines classes of memory information that can be retrieved by using the  <a href="/previous-versions/dn957455(v=vs.85)">ZwQueryVirtualMemory</a> function.

## -enum-fields

### -field MemoryBasicInformation

Memory information described in the <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_memory_basic_information">MEMORY_BASIC_INFORMATION</a> structure will be retrieved.

## -remarks

Currently, only the <b>MemoryBasicInformation</b> value is supported for use with the <a href="/previous-versions/dn957455(v=vs.85)">ZwQueryVirtualMemory</a> routine.

## -see-also

<a href="/previous-versions/dn957455(v=vs.85)">ZwQueryVirtualMemory</a>