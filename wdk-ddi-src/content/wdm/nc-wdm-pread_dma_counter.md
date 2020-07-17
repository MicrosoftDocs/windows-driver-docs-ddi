---
UID: NC:wdm.PREAD_DMA_COUNTER
title: PREAD_DMA_COUNTER (wdm.h)
description: The ReadDmaCounter routine returns the number of bytes remaining to be transferred during the current subordinate DMA operation.
old-location: kernel\readdmacounter.htm
tech.root: kernel
ms.assetid: c5a49bbd-ddb7-4faa-934a-d5846273d648
ms.date: 04/30/2018
keywords: ["PREAD_DMA_COUNTER callback function"]
ms.keywords: PREAD_DMA_COUNTER, PREAD_DMA_COUNTER callback, ReadDmaCounter, ReadDmaCounter callback function [Kernel-Mode Driver Architecture], kdma_81865501-ca01-4f66-b2a9-da0493d72589.xml, kernel.readdmacounter, wdm/ReadDmaCounter
f1_keywords:
 - "wdm/ReadDmaCounter"
 - "ReadDmaCounter"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wdm.h
api_name:
- ReadDmaCounter
product:
- Windows
targetos: Windows
req.typenames: 
---

# PREAD_DMA_COUNTER callback function


## -description


The <b>ReadDmaCounter</b> routine returns the number of bytes remaining to be transferred during the current subordinate DMA operation.


## -parameters




### -param DmaAdapter [in]

Pointer to the adapter object previously returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> representing the system DMA controller channel currently in use. 


## -returns



<b>ReadDmaCounter</b> returns the number of bytes remaining to be transferred in the current DMA operation.




## -remarks



<b>ReadDmaCounter</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>.

<b>ReadDmaCounter</b> can be called only by drivers of subordinate DMA devices. Usually, the caller is the driver of a subordinate device that uses a system DMA controller's autoinitialize mode. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_common_buffer">AllocateCommonBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers">FlushAdapterBuffers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer">MapTransfer</a>
 

 

