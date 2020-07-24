---
UID: NF:rxprocs.RxMapSystemBuffer
title: RxMapSystemBuffer function (rxprocs.h)
description: RxMapSystemBuffer returns the system buffer address from the IRP.
old-location: ifsk\rxmapsystembuffer.htm
tech.root: ifsk
ms.assetid: dc549e51-2f25-45b5-925f-3481294e0b35
ms.date: 04/16/2018
keywords: ["RxMapSystemBuffer function"]
ms.keywords: RxMapSystemBuffer, RxMapSystemBuffer function [Installable File System Drivers], ifsk.rxmapsystembuffer, rxprocs/RxMapSystemBuffer, rxref_b9222b0a-25ca-4ad4-95b9-b9651c625a39.xml
f1_keywords:
 - "rxprocs/RxMapSystemBuffer"
 - "RxMapSystemBuffer"
req.header: rxprocs.h
req.include-header: Rxcontx.h, Rxprocs.h
req.target-type: Desktop
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rxprocs.h
api_name:
- RxMapSystemBuffer
targetos: Windows
req.typenames: 
---

# RxMapSystemBuffer function


## -description


<b>RxMapSystemBuffer</b> returns the system buffer address from the IRP. 


## -parameters




### -param RxContext [in]

A pointer to the RX_CONTEXT structure for this request.


### -param Irp [in]

A pointer to the IRP for this request.


## -returns



<b>RxMapSystemBuffer </b>returns a mapped address pointer. 




## -remarks



The <b>RxMapSystemBuffer</b> routine checks that <b>Irp->MdlAddress</b> is not <b>NULL</b> and returns the <b>Irp->AssociatedIrp.SystemBuffer</b> when this is the case. 

On retail builds, <b>RxMapSystemBuffer</b> will call <b>MmGetSystemAddressForMdlSafe</b> to return the MDL from the IRP if <b>Irp->MdlAddress</b> is <b>NULL</b>. On checked builds, <b>RxMapSystemBuffer</b> causes the system to ASSERT if <b>Irp->MdlAddress</b> is <b>NULL</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetSystemAddressForMdlSafe</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxcontx/ns-rxcontx-_rx_context">RX_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/lowio/nf-lowio-rxlowiocompletion">RxLowIoCompletion</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/lowio/nf-lowio-rxlowiogetbufferaddress">RxLowIoGetBufferAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/rxnewmapuserbuffer">RxNewMapUserBuffer</a>
 

 

