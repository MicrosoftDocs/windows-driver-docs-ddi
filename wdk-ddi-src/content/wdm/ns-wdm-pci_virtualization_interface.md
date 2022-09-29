---
UID: NS:wdm._PCI_VIRTUALIZATION_INTERFACE
tech.root: pci
title: PCI_VIRTUALIZATION_INTERFACE
ms.date: 09/27/2022
targetos: Windows
description: Learn more about the PCI_VIRTUALIZATION_INTERFACE structure
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2012
req.target-type: 
req.typenames: PCI_VIRTUALIZATION_INTERFACE, *PPCI_VIRTUALIZATION_INTERFACE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_VIRTUALIZATION_INTERFACE
 - PPCI_VIRTUALIZATION_INTERFACE
 - PCI_VIRTUALIZATION_INTERFACE
f1_keywords:
 - _PCI_VIRTUALIZATION_INTERFACE
 - wdm/_PCI_VIRTUALIZATION_INTERFACE
 - PPCI_VIRTUALIZATION_INTERFACE
 - wdm/PPCI_VIRTUALIZATION_INTERFACE
 - PCI_VIRTUALIZATION_INTERFACE
 - wdm/PCI_VIRTUALIZATION_INTERFACE
dev_langs:
 - c++
helpviewer_keywords:
 - _PCI_VIRTUALIZATION_INTERFACE
---

## -description

The **PCI\_VIRTUALIZATION\_INTERFACE** structure enables drivers to manage and configure the PCI Express (PCIe) configuration space for a virtual function (VF). VFs are exposed on the PCI bus by devices that support the single root I/O virtualization (SR-IOV) interface.

This structure describes the **GUID\_PCI\_VIRTUALIZATION\_INTERFACE** interface.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Version

The driver-defined interface version.

### -field Context

A pointer to interface-specific context information.

### -field InterfaceReference

A pointer to an [*InterfaceReference*](/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface) routine that increments the interface's reference count.

### -field InterfaceDereference

A pointer to an [*InterfaceDereference*](/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference) routine that decrements the interface's reference count.

### -field SetVirtualFunctionData

A pointer to a [*SetVirtualFunctionData*](/windows-hardware/drivers/ddi/wdm/nc-wdm-set_virtual_device_data) routine that writes data to the PCIe configuration space of an SR-IOV device's VF.

### -field GetVirtualFunctionData

A pointer to a [*GetVirtualFunctionData*](/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_device_data) routine that reads data from the PCIe configuration space of an SR-IOV device's VF.

### -field GetLocation

A pointer to a [*GetLocation*](/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_device_location) routine that provides information about the current device location of a VF in the PCIe hierarchy. This information is necessary for a virtualization system that is using an I/O memory management unit (IOMMU) to route traffic to or from the device.

### -field GetResources

A pointer to a [*GetResources*](/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_device_resources) routine that provides information about the resources that are available for virtualization on an SR-IOV device.

### -field EnableVirtualization

A pointer to an [*EnableVirtualization*](/windows-hardware/drivers/ddi/wdm/nc-wdm-enable_virtualization) routine that enables or disables virtualization on an SR-IOV device.

### -field GetVirtualFunctionProbedBars

A pointer to a [*GetVirtualFunctionProbedBars*](/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_function_probed_bars) routine that allows a non-privileged Hyper-V virtual machine (VM) to determine what would be read from the PCIe Base Address Registers (BARs) of a VF after a query by the PCI bus driver. The PCI driver performs this query to determine the memory or I/O address space that the device requires.

## -remarks

For devices that support the SR-IOV interface, drivers occasionally have to access and manage the PCIe configuration space of the device's VFs. Drivers call routines from the GUID\_PCI\_VIRTUALIZATION\_INTERFACE interface to access the PCIe configuration space of the VFs on the device.

> [!NOTE]
> Since a device's VFs do not appear as complete PCIe devices on the PCI bus, the [GUID\_BUS\_INTERFACE\_STANDARD](/windows-hardware/drivers/ddi/wdm/ns-wdm-_bus_interface_standard) interface cannot be used for the management of a VF.

The **PCI\_VIRTUALIZATION\_INTERFACE** structure is an extension of the [**INTERFACE**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface) structure.

A driver obtains a pointer to the **PCI\_VIRTUALIZATION\_INTERFACE** structure by sending an [**IRP\_MN\_QUERY\_INTERFACE**](/windows-hardware/drivers/kernel/irp-mn-query-interface) I/O request packet (IRP) to its bus driver with *InterfaceType* set to GUID\_PCI\_VIRTUALIZATION\_INTERFACE.

## -see-also

[GUID\_BUS\_INTERFACE\_STANDARD](/windows-hardware/drivers/ddi/wdm/ns-wdm-_bus_interface_standard)

[*InterfaceDereference*](/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference)

[*InterfaceReference*](/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface)

[**IRP\_MN\_QUERY\_INTERFACE**](/windows-hardware/drivers/kernel/irp-mn-query-interface)
