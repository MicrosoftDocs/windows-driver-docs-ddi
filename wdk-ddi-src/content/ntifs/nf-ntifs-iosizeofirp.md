---
UID: NF:ntifs.IoSizeOfIrp
title: IoSizeOfIrp macro (ntifs.h)
description: Learn more about the IoSizeOfIrp routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["IoSizeOfIrp macro"]
ms.keywords: IoSizeOfIrp, kernel.iosizeofirp, wdm/IoSizeOfIrp
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 2000
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IoSizeOfIrp
 - ntifs/IoSizeOfIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - IoSizeOfIrp
---

# IoSizeOfIrp macro (ntifs.h)

## -description

The **IoSizeOfIrp** routine determines the size in bytes for an IRP, given the number of stack locations in the IRP.

## -parameters

### -param StackSize

[in] Specifies the number of stack locations for the IRP.

## -remarks

**IoSizeOfIrp** returns the size, in bytes, of the IRP.

The input **StackSize** value is either that of the next-lower driver's device object or one more than that value.

## -see-also

[**IoAllocateIrp**](../wdm/nf-wdm-ioallocateirp.md)

[**IoMakeAssociatedIrp**](../ntddk/nf-ntddk-iomakeassociatedirp.md)
