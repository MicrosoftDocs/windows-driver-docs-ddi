---
UID: NC:wdm.GET_DMA_ADAPTER
title: GET_DMA_ADAPTER (wdm.h)
description: The GetDmaAdapter routine returns a DMA_ADAPTER structure for the target device.
old-location: kernel\getdmaadapter.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["GET_DMA_ADAPTER callback function"]
ms.keywords: GET_DMA_ADAPTER, GetDmaAdapter, GetDmaAdapter routine [Kernel-Mode Driver Architecture], drvr_interface_5c7fd89d-0b6c-45e7-8559-8666f43beb9a.xml, kernel.busgetdmaadapter, kernel.getdmaadapter, ntddk/GetDmaAdapter
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with  Windows 2000.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - GET_DMA_ADAPTER
 - wdm/GET_DMA_ADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - GET_DMA_ADAPTER
---

# GET_DMA_ADAPTER callback function


## -description

The <i>GetDmaAdapter</i> routine returns a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure for the target device.

## -parameters

### -param Context [in]


A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_bus_interface_standard">BUS_INTERFACE_STANDARD</a> structure for the interface.

### -param DeviceDescriptor [in]


A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description">DEVICE_DESCRIPTION</a> structure that describes the attributes of the physical device.

### -param NumberOfMapRegisters [out]


A pointer to, on output, the maximum number of map registers that the driver can allocate for any DMA transfer operation. The caller must allocate a <b>LONG</b> variable to receive this data.

## -returns

The <i>GetDmaAdapter</i> routine returns a pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure when successful. If an adapter structure cannot be allocated, the routine returns <b>NULL</b>.

## -remarks

If the driver is executing at IRQL = PASSIVE_LEVEL, it should obtain a device's DMA adapter object by calling the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> function. <b>IoGetDmaAdapter</b> detects whether the bus driver supports the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_bus_interface_standard">BUS_INTERFACE_STANDARD</a> interface; if it does, <b>IoGetDmaAdapter</b> calls the routine pointed to by the <i>GetDmaAdapter</i> member of this interface to obtain the adapter object. Otherwise, <b>IoGetDmaAdapter</b> calls an equivalent legacy routine.

However, if a driver must obtain an adapter object while running at IRQL ≥ DISPATCH_LEVEL, it cannot do so with the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> function. In such a case, the driver must query for the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_bus_interface_standard">BUS_INTERFACE_STANDARD</a> interface while still at IRQL = PASSIVE_LEVEL by issuing an <a href="/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a> request.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_bus_interface_standard">BUS_INTERFACE_STANDARD</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description">DEVICE_DESCRIPTION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>

