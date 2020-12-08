---
UID: NS:ntddk._PCI_EXPRESS_CAPABILITY
title: _PCI_EXPRESS_CAPABILITY (ntddk.h)
description: The PCI_EXPRESS_CAPABILITY structure describes a PCI Express (PCIe) capability structure.
old-location: pci\pci_express_capability.htm
tech.root: PCI
ms.date: 02/24/2018
keywords: ["PCI_EXPRESS_CAPABILITY structure"]
ms.keywords: "*PPCI_EXPRESS_CAPABILITY, PCI.pci_express_capability, PCI_EXPRESS_CAPABILITY, PCI_EXPRESS_CAPABILITY structure [Buses], PPCI_EXPRESS_CAPABILITY, PPCI_EXPRESS_CAPABILITY structure pointer [Buses], _PCI_EXPRESS_CAPABILITY, ntddk/PCI_EXPRESS_CAPABILITY, ntddk/PPCI_EXPRESS_CAPABILITY, pci_struct_9c629781-bcee-486d-bab3-5d5b7441ac72.xml"
req.header: ntddk.h
req.include-header: Ntddk.h, Miniport.h
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: PCI_EXPRESS_CAPABILITY, *PPCI_EXPRESS_CAPABILITY
f1_keywords:
 - _PCI_EXPRESS_CAPABILITY
 - ntddk/_PCI_EXPRESS_CAPABILITY
 - PPCI_EXPRESS_CAPABILITY
 - ntddk/PPCI_EXPRESS_CAPABILITY
 - PCI_EXPRESS_CAPABILITY
 - ntddk/PCI_EXPRESS_CAPABILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PCI_EXPRESS_CAPABILITY
---

# _PCI_EXPRESS_CAPABILITY structure (ntddk.h)


## -description

The PCI_EXPRESS_CAPABILITY structure describes a PCI Express (PCIe) capability structure.

## -struct-fields

### -field Header

A <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_capabilities_header">PCI_CAPABILITIES_HEADER</a> structure that describes the PCI capabilities header of the PCIe capability structure.

### -field ExpressCapabilities

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capabilities_register">PCI_EXPRESS_CAPABILITIES_REGISTER</a> structure that describes the PCIe capabilities register of the PCIe capability structure.

### -field DeviceCapabilities

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_device_capabilities_register">PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER</a> structure that describes the PCIe device capabilities register of the PCIe capability structure.

### -field DeviceControl

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_device_control_register">PCI_EXPRESS_DEVICE_CONTROL_REGISTER</a> structure that describes the PCIe device control register of the PCIe capability structure.

### -field DeviceStatus

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_device_status_register">PCI_EXPRESS_DEVICE_STATUS_REGISTER</a> structure that describes the PCIe device status register of the PCIe capability structure.

### -field LinkCapabilities

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_link_capabilities_register">PCI_EXPRESS_LINK_CAPABILITIES_REGISTER</a> structure that describes the PCIe link capabilities register of the PCIe capability structure.

### -field LinkControl

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_link_control_register">PCI_EXPRESS_LINK_CONTROL_REGISTER</a> structure that describes the PCIe link control register of the PCIe capability structure.

### -field LinkStatus

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_link_status_register">PCI_EXPRESS_LINK_STATUS_REGISTER</a> structure that describes the PCIe link status register of the PCIe capability structure.

### -field SlotCapabilities

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_slot_capabilities_register">PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER</a> structure that describes the PCIe slot capabilities register of the PCIe capability structure.

### -field SlotControl

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_slot_control_register">PCI_EXPRESS_SLOT_CONTROL_REGISTER</a> structure that describes the PCIe slot control register of the PCIe capability structure.

### -field SlotStatus

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_slot_status_register">PCI_EXPRESS_SLOT_STATUS_REGISTER</a> structure that describes the PCIe slot status register of the PCIe capability structure.

### -field RootControl

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_root_control_register">PCI_EXPRESS_ROOT_CONTROL_REGISTER</a> structure that describes the PCIe root control register of the PCIe capability structure.

### -field RootCapabilities

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_root_capabilities_register">PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER</a> structure that describes the PCIe root capabilities register of the PCIe capability structure.

### -field RootStatus

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_root_status_register">PCI_EXPRESS_ROOT_STATUS_REGISTER</a> structure that describes the PCIe root status register of the PCIe capability structure.

### -field DeviceCapabilities2

### -field DeviceControl2

### -field DeviceStatus2

## -syntax

```cpp
typedef struct _PCI_EXPRESS_CAPABILITY {
  PCI_CAPABILITIES_HEADER                  Header;
  PCI_EXPRESS_CAPABILITIES_REGISTER        ExpressCapabilities;
  PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER DeviceCapabilities;
  PCI_EXPRESS_DEVICE_CONTROL_REGISTER      DeviceControl;
  PCI_EXPRESS_DEVICE_STATUS_REGISTER       DeviceStatus;
  PCI_EXPRESS_LINK_CAPABILITIES_REGISTER   LinkCapabilities;
  PCI_EXPRESS_LINK_CONTROL_REGISTER        LinkControl;
  PCI_EXPRESS_LINK_STATUS_REGISTER         LinkStatus;
  PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER   SlotCapabilities;
  PCI_EXPRESS_SLOT_CONTROL_REGISTER        SlotControl;
  PCI_EXPRESS_SLOT_STATUS_REGISTER         SlotStatus;
  PCI_EXPRESS_ROOT_CONTROL_REGISTER        RootControl;
  PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER   RootCapabilities;
  PCI_EXPRESS_ROOT_STATUS_REGISTER         RootStatus;
} PCI_EXPRESS_CAPABILITY, *PPCI_EXPRESS_CAPABILITY;
```

## -remarks

The PCI_EXPRESS_CAPABILITY structure is available in Windows Server 2008 and later versions of Windows.

For additional information about the PCIe capability structure, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=69486">PCI Express Specification</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_device_capabilities_register">PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_link_capabilities_register">PCI_EXPRESS_LINK_CAPABILITIES_REGISTER</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_root_capabilities_register">PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_root_status_register">PCI_EXPRESS_ROOT_STATUS_REGISTER</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_root_control_register">PCI_EXPRESS_ROOT_CONTROL_REGISTER</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_device_control_register">PCI_EXPRESS_DEVICE_CONTROL_REGISTER</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_device_status_register">PCI_EXPRESS_DEVICE_STATUS_REGISTER</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capabilities_register">PCI_EXPRESS_CAPABILITIES_REGISTER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_capabilities_header">PCI_CAPABILITIES_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_slot_capabilities_register">PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_link_status_register">PCI_EXPRESS_LINK_STATUS_REGISTER</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_slot_control_register">PCI_EXPRESS_SLOT_CONTROL_REGISTER</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_link_control_register">PCI_EXPRESS_LINK_CONTROL_REGISTER</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_slot_status_register">PCI_EXPRESS_SLOT_STATUS_REGISTER</a>
