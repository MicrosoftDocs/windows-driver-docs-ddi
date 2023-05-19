---
UID: NS:ntddk._PCI_EXPRESS_CAPABILITY
tech.root: PCI
title: PCI_EXPRESS_CAPABILITY (ntddk.h)
ms.date: 03/03/2022
targetos: Windows
description: The PCI_EXPRESS_CAPABILITY structure describes a PCI Express (PCIe) capability structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.include-header: Ntddk.h, Miniport.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PCI_EXPRESS_CAPABILITY, *PPCI_EXPRESS_CAPABILITY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_CAPABILITY
 - PPCI_EXPRESS_CAPABILITY
 - PCI_EXPRESS_CAPABILITY
f1_keywords:
 - _PCI_EXPRESS_CAPABILITY
 - ntddk/_PCI_EXPRESS_CAPABILITY
 - PPCI_EXPRESS_CAPABILITY
 - ntddk/PPCI_EXPRESS_CAPABILITY
 - PCI_EXPRESS_CAPABILITY
 - ntddk/PCI_EXPRESS_CAPABILITY
dev_langs:
 - c++
helpviewer_keywords:
 - _PCI_EXPRESS_CAPABILITY
---

## -description

The **PCI_EXPRESS_CAPABILITY** structure describes a PCI Express (PCIe) capability structure.

## -struct-fields

### -field Header

A [PCI_CAPABILITIES_HEADER](../wdm/ns-wdm-_pci_capabilities_header.md) structure that describes the PCI capabilities header of the PCIe capability structure.

### -field ExpressCapabilities

A [PCI_EXPRESS_CAPABILITIES_REGISTER](./ns-ntddk-_pci_express_capabilities_register.md) structure that describes the PCIe capabilities register of the PCIe capability structure.

### -field DeviceCapabilities

A [PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER](./ns-ntddk-_pci_express_device_capabilities_register.md) structure that describes the PCIe device capabilities register of the PCIe capability structure.

### -field DeviceControl

A [PCI_EXPRESS_DEVICE_CONTROL_REGISTER](./ns-ntddk-_pci_express_device_control_register.md) structure that describes the PCIe device control register of the PCIe capability structure.

### -field DeviceStatus

A [PCI_EXPRESS_DEVICE_STATUS_REGISTER](./ns-ntddk-_pci_express_device_status_register.md) structure that describes the PCIe device status register of the PCIe capability structure.

### -field LinkCapabilities

A [PCI_EXPRESS_LINK_CAPABILITIES_REGISTER](./ns-ntddk-_pci_express_link_capabilities_register.md) structure that describes the PCIe link capabilities register of the PCIe capability structure.

### -field LinkControl

A [PCI_EXPRESS_LINK_CONTROL_REGISTER](./ns-ntddk-_pci_express_link_control_register.md) structure that describes the PCIe link control register of the PCIe capability structure.

### -field LinkStatus

A [PCI_EXPRESS_LINK_STATUS_REGISTER](./ns-ntddk-_pci_express_link_status_register.md) structure that describes the PCIe link status register of the PCIe capability structure.

### -field SlotCapabilities

A [PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER](./ns-ntddk-_pci_express_slot_capabilities_register.md) structure that describes the PCIe slot capabilities register of the PCIe capability structure.

### -field SlotControl

A [PCI_EXPRESS_SLOT_CONTROL_REGISTER](./ns-ntddk-_pci_express_slot_control_register.md) structure that describes the PCIe slot control register of the PCIe capability structure.

### -field SlotStatus

A [PCI_EXPRESS_SLOT_STATUS_REGISTER](./ns-ntddk-_pci_express_slot_status_register.md) structure that describes the PCIe slot status register of the PCIe capability structure.

### -field RootControl

A [PCI_EXPRESS_ROOT_CONTROL_REGISTER](./ns-ntddk-_pci_express_root_control_register.md) structure that describes the PCIe root control register of the PCIe capability structure.

