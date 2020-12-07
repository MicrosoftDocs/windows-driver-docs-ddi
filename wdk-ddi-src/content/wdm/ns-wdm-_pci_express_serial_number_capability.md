---
UID: NS:wdm._PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
title: _PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY (wdm.h)
description: The PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure describes a serial number for a PCI Express (PCIe) device.
old-location: pci\pci_express_serial_number_capability.htm
tech.root: PCI
ms.date: 02/24/2018
keywords: ["PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure"]
ms.keywords: "*PPCI_EXPRESS_SERIAL_NUMBER_CAPABILITY, PCI.pci_express_serial_number_capability, PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY, PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure [Buses], PPCI_EXPRESS_SERIAL_NUMBER_CAPABILITY, PPCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure pointer [Buses], _PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY, pci_struct_0d9ab097-6980-40b4-8c25-02ad8239588b.xml, wdm/PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY, wdm/PPCI_EXPRESS_SERIAL_NUMBER_CAPABILITY"
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h, Miniport.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY, *PPCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
req.product: Windows 10 or later.
f1_keywords:
 - _PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
 - wdm/_PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
 - PPCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
 - wdm/PPCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
 - PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
 - wdm/PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
---

# _PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure (wdm.h)


## -description

The PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure describes a serial number for a PCI Express (PCIe) device.

## -struct-fields

### -field Header

A <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_enhanced_capability_header">PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER</a> structure that describes the header for this structure.

### -field LowSerialNumber

The lower 32 bits of the serial number.

### -field HighSerialNumber

The upper 32 bits of the serial number.

## -syntax

```cpp
typedef struct _PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY {
  PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER Header;
  ULONG                                  LowSerialNumber;
  ULONG                                  HighSerialNumber;
} PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY, *PPCI_EXPRESS_SERIAL_NUMBER_CAPABILITY;
```

## -remarks

The PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure is available in Windows Server 2008 and later versions of Windows.

The PCIe device serial number capability is an optional extended capability that can be implemented by any PCIe device. The device serial number is a 64-bit value that is unique for a given PCIe device.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_enhanced_capability_header">PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER</a>
