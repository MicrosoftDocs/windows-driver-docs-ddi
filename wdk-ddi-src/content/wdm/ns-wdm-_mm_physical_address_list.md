---
UID: NS:wdm._MM_PHYSICAL_ADDRESS_LIST
title: "_MM_PHYSICAL_ADDRESS_LIST"
author: windows-driver-content
description: The MM_PHYSICAL_ADDRESS_LIST structure specifies a range of physical addresses.
old-location: kernel\mm_physical_address_list.htm
tech.root: kernel
ms.assetid: D653607A-7C37-408D-AD19-B4A8988CDACE
ms.date: 04/30/2018
ms.keywords: "*PMM_PHYSICAL_ADDRESS_LIST, MM_PHYSICAL_ADDRESS_LIST, MM_PHYSICAL_ADDRESS_LIST structure [Kernel-Mode Driver Architecture], PMM_PHYSICAL_ADDRESS_LIST, PMM_PHYSICAL_ADDRESS_LIST structure pointer [Kernel-Mode Driver Architecture], _MM_PHYSICAL_ADDRESS_LIST, kernel.mm_physical_address_list, wdm/MM_PHYSICAL_ADDRESS_LIST, wdm/PMM_PHYSICAL_ADDRESS_LIST"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	MM_PHYSICAL_ADDRESS_LIST
product:
- Windows
targetos: Windows
req.typenames: MM_PHYSICAL_ADDRESS_LIST, *PMM_PHYSICAL_ADDRESS_LIST
---

# _MM_PHYSICAL_ADDRESS_LIST structure


## -description


The <b>MM_PHYSICAL_ADDRESS_LIST</b> structure specifies a range of physical addresses.


## -struct-fields




### -field PhysicalAddress

The starting physical address of the range. This address must be aligned to a page boundary in physical memory.


### -field NumberOfBytes

The number of bytes in the range. This member must be nonzero and an integer multiple of the memory page size.


## -remarks



The first parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/jj206443">MmAllocateMdlForIoSpace</a> routine is a pointer to an array of <b>MM_PHYSICAL_ADDRESS_LIST</b> structures.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj206443">MmAllocateMdlForIoSpace</a>
 

 