### -field RootCapabilities

A [PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER](./ns-ntddk-_pci_express_root_capabilities_register.md) structure that describes the PCIe root capabilities register of the PCIe capability structure.

### -field RootStatus

A [PCI_EXPRESS_ROOT_STATUS_REGISTER](./ns-ntddk-_pci_express_root_status_register.md) structure that describes the PCIe root status register of the PCIe capability structure.

### -field DeviceCapabilities2

Defines the **PCI_EXPRESS_DEVICE_CAPABILITIES_2_REGISTER** member **DeviceCapabilities2**.

### -field DeviceControl2

Defines the **PCI_EXPRESS_DEVICE_CONTROL_2_REGISTER** member **DeviceControl2**.

### -field DeviceStatus2

Defines the **PCI_EXPRESS_DEVICE_STATUS_2_REGISTER** member **DeviceStatus2**.

### -field LinkCapabilities2

A [PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER](ns-ntddk-pci_express_link_capabilities_2_register.md) structure that describes the PCIe link capabilities 2 register of the PCIe capability structure, extending the PCIe link capabilities register.

### -field LinkControl2

A [PCI_EXPRESS_LINK_CONTROL_2_REGISTER](ns-ntddk-pci_express_link_control_2_register.md) structure that describes the PCIe link control 2 register of the PCIe capability structure, extending the PCIe link control register.

### -field LinkStatus2

A [PCI_EXPRESS_LINK_STATUS_2_REGISTER](ns-ntddk-pci_express_link_status_2_register.md) structure that describes the PCIe link capabilities 2 register of the PCIe capability structure, extending the PCIe link capabilities register.

## -remarks

For additional information about the PCIe capability structure, see the [PCI Express Specification](https://pcisig.com/specifications/pciexpress/).

## -see-also

[PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER](./ns-ntddk-_pci_express_device_capabilities_register.md)

[PCI_EXPRESS_LINK_CAPABILITIES_REGISTER](./ns-ntddk-_pci_express_link_capabilities_register.md)

[PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER](./ns-ntddk-_pci_express_root_capabilities_register.md)

[PCI_EXPRESS_ROOT_STATUS_REGISTER](./ns-ntddk-_pci_express_root_status_register.md)

[PCI_EXPRESS_ROOT_CONTROL_REGISTER](./ns-ntddk-_pci_express_root_control_register.md)

[PCI_EXPRESS_DEVICE_CONTROL_REGISTER](./ns-ntddk-_pci_express_device_control_register.md)

[PCI_EXPRESS_DEVICE_STATUS_REGISTER](./ns-ntddk-_pci_express_device_status_register.md)

[PCI_EXPRESS_CAPABILITIES_REGISTER](./ns-ntddk-_pci_express_capabilities_register.md)

[PCI_CAPABILITIES_HEADER](../wdm/ns-wdm-_pci_capabilities_header.md)

[PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER](./ns-ntddk-_pci_express_slot_capabilities_register.md)

[PCI_EXPRESS_LINK_STATUS_REGISTER](./ns-ntddk-_pci_express_link_status_register.md)

[PCI_EXPRESS_SLOT_CONTROL_REGISTER](./ns-ntddk-_pci_express_slot_control_register.md)

[PCI_EXPRESS_LINK_CONTROL_REGISTER](./ns-ntddk-_pci_express_link_control_register.md)

[PCI_EXPRESS_SLOT_STATUS_REGISTER](./ns-ntddk-_pci_express_slot_status_register.md)

[PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER](ns-ntddk-pci_express_link_capabilities_2_register.md)

[PCI_EXPRESS_LINK_CONTROL_2_REGISTER](ns-ntddk-pci_express_link_control_2_register.md) 

[PCI_EXPRESS_LINK_STATUS_2_REGISTER](ns-ntddk-pci_express_link_status_2_register.md)

