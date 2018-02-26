---
UID: NS:wdm._MM_PHYSICAL_ADDRESS_LIST
title: "_MM_PHYSICAL_ADDRESS_LIST"
author: windows-driver-content
description: The MM_PHYSICAL_ADDRESS_LIST structure specifies a range of physical addresses.
old-location: kernel\mm_physical_address_list.htm
old-project: kernel
ms.assetid: D653607A-7C37-408D-AD19-B4A8988CDACE
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PMM_PHYSICAL_ADDRESS_LIST, ,, A, C, D, E, H, I, L, M, MM_PHYSICAL_ADDRESS_LIST, MM_PHYSICAL_ADDRESS_LIST structure [Kernel-Mode Driver Architecture], P, PMM_PHYSICAL_ADDRESS_LIST, PMM_PHYSICAL_ADDRESS_LIST structure pointer [Kernel-Mode Driver Architecture], R, S, T, Y, _, _MM_PHYSICAL_ADDRESS_LIST, kernel.mm_physical_address_list, wdm/MM_PHYSICAL_ADDRESS_LIST, wdm/PMM_PHYSICAL_ADDRESS_LIST"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	MM_PHYSICAL_ADDRESS_LIST
product: Windows
targetos: Windows
req.typenames: MM_PHYSICAL_ADDRESS_LIST, *PMM_PHYSICAL_ADDRESS_LIST
req.product: Windows 10 or later.
---

# _MM_PHYSICAL_ADDRESS_LIST structure


## -description


The <b>MM_PHYSICAL_ADDRESS_LIST</b> structure specifies a range of physical addresses.


## -syntax


````
typedef struct _MM_PHYSICAL_ADDRESS_LIST {
  PHYSICAL_ADDRESS PhysicalAddress;
  SIZE_T           NumberOfBytes;
} MM_PHYSICAL_ADDRESS_LIST, *PMM_PHYSICAL_ADDRESS_LIST;
````


## -struct-fields




### -field PhysicalAddress

The starting physical address of the range. This address must be aligned to a page boundary in physical memory.


### -field NumberOfBytes

The number of bytes in the range. This member must be nonzero and an integer multiple of the memory page size.


## -remarks



The first parameter to the <a href="..\wdm\nf-wdm-mmallocatemdlforiospace.md">MmAllocateMdlForIoSpace</a> routine is a pointer to an array of <b>MM_PHYSICAL_ADDRESS_LIST</b> structures.




## -see-also

<a href="..\wdm\nf-wdm-mmallocatemdlforiospace.md">MmAllocateMdlForIoSpace</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MM_PHYSICAL_ADDRESS_LIST structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

