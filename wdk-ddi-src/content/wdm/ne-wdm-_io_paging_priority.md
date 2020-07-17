---
UID: NE:wdm._IO_PAGING_PRIORITY
title: _IO_PAGING_PRIORITY (wdm.h)
description: The IO_PAGING_PRIORITY enumeration describes the priority value for a paging I/O IRP.
old-location: kernel\io_paging_priority.htm
tech.root: kernel
ms.assetid: c96d1c81-429f-46de-b56c-6424734ccd7a
ms.date: 04/30/2018
keywords: ["_IO_PAGING_PRIORITY enumeration"]
ms.keywords: IO_PAGING_PRIORITY, IO_PAGING_PRIORITY enumeration [Kernel-Mode Driver Architecture], IoPagingPriorityHigh, IoPagingPriorityInvalid, IoPagingPriorityNormal, IoPagingPriorityReserved1, IoPagingPriorityReserved2, _IO_PAGING_PRIORITY, kernel.io_paging_priority, sysenum_8e021ebd-f26a-4749-8e76-c540af5dfae1.xml, wdm/IO_PAGING_PRIORITY, wdm/IoPagingPriorityHigh, wdm/IoPagingPriorityInvalid, wdm/IoPagingPriorityNormal, wdm/IoPagingPriorityReserved1, wdm/IoPagingPriorityReserved2
f1_keywords:
 - "wdm/IO_PAGING_PRIORITY"
 - "IO_PAGING_PRIORITY"
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
- wdm.h
api_name:
- IO_PAGING_PRIORITY
product:
- Windows
targetos: Windows
req.typenames: IO_PAGING_PRIORITY
---

# _IO_PAGING_PRIORITY enumeration


## -description


The <b>IO_PAGING_PRIORITY</b> enumeration describes the priority value for a paging I/O IRP.


## -enum-fields




### -field IoPagingPriorityInvalid

The IRP is not a paging I/O IRP.


### -field IoPagingPriorityNormal

The associated IRP has a normal priority level for paging I/O. 


### -field IoPagingPriorityHigh

The associated IRP has a high priority level for paging I/O. 


### -field IoPagingPriorityReserved1

Reserved for system use.


### -field IoPagingPriorityReserved2

Reserved for system use. 


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iogetpagingiopriority">IoGetPagingIoPriority</a> routine returns an <b>IO_PAGING_PRIORITY</b> value to indicate the priority value of a paging I/O IRP. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iogetpagingiopriority">IoGetPagingIoPriority</a>
 

 

