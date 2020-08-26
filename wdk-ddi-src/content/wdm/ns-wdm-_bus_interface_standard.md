---
UID: NS:wdm._BUS_INTERFACE_STANDARD
title: _BUS_INTERFACE_STANDARD (wdm.h)
description: The BUS_INTERFACE_STANDARD interface structure enables device drivers to make direct calls to parent bus driver routines. This structure defines the GUID_BUS_INTERFACE_STANDARD interface.
old-location: kernel\bus_interface_standard.htm
tech.root: kernel
ms.assetid: cebe5b45-2a7a-4e33-aacb-5cc3ee112808
ms.date: 04/30/2018
keywords: ["BUS_INTERFACE_STANDARD structure"]
ms.keywords: "*PBUS_INTERFACE_STANDARD, BUS_INTERFACE_STANDARD, BUS_INTERFACE_STANDARD structure [Kernel-Mode Driver Architecture], PBUS_INTERFACE_STANDARD, PBUS_INTERFACE_STANDARD structure pointer [Kernel-Mode Driver Architecture], _BUS_INTERFACE_STANDARD, drvr_interface_fbfd342b-15f3-485b-98e4-513beb7db0f5.xml, kernel.bus_interface_standard, wdm/BUS_INTERFACE_STANDARD, wdm/PBUS_INTERFACE_STANDARD"
f1_keywords:
 - "wdm/BUS_INTERFACE_STANDARD"
 - "BUS_INTERFACE_STANDARD"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- BUS_INTERFACE_STANDARD
targetos: Windows
req.typenames: BUS_INTERFACE_STANDARD, *PBUS_INTERFACE_STANDARD
---

# _BUS_INTERFACE_STANDARD structure


## -description


The <b>BUS_INTERFACE_STANDARD</b> interface structure enables device drivers to make direct calls to parent bus driver routines. This structure defines the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/obtaining-device-configuration-information-at-irql---dispatch-level">GUID_BUS_INTERFACE_STANDARD</a> interface.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The driver-defined interface version.


### -field Context

A pointer to interface-specific context information.


### -field InterfaceReference

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a> routine that increments the interface's reference count.


### -field InterfaceDereference

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a> routine that decrements the interface's reference count.


### -field TranslateBusAddress

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-translate_bus_address">TranslateBusAddress</a> routine that translates addresses on the parent bus to logical addresses.


### -field GetDmaAdapter

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_dma_adapter">GetDmaAdapter</a> routine that returns a DMA adapter structure (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>) for the target device.


### -field SetBusData

A pointer to a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/gg604856(v=vs.85)">SetBusData</a> routine that writes data to the device's configuration space.


### -field GetBusData

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_set_device_data">GetBusData</a> routine that reads data from the device's configuration space.


## -remarks



The <b>BUS_INTERFACE_STANDARD</b> structure is an extension of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure.

Some operations on a device are reserved for the device's parent bus driver. These operations might include accessing the device-specific configuration space of a bus or programming a DMA controller.

To read from or write to a device's configuration space, a device driver must rely on the agency of the bus driver in either of two ways:

<ul>
<li>
By sending the I/O request packets (IRPs) <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-read-config">IRP_MN_READ_CONFIG</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-write-config">IRP_MN_WRITE_CONFIG</a> to the bus driver.

</li>
<li>
By obtaining an interface from the bus driver. The device driver can then access its device's configuration space by making direct calls to the bus driver routines provided by the <b>BUS_INTERFACE_STANDARD</b> interface structure. Its member routines, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_set_device_data">GetBusData</a> and <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/gg604856(v=vs.85)">SetBusData</a>, can be used to read from and write to a device's configuration space, respectively.



</li>
</ul>
For more information about the ways to access configuration space, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/accessing-device-configuration-space">Accessing Device Configuration Space</a>.

Some types of devices, such as a bus-mastering storage device, have on-board DMA controllers. However, the device drivers for these devices cannot program these DMA controllers directly. Instead they must rely on routines provided by the parent bus driver. For a device driver to program the DMA controller for its device, it must first request an adapter object from the parent bus driver. The adapter object contains the routines supplied by the bus driver that can be used to program the device's DMA controller. Device drivers must rely on the <b>BUS_INTERFACE_STANDARD</b>, either directly or indirectly, to obtain the adapter object.

If the driver is executing at IRQL = PASSIVE_LEVEL, it should obtain a device's DMA adapter object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>. <b>IoGetDmaAdapter</b> detects whether the bus driver supports the <b>BUS_INTERFACE_STANDARD</b> interface.   If it does, <b>IoGetDmaAdapter</b> calls the routine pointed to by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_dma_adapter">GetDmaAdapter</a> member of this interface to obtain the adapter object. Otherwise, <b>IoGetDmaAdapter</b> calls an equivalent legacy routine.

However, if a driver must obtain an adapter object while running at IRQL >= DISPATCH_LEVEL, it cannot do so with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>. In this case, the driver must query for the <b>BUS_INTERFACE_STANDARD</b> interface while still at IRQL = PASSIVE_LEVEL by using <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description">DEVICE_DESCRIPTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546561">GUID_BUS_INTERFACE_STANDARD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_set_device_data">GetBusData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_dma_adapter">GetDmaAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-read-config">IRP_MN_READ_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-write-config">IRP_MN_WRITE_CONFIG </a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/gg604856(v=vs.85)">SetBusData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-translate_bus_address">TranslateBusAddress</a>
 

 

