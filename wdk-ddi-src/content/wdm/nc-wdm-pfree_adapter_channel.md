---
UID: NC:wdm.PFREE_ADAPTER_CHANNEL
title: PFREE_ADAPTER_CHANNEL (wdm.h)
description: The FreeAdapterChannel routine releases the system DMA controller when a driver has completed all DMA operations necessary to satisfy the current IRP.
old-location: kernel\freeadapterchannel.htm
tech.root: kernel
ms.assetid: 916531dd-4768-436a-910c-07d49924ac48
ms.date: 04/30/2018
ms.keywords: FreeAdapterChannel, FreeAdapterChannel callback function [Kernel-Mode Driver Architecture], PFREE_ADAPTER_CHANNEL, PFREE_ADAPTER_CHANNEL callback, kdma_f48025a6-96a2-4bdd-8b48-6c939bdf738b.xml, kernel.freeadapterchannel, wdm/FreeAdapterChannel
ms.topic: callback
f1_keywords:
 - "wdm/FreeAdapterChannel"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch, IrqlDispatch(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wdm.h
api_name:
- FreeAdapterChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFREE_ADAPTER_CHANNEL callback function


## -description


The <b>FreeAdapterChannel</b> routine releases the system DMA controller when a driver has completed all DMA operations necessary to satisfy the current IRP.


## -parameters




### -param DmaAdapter [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>  structure returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


## -remarks



<b>FreeAdapterChannel</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>.

After a driver has transferred all the data and called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers">FlushAdapterBuffers</a>, it calls <b>FreeAdapterChannel</b> to release the system DMA controller that was previously allocated with a call to <b>AllocateAdapterChannel</b>.

<b>FreeAdapterChannel</b> frees any map registers that were allocated by an earlier call to <b>AllocateAdapterChannel</b>. A driver calls this routine only if its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a> routine returns <b>KeepObject</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel">AllocateAdapterChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers">FlushAdapterBuffers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pfree_map_registers">FreeMapRegisters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer">MapTransfer</a>
 

 

