---
UID: NS:wdm._PCI_VIRTUALIZATION_INTERFACE
tech.root: pci
title: PCI_VIRTUALIZATION_INTERFACE
ms.date: 01/06/2023
targetos: Windows
description: Learn more about the PCI_VIRTUALIZATION_INTERFACE structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
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

The **PCI_VIRTUALIZATION_INTERFACE** structure enables drivers to manage and configure the PCI Express (PCIe) configuration space for a virtual function (VF). VFs are exposed on the PCI bus by devices that support the single root I/O virtualization (SR-IOV) interface.

This structure describes the **GUID_PCI_VIRTUALIZATION_INTERFACE** interface.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Version

The driver-defined interface version.

### -field Context

A pointer to interface-specific context information.

### -field InterfaceReference

A pointer to an [*InterfaceReference*](ns-wdm-_interface.md) routine that increments the interface's reference count.

### -field InterfaceDereference

A pointer to an [*InterfaceDereference*](nc-wdm-pinterface_dereference.md) routine that decrements the interface's reference count.

### -field SetVirtualFunctionData

A pointer to a [*SetVirtualFunctionData*](nc-wdm-set_virtual_device_data.md) routine that writes data to the PCIe configuration space of an SR-IOV device's VF.

### -field GetVirtualFunctionData

A pointer to a [*GetVirtualFunctionData*](nc-wdm-get_virtual_device_data.md) routine that reads data from the PCIe configuration space of an SR-IOV device's VF.

### -field GetLocation

A pointer to a [*GetLocation*](nc-wdm-get_virtual_device_location.md) routine that provides information about the current device location of a VF in the PCIe hierarchy. This information is necessary for a virtualization system that is using an I/O memory management unit (IOMMU) to route traffic to or from the device.

### -field GetResources

A pointer to a [*GetResources*](nc-wdm-get_virtual_device_resources.md) routine that provides information about the resources that are available for virtualization on an SR-IOV device.

### -field EnableVirtualization

A pointer to an [*EnableVirtualization*](nc-wdm-enable_virtualization.md) routine that enables or disables virtualization on an SR-IOV device.

### -field GetVirtualFunctionProbedBars

A pointer to a [*GetVirtualFunctionProbedBars*](nc-wdm-get_virtual_function_probed_bars.md) routine that allows a non-privileged Hyper-V virtual machine (VM) to determine what would be read from the PCIe Base Address Registers (BARs) of a VF after a query by the PCI bus driver. The PCI driver performs this query to determine the memory or I/O address space that the device requires.

## -remarks

For devices that support the SR-IOV interface, drivers occasionally have to access and manage the PCIe configuration space of the device's VFs. Drivers call routines from the GUID_PCI_VIRTUALIZATION_INTERFACE interface to access the PCIe configuration space of the VFs on the device.

Since a device's VFs do not appear as complete PCIe devices on the PCI bus, the [**GUID_BUS_INTERFACE_STANDARD**](ns-wdm-_bus_interface_standard.md) interface cannot be used for the management of a VF.

The **PCI_VIRTUALIZATION_INTERFACE** structure is an extension of the [**INTERFACE**](ns-wdm-_interface.md) structure.

A driver obtains a pointer to the **PCI_VIRTUALIZATION_INTERFACE** structure by sending an [**IRP_MN_QUERY_INTERFACE**](/windows-hardware/drivers/kernel/irp-mn-query-interface) I/O request packet (IRP) to its bus driver with *InterfaceType* set to GUID_PCI_VIRTUALIZATION_INTERFACE.

## -see-also

[**GUID_BUS_INTERFACE_STANDARD**](ns-wdm-_bus_interface_standard.md)

[*InterfaceDereference*](nc-wdm-pinterface_dereference.md)

[**InterfaceReference**](ns-wdm-_interface.md)

[**IRP_MN_QUERY_INTERFACE**](/windows-hardware/drivers/kernel/irp-mn-query-interface)
