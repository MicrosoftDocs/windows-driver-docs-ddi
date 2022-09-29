---
UID: NE:ntifs._MEMORY_INFORMATION_CLASS
title: MEMORY_INFORMATION_CLASS (ntifs.h)
description: Defines classes of memory information that can be retrieved by using the ZwQueryVirtualMemory function.
old-location: kernel\memory_information_class.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["MEMORY_INFORMATION_CLASS enumeration"]
ms.keywords: MEMORY_INFORMATION_CLASS, MEMORY_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], MemoryBasicInformation, _MEMORY_INFORMATION_CLASS, kernel.memory_information_class, ntifs/MEMORY_INFORMATION_CLASS, ntifs/MemoryBasicInformation
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
 - _MEMORY_INFORMATION_CLASS
 - MEMORY_INFORMATION_CLASS
---

# MEMORY_INFORMATION_CLASS enumeration

## -description

Defines classes of memory information that can be retrieved by using the [**ZwQueryVirtualMemory**](nf-ntifs-zwqueryvirtualmemory.md) function.

## -enum-fields

### -field MemoryBasicInformation

Memory information described in the [**MEMORY_BASIC_INFORMATION**](ns-ntifs-_memory_basic_information.md) structure will be retrieved.

## -remarks

Currently, only the **MemoryBasicInformation** value is supported for use with the [**ZwQueryVirtualMemory**](nf-ntifs-zwqueryvirtualmemory.md) routine.

## -see-also

[**ZwQueryVirtualMemory**](nf-ntifs-zwqueryvirtualmemory.md)
