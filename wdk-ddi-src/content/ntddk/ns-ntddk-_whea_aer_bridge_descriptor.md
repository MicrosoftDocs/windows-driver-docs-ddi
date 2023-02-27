---
UID: NS:ntddk._WHEA_AER_BRIDGE_DESCRIPTOR
title: WHEA_AER_BRIDGE_DESCRIPTOR (ntddk.h)
description: The WHEA_AER_BRIDGE_DESCRIPTOR structure describes a PCI Express (PCIe) bridge error source.
tech.root: whea
ms.date: 01/11/2023
keywords: ["WHEA_AER_BRIDGE_DESCRIPTOR structure"]
ms.keywords: "*PWHEA_AER_BRIDGE_DESCRIPTOR, PWHEA_AER_BRIDGE_DESCRIPTOR, PWHEA_AER_BRIDGE_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_AER_BRIDGE_DESCRIPTOR, WHEA_AER_BRIDGE_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_AER_BRIDGE_DESCRIPTOR, ntddk/PWHEA_AER_BRIDGE_DESCRIPTOR, ntddk/WHEA_AER_BRIDGE_DESCRIPTOR, whea.whea_aer_bridge_descriptor, whearef_52e2fbef-c8d7-42c8-b8ae-584fbc4f622f.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.typenames: WHEA_AER_BRIDGE_DESCRIPTOR, *PWHEA_AER_BRIDGE_DESCRIPTOR
f1_keywords:
 - _WHEA_AER_BRIDGE_DESCRIPTOR
 - ntddk/_WHEA_AER_BRIDGE_DESCRIPTOR
 - PWHEA_AER_BRIDGE_DESCRIPTOR
 - ntddk/PWHEA_AER_BRIDGE_DESCRIPTOR
 - WHEA_AER_BRIDGE_DESCRIPTOR
 - ntddk/WHEA_AER_BRIDGE_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_AER_BRIDGE_DESCRIPTOR
 - PWHEA_AER_BRIDGE_DESCRIPTOR
 - WHEA_AER_BRIDGE_DESCRIPTOR
---

## -description

The **WHEA_AER_BRIDGE_DESCRIPTOR** structure describes a PCI Express (PCIe) bridge error source.

## -struct-fields

### -field Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_AERBRIDGE.

### -field Enabled

A Boolean value that indicates if the error source is enabled.

### -field Reserved

Reserved for system use.

### -field BusNumber

The bridge's primary bus number.

### -field Slot

A [**WHEA_PCI_SLOT_NUMBER**](./ns-ntddk-_whea_pci_slot_number.md) structure that describes the logical PCI slot where the bridge is located in the system.

### -field DeviceControl

The contents of the bridge's Device Control register.

### -field Flags

An **AER_BRIDGE_DESCRIPTOR_FLAGS** union that indicates which of the members of the **WHEA_AER_BRIDGE_DESCRIPTOR** structure can be written to by the operating system. The AER_BRIDGE_DESCRIPTOR_FLAGS union is defined as follows:

```cpp
typedef union _AER_BRIDGE_DESCRIPTOR_FLAGS {
  struct {
    USHORT  UncorrectableErrorMaskRW:1;
    USHORT  UncorrectableErrorSeverityRW:1;
    USHORT  CorrectableErrorMaskRW:1;
    USHORT  AdvancedCapsAndControlRW:1;
    USHORT  SecondaryUncorrectableErrorMaskRW:1;
    USHORT  SecondaryUncorrectableErrorSevRW:1;
    USHORT  SecondaryCapsAndControlRW:1;
    USHORT  Reserved:9;
  };
  USHORT  AsUSHORT;
} AER_BRIDGE_DESCRIPTOR_FLAGS, *PAER_BRIDGE_DESCRIPTOR_FLAGS
```

#### UncorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the **UncorrectableErrorMask** member of the **WHEA_AER_BRIDGE_DESCRIPTOR** structure.

#### UncorrectableErrorSeverityRW

A single bit that indicates that the operating system can write to the **UncorrectableErrorSeverity** member of the **WHEA_AER_BRIDGE_DESCRIPTOR** structure.

#### CorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the **CorrectableErrorMask** member of the **WHEA_AER_BRIDGE_DESCRIPTOR** structure.

#### AdvancedCapsAndControlRW

A single bit that indicates that the operating system can write to the **AdvancedCapsAndControl** member of the **WHEA_AER_BRIDGE_DESCRIPTOR** structure.

#### SecondaryUncorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the **SecondaryUncorrectableErrorMask** member of the **WHEA_AER_BRIDGE_DESCRIPTOR** structure.

#### SecondaryUncorrectableErrorSevRW

A single bit that indicates that the operating system can write to the **SecondaryUncorrectableErrorSev** member of the **WHEA_AER_BRIDGE_DESCRIPTOR** structure.

#### SecondaryCapsAndControlRW

A single bit that indicates that the operating system can write to the **SecondaryCapsAndControl** member of the **WHEA_AER_BRIDGE_DESCRIPTOR** structure.

#### Reserved

Reserved for system use.

#### AsUSHORT

A USHORT representation of the contents of the **AER_ROOTPORT_DESCRIPTOR_FLAGS** union.

### -field UncorrectableErrorMask

The contents of the bridge's Uncorrectable Error Mask register.

### -field UncorrectableErrorSeverity

The contents of the bridge's Uncorrectable Error Severity register.

### -field CorrectableErrorMask

The contents of the bridge's Correctable Error Mask register.

### -field AdvancedCapsAndControl

The contents of the bridge's Advanced Error Capabilities and Control register.

### -field SecondaryUncorrectableErrorMask

The contents of the bridge's Secondary Uncorrectable Error Mask register.

### -field SecondaryUncorrectableErrorSev

The contents of the bridge's Secondary Uncorrectable Error Severity register.

### -field SecondaryCapsAndControl

The contents of the bridge's Secondary Error Capabilities and Control register.

## -remarks

A **WHEA_AER_BRIDGE_DESCRIPTOR** structure is contained within the [**WHEA_ERROR_SOURCE_DESCRIPTOR**](./ns-ntddk-_whea_error_source_descriptor.md) structure.

## -see-also

[**WHEA_ERROR_SOURCE_DESCRIPTOR**](./ns-ntddk-_whea_error_source_descriptor.md)

[**WHEA_PCI_SLOT_NUMBER**](./ns-ntddk-_whea_pci_slot_number.md)