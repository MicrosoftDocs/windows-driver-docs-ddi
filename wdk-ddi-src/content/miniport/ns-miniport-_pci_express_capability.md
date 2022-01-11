---
UID: NS:miniport._PCI_EXPRESS_CAPABILITY
title: PCI_EXPRESS_CAPABILITY (miniport.h)
description: The _PCI_EXPRESS_CAPABILITY structure (miniport.h) describes a PCI Express (PCIe) capability structure.
old-location: pci\pci_express_capability.htm
tech.root: PCI
ms.date: 01/09/2022
keywords: ["PCI_EXPRESS_CAPABILITY structure"]
ms.keywords: "*PPCI_EXPRESS_CAPABILITY, PCI.pci_express_capability, PCI_EXPRESS_CAPABILITY, PCI_EXPRESS_CAPABILITY structure [Buses], PPCI_EXPRESS_CAPABILITY, PPCI_EXPRESS_CAPABILITY structure pointer [Buses], _PCI_EXPRESS_CAPABILITY, ntddk/PCI_EXPRESS_CAPABILITY, ntddk/PPCI_EXPRESS_CAPABILITY, pci_struct_9c629781-bcee-486d-bab3-5d5b7441ac72.xml"
req.header: miniport.h
req.include-header: Ntddk.h, Miniport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2008
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
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: PCI_EXPRESS_CAPABILITY, *PPCI_EXPRESS_CAPABILITY
f1_keywords:
 - _PCI_EXPRESS_CAPABILITY
 - miniport/_PCI_EXPRESS_CAPABILITY
 - PPCI_EXPRESS_CAPABILITY
 - miniport/PPCI_EXPRESS_CAPABILITY
 - PCI_EXPRESS_CAPABILITY
 - miniport/PCI_EXPRESS_CAPABILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_CAPABILITY
 - PPCI_EXPRESS_CAPABILITY
 - PCI_EXPRESS_CAPABILITY
---

# PCI_EXPRESS_CAPABILITY structure (miniport.h)

## -description

The **PCI_EXPRESS_CAPABILITY** structure describes a PCI Express (PCIe) capability structure.

## -struct-fields

### -field Header

A [**PCI_CAPABILITIES_HEADER**](../wdm/ns-wdm-_pci_capabilities_header.md) structure that describes the PCI capabilities header of the PCIe capability structure.

### -field ExpressCapabilities

A [**PCI_EXPRESS_CAPABILITIES_REGISTER**](../ntddk/ns-ntddk-_pci_express_capabilities_register.md) structure that describes the PCIe capabilities register of the PCIe capability structure.

### -field DeviceCapabilities

A [**PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER**](../ntddk/ns-ntddk-_pci_express_device_capabilities_register.md) structure that describes the PCIe device capabilities register of the PCIe capability structure.

### -field DeviceControl

A [**PCI_EXPRESS_DEVICE_CONTROL_REGISTER**](../ntddk/ns-ntddk-_pci_express_device_control_register.md) structure that describes the PCIe device control register of the PCIe capability structure.

### -field DeviceStatus

A [**PCI_EXPRESS_DEVICE_STATUS_REGISTER**](../ntddk/ns-ntddk-_pci_express_device_status_register.md) structure that describes the PCIe device status register of the PCIe capability structure.

### -field LinkCapabilities

A [**PCI_EXPRESS_LINK_CAPABILITIES_REGISTER**](../ntddk/ns-ntddk-_pci_express_link_capabilities_register.md) structure that describes the PCIe link capabilities register of the PCIe capability structure.

### -field LinkControl

A [**PCI_EXPRESS_LINK_CONTROL_REGISTER**](../ntddk/ns-ntddk-_pci_express_link_control_register.md) structure that describes the PCIe link control register of the PCIe capability structure.

### -field LinkStatus

A [**PCI_EXPRESS_LINK_STATUS_REGISTER**](../ntddk/ns-ntddk-_pci_express_link_status_register.md) structure that describes the PCIe link status register of the PCIe capability structure.

