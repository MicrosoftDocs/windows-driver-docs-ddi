---
UID: NS:wdm._DMA_ADAPTER_INFO
title: "_DMA_ADAPTER_INFO" (wdm.h)
description: The DMA_ADAPTER_INFO structure is a container for a DMA_ADAPTER_INFO_XXX structure that describes the capabilities of a system DMA controller.
old-location: kernel\dma_adapter_info.htm
tech.root: kernel
ms.assetid: 181C3421-85D1-457E-85A5-42C84AE41BD6
ms.date: 04/30/2018
ms.keywords: "*PDMA_ADAPTER_INFO, DMA_ADAPTER_INFO, DMA_ADAPTER_INFO structure [Kernel-Mode Driver Architecture], PDMA_ADAPTER_INFO, PDMA_ADAPTER_INFO structure pointer [Kernel-Mode Driver Architecture], _DMA_ADAPTER_INFO, kernel.dma_adapter_info, wdm/DMA_ADAPTER_INFO, wdm/PDMA_ADAPTER_INFO"
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
-	DMA_ADAPTER_INFO
product:
- Windows
targetos: Windows
req.typenames: DMA_ADAPTER_INFO, *PDMA_ADAPTER_INFO
---

# _DMA_ADAPTER_INFO structure


## -description


The <b>DMA_ADAPTER_INFO</b> structure is a container for a <b>DMA_ADAPTER_INFO_</b><i>XXX</i> structure that describes the capabilities of a system DMA controller.


## -struct-fields




### -field Version

The version number of the <b>DMA_ADAPTER_INFO_</b><i>XXX</i> structure that follows this member. For a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450995">DMA_ADAPTER_INFO_V1</a> structure, set this member to DMA_ADAPTER_INFO_VERSION1 before calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451121">GetDmaAdapterInfo</a> routine.


### -field V1

The capabilities of the bus-master DMA device or the system DMA controller. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450995">DMA_ADAPTER_INFO_V1</a>.


## -remarks



A device driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451121">GetDmaAdapterInfo</a> routine to obtain a <b>DMA_ADAPTER_INFO</b> structure that describes the capabilities of a DMA controller.

The unnamed union in this structure contains a <b>DMA_ADAPTER_INFO_</b><i>XXX</i> structure. The <b>Version</b> member indicates which version of the <b>DMA_ADAPTER_INFO_</b><i>XXX</i> structure is contained in the union. Currently, only version 1 is supported.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450995">DMA_ADAPTER_INFO_V1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451121">GetDmaAdapterInfo</a>
 

 

