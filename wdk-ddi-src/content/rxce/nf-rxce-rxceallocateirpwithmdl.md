---
UID: NF:rxce.RxCeAllocateIrpWithMDL
title: RxCeAllocateIrpWithMDL function (rxce.h)
description: RxCeAllocateIrpWithMDL allocates an IRP and associates it with an existing memory descriptor list.
old-location: ifsk\rxceallocateirpwithmdl.htm
tech.root: ifsk
ms.assetid: ffc6332b-7daa-4b23-8cf4-6077f7d1d40a
ms.date: 04/16/2018
keywords: ["RxCeAllocateIrpWithMDL function"]
ms.keywords: RxCeAllocateIrpWithMDL, RxCeAllocateIrpWithMDL function [Installable File System Drivers], ifsk.rxceallocateirpwithmdl, rxce/RxCeAllocateIrpWithMDL, rxref_8cb4dfd0-5789-4359-ad9f-bd1a9d460eb3.xml
req.header: rxce.h
req.include-header: Rxce.h
req.target-type: Desktop
req.target-min-winverclnt: The RxCeAllocateIrpWithMDL routine is only available on Windows XP.
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RxCeAllocateIrpWithMDL
 - rxce/RxCeAllocateIrpWithMDL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rxce.h
api_name:
 - RxCeAllocateIrpWithMDL
---

# RxCeAllocateIrpWithMDL function


## -description

<b>RxCeAllocateIrpWithMDL</b> allocates an IRP and associates it with an existing memory descriptor list.

## -parameters

### -param StackSize 

[in]
The stack size to allocate for the IRP.

### -param ChargeQuota 

[in]
This parameter should be set to <b>FALSE</b> by intermediate drivers. This can be set to <b>TRUE</b> only by highest-level drivers that are called in the context of the thread that originates the I/O request for which the driver is allocating another IRP.

### -param Buffer 

[in]
A pointer to the buffer that contains the memory descriptor list to be associated with this IRP.

## -returns

<b>RxCeAllocateIrpWithMDL</b> returns a pointer to the IRP on success or a <b>NULL</b> pointer on error.

## -remarks

The goal of <b>RxCeAllocateIrpWithMDL</b> is to allow easier debugging of IRPs that are issued to other components and then stall. IRPs issued using <b>RxCeAllocateIrpWithMDL</b> are queued to a global list of IRPs maintained by RDBSS. Thus, when an RX_CONTEXT is waiting for a send completion, it is possible to walk the global list to find the IRP that is waiting in the transport.

An IRP allocated with an associated memory descriptor list allocated with <b>RxCeAllocateIrpWithMDL</b> should be freed when the IRP is completed using <b>RxCeFreeIrp</b>.

<b>IoAllocateIrp</b> automatically initializes the IRP's members and inserts the IRP into a global list of IRPs maintained by RDBSS. If memory for the MDL to be associated with the IRP cannot be allocated, then the IRP that was created is freed and <b>RxCeAllocateIrpWithMDL</b> returns a <b>NULL</b> pointer indicating failure.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>



<a href="/windows-hardware/drivers/ddi/rxce/nf-rxce-rxcefreeirp">RxCeFreeIrp</a>