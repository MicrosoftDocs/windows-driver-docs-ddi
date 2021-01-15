---
UID: NC:wdm.PGET_DMA_ALIGNMENT
title: PGET_DMA_ALIGNMENT (wdm.h)
description: The GetDmaAlignment routine returns the alignment requirements of the DMA system.
old-location: kernel\getdmaalignment.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PGET_DMA_ALIGNMENT callback function"]
ms.keywords: GetDmaAlignment, GetDmaAlignment callback function [Kernel-Mode Driver Architecture], PGET_DMA_ALIGNMENT, PGET_DMA_ALIGNMENT callback, kdma_3b830c2d-6c3d-477c-b781-c9d1a7dbe5bf.xml, kernel.getdmaalignment, wdm/GetDmaAlignment
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with  Windows 2000.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PGET_DMA_ALIGNMENT
 - wdm/PGET_DMA_ALIGNMENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - PGET_DMA_ALIGNMENT
---

# PGET_DMA_ALIGNMENT callback function


## -description

The <b>GetDmaAlignment</b> routine returns the alignment requirements of the DMA system.

## -parameters

### -param DmaAdapter 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure returned by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.

## -returns

<b>GetDmaAlignment</b> returns the alignment requirements, in bytes, of the DMA system.  The starting address and length of DMA buffers must be a multiple of this value.

## -remarks

<b>GetDmaAlignment</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>.

A driver can call this routine to determine alignment requirements for DMA buffers it allocates. The returned value should be used to set the <b>AlignmentRequirement</b> field in the device object. A driver may need to increase this value because of additional hardware device restrictions.  For more information, see <a href="/windows-hardware/drivers/kernel/initializing-a-device-object">Initializing a Device Object</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>

