---
UID: NS:wdm._DMA_ADAPTER
title: DMA_ADAPTER (wdm.h)
description: The DMA_ADAPTER structure describes a system-defined interface to a DMA controller for a given device. A driver calls IoGetDmaAdapter to obtain this structure.
tech.root: kernel
ms.date: 12/15/2022
keywords: ["DMA_ADAPTER structure"]
ms.keywords: "*PADAPTER_OBJECT, *PDMA_ADAPTER, DMA_ADAPTER, DMA_ADAPTER structure [Kernel-Mode Driver Architecture], PDMA_ADAPTER, PDMA_ADAPTER structure pointer [Kernel-Mode Driver Architecture], _DMA_ADAPTER, kernel.dma_adapter, kstruct_a_030ef4da-75e2-4427-baf6-cb9a5eb194cf.xml, wdm/DMA_ADAPTER, wdm/PDMA_ADAPTER"
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
targetos: Windows
req.typenames: "*PADAPTER_OBJECT, DMA_ADAPTER, *PDMA_ADAPTER"
f1_keywords:
 - _DMA_ADAPTER
 - wdm/_DMA_ADAPTER
 - PADAPTER_OBJECT
 - wdm/PADAPTER_OBJECT
 - DMA_ADAPTER
 - wdm/DMA_ADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _DMA_ADAPTER
 - PADAPTER_OBJECT
 - DMA_ADAPTER
---

## -description

The **DMA_ADAPTER** structure describes a system-defined interface to a DMA controller for a given device. A driver calls [IoGetDmaAdapter](/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter) to obtain this structure.

## -struct-fields

### -field Version

Specifies the version of this structure. Version 3 of the **DMA_ADAPTER** structure is available starting with Windows 8. For versions 1 and 2 of this structure, this member is set to the value 1. For more information, see the following Remarks section.

### -field Size

Specifies the size, in bytes, of this structure.

### -field DmaOperations

Pointer to a [**DMA_OPERATIONS**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations) structure that contains pointers to DMA adapter functions. The version of the **DMA_OPERATIONS** structure that this member points to is determined by the version of the **DMA_ADAPTER** structure. Thus, for version 1 of the **DMA_ADAPTER** structure, *DmaOperations* points to version 1 of the **DMA_OPERATIONS** structure, and so on. For more information about structure versions, see the following Remarks section.

## -remarks

Drivers for devices that use DMA to transfer data use this structure to obtain the addresses of functions that enable use of a DMA controller. Usually, drivers obtain this structure by calling the [IoGetDmaAdapter](/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter) routine. Drivers can also obtain this structure by querying for the [**BUS_INTERFACE_STANDARD**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_bus_interface_standard) interface.

When the **IoGetDmaAdapter** routine returns a pointer to version 1 or version 2 of the **DMA_ADAPTER** structure, this routine always sets the **Version** member of this structure to 1. Thus, the caller cannot use the **Version** member to distinguish between versions 1 and 2 of the **DMA_ADAPTER** structure. For more information about how to determine the version of a **DMA_ADAPTER** structure that is returned by this routine, see [IoGetDmaAdapter](/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter).

## -see-also

[**BUS_INTERFACE_STANDARD**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_bus_interface_standard)

[**DMA_OPERATIONS**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations)

[IoGetDmaAdapter](/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter)
