---
UID: NS:vpci._VPCI_INTERFACE_STANDARD
tech.root: pci
title: VPCI_INTERFACE_STANDARD
ms.date: 09/27/2022
targetos: Windows
description: Learn more about the VPCI_INTERFACE_STANDARD structure
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: vpci.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2012
req.target-type: 
req.typenames: VPCI_INTERFACE_STANDARD, *PVPCI_INTERFACE_STANDARD
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - vpci.h
api_name:
 - _VPCI_INTERFACE_STANDARD
 - PVPCI_INTERFACE_STANDARD
 - VPCI_INTERFACE_STANDARD
f1_keywords:
 - _VPCI_INTERFACE_STANDARD
 - vpci/_VPCI_INTERFACE_STANDARD
 - PVPCI_INTERFACE_STANDARD
 - vpci/PVPCI_INTERFACE_STANDARD
 - VPCI_INTERFACE_STANDARD
 - vpci/VPCI_INTERFACE_STANDARD
dev_langs:
 - c++
helpviewer_keywords:
 - _VPCI_INTERFACE_STANDARD
---

## -description

The **VPCI\_INTERFACE\_STANDARD** interface structure enables device drivers to access blocks of configuration data that is specific to a PCI Express (PCIe) virtual function (VF) of devices that support the single root I/O virtualization (SR-IOV) interface.

This structure describes the **GUID\_VPCI\_INTERFACE\_STANDARD** interface.

> [!NOTE]
> The location of the VF configuration block and the format of the configuration data are defined by the independent hardware vendor (IHV) of the device. They are used only by the drivers of the PCIe physical function (PF) and the VF.

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

### -field WriteVfConfigBlock

A pointer to a [*WriteVfConfigBlock*](/windows-hardware/drivers/ddi/vpci/nc-vpci-vpci_write_block) routine that writes a block of configuration data for a PCIe VF.

### -field ReadVfConfigBlock

A pointer to a [*ReadVfConfigBlock*](/windows-hardware/drivers/ddi/vpci/nc-vpci-vpci_read_block) routine that reads a block of configuration data for a PCIe VF.

### -field SerialNumber

A UINT32 value that contains the serial number for the PCIe VF on the device. The virtualization stack generates a unique serial number for each VF that is exposed on the device.

## -remarks

The **GUID\_VPCI\_INTERFACE\_STANDARD** interface is provided by the virtual PCI (VPCI) bus driver that creates the physical device objects (PDOs) that are layered below the loaded drivers for the VFs. These drivers are loaded in the guest operating system that runs in a Hyper-V child partition.

A driver obtains a pointer to the **VPCI\_INTERFACE\_STANDARD** structure by sending an [**IRP\_MN\_QUERY\_INTERFACE**](/windows-hardware/drivers/kernel/irp-mn-query-interface) IRP to its bus driver with **InterfaceType** set to GUID\_VPCI\_INTERFACE\_STANDARD.

## -see-also

[*InterfaceDereference*](/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference)

[*InterfaceReference*](/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface)

[**IRP\_MN\_QUERY\_INTERFACE**](/windows-hardware/drivers/kernel/irp-mn-query-interface)

[*ReadVfConfigBlock*](/windows-hardware/drivers/ddi/vpci/nc-vpci-vpci_read_block)

[*WriteVfConfigBlock*](/windows-hardware/drivers/ddi/vpci/nc-vpci-vpci_write_block)