### -field SlotCapabilities

A [**PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER**](../ntddk/ns-ntddk-_pci_express_slot_capabilities_register.md) structure that describes the PCIe slot capabilities register of the PCIe capability structure.

### -field SlotControl

A [**PCI_EXPRESS_SLOT_CONTROL_REGISTER**](../ntddk/ns-ntddk-_pci_express_slot_control_register.md) structure that describes the PCIe slot control register of the PCIe capability structure.

### -field SlotStatus

A [**PCI_EXPRESS_SLOT_STATUS_REGISTER**](../ntddk/ns-ntddk-_pci_express_slot_status_register.md) structure that describes the PCIe slot status register of the PCIe capability structure.

### -field RootControl

A [**PCI_EXPRESS_ROOT_CONTROL_REGISTER**](../ntddk/ns-ntddk-_pci_express_root_control_register.md) structure that describes the PCIe root control register of the PCIe capability structure.

### -field RootCapabilities

A [**PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER**](../ntddk/ns-ntddk-_pci_express_root_capabilities_register.md) structure that describes the PCIe root capabilities register of the PCIe capability structure.

### -field RootStatus

A [**PCI_EXPRESS_ROOT_STATUS_REGISTER**](../ntddk/ns-ntddk-_pci_express_root_status_register.md) structure that describes the PCIe root status register of the PCIe capability structure.

### -field DeviceCapabilities2

A **PCI_EXPRESS_DEVICE_CAPABILITIES_2_REGISTER** structure that describes the PCIe device capabilities 2 register of the PCIe capability structure.

### -field DeviceControl2

A **PCI_EXPRESS_DEVICE_CONTROL_2_REGISTER** structure that describes the PCIe device control 2 register of the PCIe capability structure.

### -field DeviceStatus2

A **PCI_EXPRESS_DEVICE_STATUS_2_REGISTER** structure that describes the PCIe device status 2 register of the PCIe capability structure.

## -remarks

For additional information about the PCIe capability structure, see the [PCI Express Specification](https://pcisig.com/specifications/pciexpress).

## -see-also

[**PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER**](../ntddk/ns-ntddk-_pci_express_device_capabilities_register.md)

[**PCI_EXPRESS_LINK_CAPABILITIES_REGISTER**](../ntddk/ns-ntddk-_pci_express_link_capabilities_register.md)

[**PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER**](../ntddk/ns-ntddk-_pci_express_root_capabilities_register.md)

[**PCI_EXPRESS_ROOT_STATUS_REGISTER**](../ntddk/ns-ntddk-_pci_express_root_status_register.md)

[**PCI_EXPRESS_ROOT_CONTROL_REGISTER**](../ntddk/ns-ntddk-_pci_express_root_control_register.md)

[**PCI_EXPRESS_DEVICE_CONTROL_REGISTER**](../ntddk/ns-ntddk-_pci_express_device_control_register.md)

[**PCI_EXPRESS_DEVICE_STATUS_REGISTER**](../ntddk/ns-ntddk-_pci_express_device_status_register.md)

[**PCI_EXPRESS_CAPABILITIES_REGISTER**](../ntddk/ns-ntddk-_pci_express_capabilities_register.md)

[**PCI_CAPABILITIES_HEADER**](../wdm/ns-wdm-_pci_capabilities_header.md)

[**PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER**](../ntddk/ns-ntddk-_pci_express_slot_capabilities_register.md)

[**PCI_EXPRESS_LINK_STATUS_REGISTER**](../ntddk/ns-ntddk-_pci_express_link_status_register.md)

[**PCI_EXPRESS_SLOT_CONTROL_REGISTER**](../ntddk/ns-ntddk-_pci_express_slot_control_register.md)

[**PCI_EXPRESS_LINK_CONTROL_REGISTER**](../ntddk/ns-ntddk-_pci_express_link_control_register.md)

[**PCI_EXPRESS_SLOT_STATUS_REGISTER**](../ntddk/ns-ntddk-_pci_express_slot_status_register.md)
