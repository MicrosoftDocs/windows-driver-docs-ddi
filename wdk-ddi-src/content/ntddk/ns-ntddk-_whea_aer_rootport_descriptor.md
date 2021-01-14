---
UID: NS:ntddk._WHEA_AER_ROOTPORT_DESCRIPTOR
title: _WHEA_AER_ROOTPORT_DESCRIPTOR (ntddk.h)
description: The WHEA_AER_ROOTPORT_DESCRIPTOR structure describes a PCI Express (PCIe) root port error source.
old-location: whea\whea_aer_rootport_descriptor.htm
tech.root: whea
ms.date: 02/20/2018
keywords: ["WHEA_AER_ROOTPORT_DESCRIPTOR structure"]
ms.keywords: "*PWHEA_AER_ROOTPORT_DESCRIPTOR, PWHEA_AER_ROOTPORT_DESCRIPTOR, PWHEA_AER_ROOTPORT_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_AER_ROOTPORT_DESCRIPTOR, WHEA_AER_ROOTPORT_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_AER_ROOTPORT_DESCRIPTOR, ntddk/PWHEA_AER_ROOTPORT_DESCRIPTOR, ntddk/WHEA_AER_ROOTPORT_DESCRIPTOR, whea.whea_aer_rootport_descriptor, whearef_e96777a4-ff19-4291-9730-ffe4c9828381.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.typenames: WHEA_AER_ROOTPORT_DESCRIPTOR, *PWHEA_AER_ROOTPORT_DESCRIPTOR
f1_keywords:
 - _WHEA_AER_ROOTPORT_DESCRIPTOR
 - ntddk/_WHEA_AER_ROOTPORT_DESCRIPTOR
 - PWHEA_AER_ROOTPORT_DESCRIPTOR
 - ntddk/PWHEA_AER_ROOTPORT_DESCRIPTOR
 - WHEA_AER_ROOTPORT_DESCRIPTOR
 - ntddk/WHEA_AER_ROOTPORT_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_AER_ROOTPORT_DESCRIPTOR
 - PWHEA_AER_ROOTPORT_DESCRIPTOR
 - WHEA_AER_ROOTPORT_DESCRIPTOR
---

# _WHEA_AER_ROOTPORT_DESCRIPTOR structure


## -description

The WHEA_AER_ROOTPORT_DESCRIPTOR structure describes a PCI Express (PCIe) root port error source.

## -struct-fields

### -field Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_AERROOTPORT.

### -field Enabled

A Boolean value that indicates if the error source is enabled.

### -field Reserved

Reserved for system use.

### -field BusNumber

The root port's bus number.

### -field Slot

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pci_slot_number">WHEA_PCI_SLOT_NUMBER</a> structure that describes the logical PCI slot where the root port is located in the system.

### -field DeviceControl

The contents of the root port's Device Control register.

### -field Flags

An AER_ROOTPORT_DESCRIPTOR_FLAGS union that indicates which of the members of the WHEA_AER_ROOTPORT_DESCRIPTOR structure can be written to by the operating system. The AER_ROOTPORT_DESCRIPTOR_FLAGS union is defined as follows:


```
typedef union _AER_ROOTPORT_DESCRIPTOR_FLAGS {
  struct {
    USHORT  UncorrectableErrorMaskRW:1;
    USHORT  UncorrectableErrorSeverityRW:1;
    USHORT  CorrectableErrorMaskRW:1;
    USHORT  AdvancedCapsAndControlRW:1;
    USHORT  RootErrorCommandRW:1;
    USHORT  Reserved:11;
  };
  USHORT  AsUSHORT;
} AER_ROOTPORT_DESCRIPTOR_FLAGS, *PAER_ROOTPORT_DESCRIPTOR_FLAGS
```





#### UncorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the <b>UncorrectableErrorMask</b> member of the WHEA_AER_ROOTPORT_DESCRIPTOR structure.



#### UncorrectableErrorSeverityRW

A single bit that indicates that the operating system can write to the <b>UncorrectableErrorSeverity </b>member of the WHEA_AER_ROOTPORT_DESCRIPTOR structure.



#### CorrectableErrorMaskRW

A single bit that indicates that the operating system can write to the <b>CorrectableErrorMask</b> member of the WHEA_AER_ROOTPORT_DESCRIPTOR structure.



#### AdvancedCapsAndControlRW

A single bit that indicates that the operating system can write to the <b>AdvancedCapsAndControl</b> member of the WHEA_AER_ROOTPORT_DESCRIPTOR structure.



#### RootErrorCommandRW

A single bit that indicates that the operating system can write to the <b>RootErrorCommand</b> member of the WHEA_AER_ROOTPORT_DESCRIPTOR structure.



#### Reserved

Reserved for system use.



#### AsUSHORT

A USHORT representation of the contents of the AER_ROOTPORT_DESCRIPTOR_FLAGS union.

### -field UncorrectableErrorMask

The contents of the root port's Uncorrectable Error Mask register.

### -field UncorrectableErrorSeverity

The contents of the root port's Uncorrectable Error Severity register.

### -field CorrectableErrorMask

The contents of the root port's Correctable Error Mask register.

### -field AdvancedCapsAndControl

The contents of the root port's Advanced Error Capabilities and Control register.

### -field RootErrorCommand

The contents of the root port's Root Error Command register.

## -remarks

A WHEA_AER_ROOTPORT_DESCRIPTOR structure is contained within the <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pci_slot_number">WHEA_PCI_SLOT_NUMBER</a>

