---
UID: NS:ntddk._MM_COPY_ADDRESS
title: _MM_COPY_ADDRESS (ntddk.h)
description: The MM_COPY_ADDRESS structure contains either a virtual memory address or a physical memory address.
old-location: kernel\mm_copy_address.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["MM_COPY_ADDRESS structure"]
ms.keywords: "*PMMCOPY_ADDRESS, MM_COPY_ADDRESS, MM_COPY_ADDRESS structure [Kernel-Mode Driver Architecture], PMM_COPY_ADDRESS, PMM_COPY_ADDRESS structure pointer [Kernel-Mode Driver Architecture], _MM_COPY_ADDRESS, kernel.mm_copy_address, ntddk/MM_COPY_ADDRESS, ntddk/PMM_COPY_ADDRESS"
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.1.
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
req.typenames: MM_COPY_ADDRESS, *PMMCOPY_ADDRESS
f1_keywords:
 - _MM_COPY_ADDRESS
 - ntddk/_MM_COPY_ADDRESS
 - PMMCOPY_ADDRESS
 - ntddk/PMMCOPY_ADDRESS
 - MM_COPY_ADDRESS
 - ntddk/MM_COPY_ADDRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddk.h
api_name:
 - _MM_COPY_ADDRESS
 - PMMCOPY_ADDRESS
 - MM_COPY_ADDRESS
---

# _MM_COPY_ADDRESS structure


## -description

The <b>MM_COPY_ADDRESS</b> structure contains either a virtual memory address or a physical memory address.

## -struct-fields

### -field VirtualAddress

### -field PhysicalAddress

 




#### - ( unnamed union )

Either a virtual address or a physical address.



#### VirtualAddress

A virtual memory address.



#### PhysicalAddress

A physical memory address.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmcopymemory">MmCopyMemory</a> routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmcopymemory">MmCopyMemory</a>

