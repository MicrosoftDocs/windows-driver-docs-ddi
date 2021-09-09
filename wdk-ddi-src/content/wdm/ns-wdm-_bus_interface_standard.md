---
UID: NS:wdm._BUS_INTERFACE_STANDARD
title: _BUS_INTERFACE_STANDARD (wdm.h)
description: The BUS_INTERFACE_STANDARD interface structure enables device drivers to make direct calls to parent bus driver routines. This structure defines the GUID_BUS_INTERFACE_STANDARD interface.
old-location: kernel\bus_interface_standard.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["BUS_INTERFACE_STANDARD structure"]
ms.keywords: "*PBUS_INTERFACE_STANDARD, BUS_INTERFACE_STANDARD, BUS_INTERFACE_STANDARD structure [Kernel-Mode Driver Architecture], PBUS_INTERFACE_STANDARD, PBUS_INTERFACE_STANDARD structure pointer [Kernel-Mode Driver Architecture], _BUS_INTERFACE_STANDARD, drvr_interface_fbfd342b-15f3-485b-98e4-513beb7db0f5.xml, kernel.bus_interface_standard, wdm/BUS_INTERFACE_STANDARD, wdm/PBUS_INTERFACE_STANDARD"
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
req.typenames: BUS_INTERFACE_STANDARD, *PBUS_INTERFACE_STANDARD
f1_keywords:
 - _BUS_INTERFACE_STANDARD
 - wdm/_BUS_INTERFACE_STANDARD
 - PBUS_INTERFACE_STANDARD
 - wdm/PBUS_INTERFACE_STANDARD
 - BUS_INTERFACE_STANDARD
 - wdm/BUS_INTERFACE_STANDARD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _BUS_INTERFACE_STANDARD
 - PBUS_INTERFACE_STANDARD
 - BUS_INTERFACE_STANDARD
---

# _BUS_INTERFACE_STANDARD structure

## -description

The **BUS_INTERFACE_STANDARD** interface structure enables device drivers to make direct calls to parent bus driver routines. This structure defines the [GUID_BUS_INTERFACE_STANDARD](/windows-hardware/drivers/kernel/obtaining-device-configuration-information-at-irql---dispatch-level) interface.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Version

The driver-defined interface version.

### -field Context

A pointer to interface-specific context information.

### -field InterfaceReference

A pointer to an [InterfaceReference](./nc-wdm-pinterface_reference.md) routine that increments the interface's reference count.

### -field InterfaceDereference

A pointer to an [InterfaceDereference](./nc-wdm-pinterface_dereference.md) routine that decrements the interface's reference count.

### -field TranslateBusAddress

A pointer to a [TranslateBusAddress](./nc-wdm-translate_bus_address.md) routine that translates addresses on the parent bus to logical addresses.

### -field GetDmaAdapter

A pointer to a [GetDmaAdapter](./nc-wdm-get_dma_adapter.md) routine that returns a DMA adapter structure ([DMA_ADAPTER](./ns-wdm-_dma_adapter.md)) for the target device.

### -field SetBusData

A pointer to a [SetBusData](/previous-versions/windows/hardware/drivers/gg604856(v=vs.85)) routine that writes data to the device's configuration space.

### -field GetBusData

A pointer to a [GetBusData](./nc-wdm-get_set_device_data.md) routine that reads data from the device's configuration space.

## -remarks

The **BUS_INTERFACE_STANDARD** structure is an extension of the [INTERFACE](./ns-wdm-_interface.md) structure.

Some operations on a device are reserved for the device's parent bus driver. These operations might include accessing the device-specific configuration space of a bus or programming a DMA controller.

To read from or write to a device's configuration space, a device driver must rely on the agency of the bus driver in either of two ways:

- By sending the I/O request packets (IRPs) [IRP_MN_READ_CONFIG](/windows-hardware/drivers/kernel/irp-mn-read-config) and [IRP_MN_WRITE_CONFIG](/windows-hardware/drivers/kernel/irp-mn-write-config) to the bus driver.

- By obtaining an interface from the bus driver. The device driver can then access its device's configuration space by making direct calls to the bus driver routines provided by the **BUS_INTERFACE_STANDARD** interface structure. Its member routines, [GetBusData](./nc-wdm-get_set_device_data.md) and [SetBusData](/previous-versions/windows/hardware/drivers/gg604856(v=vs.85)), can be used to read from and write to a device's configuration space, respectively.

For more information about the ways to access configuration space, see [Accessing Device Configuration Space](/windows-hardware/drivers/kernel/accessing-device-configuration-space).

Some types of devices, such as a bus-mastering storage device, have on-board DMA controllers. However, the device drivers for these devices cannot program these DMA controllers directly. Instead they must rely on routines provided by the parent bus driver. For a device driver to program the DMA controller for its device, it must first request an adapter object from the parent bus driver. The adapter object contains the routines supplied by the bus driver that can be used to program the device's DMA controller. Device drivers must rely on the **BUS_INTERFACE_STANDARD**, either directly or indirectly, to obtain the adapter object.

If the driver is executing at IRQL = PASSIVE_LEVEL, it should obtain a device's DMA adapter object by calling [IoGetDmaAdapter](./nf-wdm-iogetdmaadapter.md). **IoGetDmaAdapter** detects whether the bus driver supports the **BUS_INTERFACE_STANDARD** interface.   If it does, **IoGetDmaAdapter** calls the routine pointed to by the [GetDmaAdapter](./nc-wdm-get_dma_adapter.md) member of this interface to obtain the adapter object. Otherwise, **IoGetDmaAdapter** calls an equivalent legacy routine.

However, if a driver must obtain an adapter object while running at IRQL >= DISPATCH_LEVEL, it cannot do so with [IoGetDmaAdapter](./nf-wdm-iogetdmaadapter.md). In this case, the driver must query for the **BUS_INTERFACE_STANDARD** interface while still at IRQL = PASSIVE_LEVEL by using [IRP_MN_QUERY_INTERFACE](/windows-hardware/drivers/kernel/irp-mn-query-interface).

## -see-also

[DEVICE_DESCRIPTION](./ns-wdm-_device_description.md)

[DMA_ADAPTER](./ns-wdm-_dma_adapter.md)

[GUID_BUS_INTERFACE_STANDARD](/windows-hardware/drivers/kernel/obtaining-device-configuration-information-at-irql---dispatch-level)

[GetBusData](./nc-wdm-get_set_device_data.md)

[GetDmaAdapter](./nc-wdm-get_dma_adapter.md)

[INTERFACE](./ns-wdm-_interface.md)

[IRP_MN_QUERY_INTERFACE](/windows-hardware/drivers/kernel/irp-mn-query-interface)

[IRP_MN_READ_CONFIG](/windows-hardware/drivers/kernel/irp-mn-read-config)

[IRP_MN_WRITE_CONFIG](/windows-hardware/drivers/kernel/irp-mn-write-config)

[InterfaceDereference](./nc-wdm-pinterface_dereference.md)

[InterfaceReference](./nc-wdm-pinterface_reference.md)

[IoGetDmaAdapter](./nf-wdm-iogetdmaadapter.md)

[SetBusData](/previous-versions/windows/hardware/drivers/gg604856(v=vs.85))

[TranslateBusAddress](./nc-wdm-translate_bus_address.md)