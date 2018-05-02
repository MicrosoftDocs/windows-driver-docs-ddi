---
UID: NS:wdm._DMA_ADAPTER
title: "_DMA_ADAPTER"
author: windows-driver-content
description: The DMA_ADAPTER structure describes a system-defined interface to a DMA controller for a given device. A driver calls IoGetDmaAdapter to obtain this structure.
old-location: kernel\dma_adapter.htm
old-project: kernel
ms.assetid: 08cd5b10-725e-4a36-b70d-42a831b79372
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PADAPTER_OBJECT, *PDMA_ADAPTER, DMA_ADAPTER, DMA_ADAPTER structure [Kernel-Mode Driver Architecture], PDMA_ADAPTER, PDMA_ADAPTER structure pointer [Kernel-Mode Driver Architecture], _DMA_ADAPTER, kernel.dma_adapter, kstruct_a_030ef4da-75e2-4427-baf6-cb9a5eb194cf.xml, wdm/DMA_ADAPTER, wdm/PDMA_ADAPTER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	DMA_ADAPTER
product: Windows
targetos: Windows
req.typenames: "*PADAPTER_OBJECT, DMA_ADAPTER, *PDMA_ADAPTER"
---

# _DMA_ADAPTER structure


## -description


The <b>DMA_ADAPTER</b> structure describes a system-defined interface to a DMA controller for a given device. A driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> to obtain this structure.


## -struct-fields




### -field Version

Specifies the version of this structure. Version 3 of the <b>DMA_ADAPTER</b> structure is available starting with Windows 8. For versions 1 and 2 of this structure, this member is set to the value 1. For more information, see the following Remarks section.


### -field Size

Specifies the size, in bytes, of this structure.


### -field DmaOperations

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a> structure that contains pointers to DMA adapter functions. The version of the <b>DMA_OPERATIONS</b> structure that this member points to is determined by the version of the <b>DMA_ADAPTER</b> structure. Thus, for version 1 of the <b>DMA_ADAPTER</b> structure, <i>DmaOperations</i> points to version 1 of the <b>DMA_OPERATIONS</b> structure, and so on. For more information about structure versions, see the following Remarks section.


## -remarks



Drivers for devices that use DMA to transfer data use this structure to obtain the addresses of functions that enable use of a DMA controller. Usually, drivers obtain this structure by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine. Drivers can also obtain this structure by querying for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540707">BUS_INTERFACE_STANDARD</a> interface.

<div class="alert"><b>Note</b>  When the <b>IoGetDmaAdapter</b> routine returns a pointer to version 1 or version 2 of the <b>DMA_ADAPTER</b> structure, this routine always sets the <b>Version</b> member of this structure to 1. Thus, the caller cannot use the <b>Version</b> member to distinguish between versions 1 and 2 of the <b>DMA_ADAPTER</b> structure. For more information about how to determine the version of a <b>DMA_ADAPTER</b> structure that is returned by this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540707">BUS_INTERFACE_STANDARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>
 

 

