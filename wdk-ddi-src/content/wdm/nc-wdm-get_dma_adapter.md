---
UID: NC:wdm.GET_DMA_ADAPTER
title: GET_DMA_ADAPTER
author: windows-driver-content
description: The GetDmaAdapter routine returns a DMA_ADAPTER structure for the target device.
old-location: kernel\getdmaadapter.htm
old-project: kernel
ms.assetid: 0F703E88-2650-4451-9F5A-05FBCF33C131
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: GET_DMA_ADAPTER, GetDmaAdapter, GetDmaAdapter routine [Kernel-Mode Driver Architecture], drvr_interface_5c7fd89d-0b6c-45e7-8559-8666f43beb9a.xml, kernel.busgetdmaadapter, kernel.getdmaadapter, ntddk/GetDmaAdapter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ntddk.h
api_name:
-	GetDmaAdapter
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# GET_DMA_ADAPTER callback


## -description


The <i>GetDmaAdapter</i> routine returns a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure for the target device. 


## -prototype


````
GET_DMA_ADAPTER GetDmaAdapter;

PDMA_ADAPTER GetDmaAdapter(
  _In_  PVOID               Context,
  _In_  PDEVICE_DESCRIPTION DeviceDescriptor,
  _Out_ PULONG              NumberOfMapRegisters
)
{ ... }
````


## -parameters




### -param Context [in]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="..\wdm\ns-wdm-_bus_interface_standard.md">BUS_INTERFACE_STANDARD</a> structure for the interface.


### -param DeviceDescriptor [in]

A pointer to a <a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a> structure that describes the attributes of the physical device. 


### -param NumberOfMapRegisters [out]

A pointer to, on output, the maximum number of map registers that the driver can allocate for any DMA transfer operation. The caller must allocate a <b>LONG</b> variable to receive this data.


## -returns



The <i>GetDmaAdapter</i> routine returns a pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure when successful. If an adapter structure cannot be allocated, the routine returns <b>NULL</b>.




## -remarks



If the driver is executing at IRQL = PASSIVE_LEVEL, it should obtain a device's DMA adapter object by calling the <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> function. <b>IoGetDmaAdapter</b> detects whether the bus driver supports the <a href="..\wdm\ns-wdm-_bus_interface_standard.md">BUS_INTERFACE_STANDARD</a> interface; if it does, <b>IoGetDmaAdapter</b> calls the routine pointed to by the <i>GetDmaAdapter</i> member of this interface to obtain the adapter object. Otherwise, <b>IoGetDmaAdapter</b> calls an equivalent legacy routine.

However, if a driver must obtain an adapter object while running at IRQL ≥ DISPATCH_LEVEL, it cannot do so with the <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> function. In such a case, the driver must query for the <a href="..\wdm\ns-wdm-_bus_interface_standard.md">BUS_INTERFACE_STANDARD</a> interface while still at IRQL = PASSIVE_LEVEL by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request.




## -see-also

<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>



<a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>



<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



<a href="..\wdm\ns-wdm-_bus_interface_standard.md">BUS_INTERFACE_STANDARD</a>



 

 


