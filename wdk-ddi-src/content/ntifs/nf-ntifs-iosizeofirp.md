---
UID: NF:ntifs.IoSizeOfIrp
title: IoSizeOfIrp macro (ntifs.h)
description: The IoSizeOfIrp routine determines the size in bytes for an IRP, given the number of stack locations in the IRP.
old-location: kernel\iosizeofirp.htm
tech.root: kernel
ms.assetid: b7a6f903-a986-464a-9c9c-12d44f9abf6a
ms.date: 04/30/2018
keywords: ["IoSizeOfIrp macro"]
ms.keywords: IoSizeOfIrp, IoSizeOfIrp routine [Kernel-Mode Driver Architecture], k104_7c08c9ff-7731-462e-acb8-3793f85a84c2.xml, kernel.iosizeofirp, wdm/IoSizeOfIrp
f1_keywords:
 - "ntifs/IoSizeOfIrp"
 - "IoSizeOfIrp"
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- IoSizeOfIrp
targetos: Windows
req.typenames: 
---

# IoSizeOfIrp macro


## -description


The <b>IoSizeOfIrp</b> routine determines the size in bytes for an IRP, given the number of stack locations in the IRP.


## -parameters




### -param StackSize [in]

Specifies the number of stack locations for the IRP. 

## -returns
**IoSizeOfIrp** returns the size, in bytes, of the IRP.

## -remarks



The input <i>StackSize</i> value is either that of the next-lower driver's device object or one more than that value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp">IoAllocateIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iomakeassociatedirp">IoMakeAssociatedIrp</a>
 

 

