---
UID: NS:wdm._DMA_ADAPTER_INFO_V1
title: "_DMA_ADAPTER_INFO_V1" (wdm.h)
description: The DMA_ADAPTER_INFO_V1 structure describes the capabilities of the system DMA controller that is represented by an adapter object.
old-location: kernel\dma_adapter_info_v1.htm
tech.root: kernel
ms.assetid: 5BB089B8-4384-450D-BC81-9D9D068CF4EB
ms.date: 04/30/2018
ms.keywords: "*PDMA_ADAPTER_INFO_V1, DMA_ADAPTER_INFO_V1, DMA_ADAPTER_INFO_V1 structure [Kernel-Mode Driver Architecture], PDMA_ADAPTER_INFO_V1, PDMA_ADAPTER_INFO_V1 structure pointer [Kernel-Mode Driver Architecture], _DMA_ADAPTER_INFO_V1, kernel.dma_adapter_info_v1, wdm/DMA_ADAPTER_INFO_V1, wdm/PDMA_ADAPTER_INFO_V1"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
-	DMA_ADAPTER_INFO_V1
product:
- Windows
targetos: Windows
req.typenames: DMA_ADAPTER_INFO_V1, *PDMA_ADAPTER_INFO_V1
---

# _DMA_ADAPTER_INFO_V1 structure


## -description



The <b>DMA_ADAPTER_INFO_V1</b> structure describes the capabilities of the system DMA controller that is represented by an adapter object.




## -struct-fields




### -field ReadDmaCounterAvailable

Whether the counter value in each DMA channel can be read. This member is <b>TRUE</b> if the counter can be read, and is <b>FALSE</b> if it cannot be read.


### -field ScatterGatherLimit

The maximum number of elements in a scatter/gather list that the DMA controller can process in a single scatter/gather DMA transfer.


### -field DmaAddressWidth

The memory address width, in bits, of the DMA controller. The width is expressed as the number of bits in a DMA address. If the DMA address width is less than the memory address width, the platform hardware drives the remaining, high-order memory address bits to zero during a DMA transfer.


### -field Flags

A set of flags that describe the capabilities of the DMA adapter. No flags are currently defined for this member.


### -field MinimumTransferUnit

The size, in bytes, of the minimum transfer unit. The number of bytes specified by an element in a scatter/gather list must be an integer multiple of the minimum transfer unit.


## -remarks



The <b>V1</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450993">DMA_ADAPTER_INFO</a> structure is a structure of type <b>DMA_ADAPTER_INFO_V1</b>.

A driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh451121">GetDmaAdapterInfo</a> to obtain information about the hardware capabilities of a system DMA channel. <b>GetDmaAdapterInfo</b> writes this information into the <b>V1</b> member of a caller-supplied <b>DMA_ADAPTER_INFO</b> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450993">DMA_ADAPTER_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451121">GetDmaAdapterInfo</a>
 

 

