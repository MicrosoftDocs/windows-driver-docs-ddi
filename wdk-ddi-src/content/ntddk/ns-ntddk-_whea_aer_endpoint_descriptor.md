---
UID: NS:ntddk._WHEA_AER_ENDPOINT_DESCRIPTOR
title: WHEA_AER_ENDPOINT_DESCRIPTOR (ntddk.h)
description: The WHEA_AER_ENDPOINT_DESCRIPTOR structure describes a PCI Express (PCIe) endpoint error source.
tech.root: whea
ms.date: 01/11/2023
keywords: ["WHEA_AER_ENDPOINT_DESCRIPTOR structure"]
ms.keywords: "*PWHEA_AER_ENDPOINT_DESCRIPTOR, PWHEA_AER_ENDPOINT_DESCRIPTOR, PWHEA_AER_ENDPOINT_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_AER_ENDPOINT_DESCRIPTOR, WHEA_AER_ENDPOINT_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_AER_ENDPOINT_DESCRIPTOR, ntddk/PWHEA_AER_ENDPOINT_DESCRIPTOR, ntddk/WHEA_AER_ENDPOINT_DESCRIPTOR, whea.whea_aer_endpoint_descriptor, whearef_06cb1486-51b0-457d-a0d0-b902c6c43cfc.xml"
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
req.typenames: WHEA_AER_ENDPOINT_DESCRIPTOR, *PWHEA_AER_ENDPOINT_DESCRIPTOR
f1_keywords:
 - _WHEA_AER_ENDPOINT_DESCRIPTOR
 - ntddk/_WHEA_AER_ENDPOINT_DESCRIPTOR
 - PWHEA_AER_ENDPOINT_DESCRIPTOR
 - ntddk/PWHEA_AER_ENDPOINT_DESCRIPTOR
 - WHEA_AER_ENDPOINT_DESCRIPTOR
 - ntddk/WHEA_AER_ENDPOINT_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_AER_ENDPOINT_DESCRIPTOR
 - PWHEA_AER_ENDPOINT_DESCRIPTOR
 - WHEA_AER_ENDPOINT_DESCRIPTOR
---

## -description

The **WHEA_AER_ENDPOINT_DESCRIPTOR** structure describes a PCI Express (PCIe) endpoint error source.

## -struct-fields

### -field Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_AERENDPOINT.

### -field Enabled

A Boolean value that indicates if the error source is enabled.

### -field Reserved

Reserved for system use.

### -field BusNumber

The endpoint's bus number.

### -field Slot

A [**WHEA_PCI_SLOT_NUMBER**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pci_slot_number) structure that describes the logical PCI slot where the endpoint is located in the system.

### -field DeviceControl

The contents of the endpoint's Device Control register.

### -field Flags

An AER_ENDPOINT_DESCRIPTOR_FLAGS union that indicates which of the members of the **WHEA_AER_ENDPOINT_DESCRIPTOR** structure can be written to by the operating system. The **AER_ENDPOINT_DESCRIPTOR_FLAGS** union is defined as follows:

```cpp
typedef union _AER_ENDPOINT_DESCRIPTOR_FLAGS {
  struct {
    USHORT  UncorrectableErrorMaskRW:1;
    USHORT  UncorrectableErrorSeverityRW:1;
    USHORT  CorrectableErrorMaskRW:1;
    USHORT  AdvancedCapsAndControlRW:1;
    USHORT  Reserved:12;
  };
  USHORT  AsUSHORT;
} AER_ENDPOINT_DESCRIPTOR_FLAGS, *PAER_ENDPOINT_DESCRIPTOR_FLAGS
```

#### UncorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the **UncorrectableErrorMask** member of the **WHEA_AER_ENDPOINT_DESCRIPTOR** structure.

#### UncorrectableErrorSeverityRW

A single bit that indicates that the operating system can write to the **UncorrectableErrorSeverity** member of the **WHEA_AER_ENDPOINT_DESCRIPTOR** structure.

#### CorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the **CorrectableErrorMask** member of the **WHEA_AER_ENDPOINT_DESCRIPTOR** structure.

#### AdvancedCapsAndControlRW

A single bit that indicates that the operating system can write to the **AdvancedCapsAndControl** member of the **WHEA_AER_ENDPOINT_DESCRIPTOR** structure.

#### Reserved

Reserved for system use.

#### AsUSHORT

A USHORT representation of the contents of the **AER_ENDPOINT_DESCRIPTOR_FLAGS** union.

### -field UncorrectableErrorMask

The contents of the endpoint's Uncorrectable Error Mask register.

### -field UncorrectableErrorSeverity

The contents of the endpoint's Uncorrectable Error Severity register.

### -field CorrectableErrorMask

The contents of the endpoint's Correctable Error Mask register.

### -field AdvancedCapsAndControl

The contents of the endpoint's Advanced Error Capabilities and Control register.

## -remarks

A **WHEA_AER_ENDPOINT_DESCRIPTOR** structure is contained within the [**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor) structure.

## -see-also

[**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor)

[**WHEA_PCI_SLOT_NUMBER**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pci_slot_number)
