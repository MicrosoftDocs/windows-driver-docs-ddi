---
UID: NS:miniport._PCI_EXPRESS_AER_CAPABILITIES
title: PCI_EXPRESS_AER_CAPABILITIES (miniport.h)
description: The _PCI_EXPRESS_AER_CAPABILITIES union (miniport.h) describes a PCI Express (PCIe) advanced error capabilities and control register.
tech.root: PCI
ms.date: 07/18/2022
keywords: ["PCI_EXPRESS_AER_CAPABILITIES structure"]
ms.keywords: "*PPCI_EXPRESS_AER_CAPABILITIES, PCI.pci_express_aer_capabilities, PCI_EXPRESS_AER_CAPABILITIES, PCI_EXPRESS_AER_CAPABILITIES union [Buses], PPCI_EXPRESS_AER_CAPABILITIES, PPCI_EXPRESS_AER_CAPABILITIES union pointer [Buses], _PCI_EXPRESS_AER_CAPABILITIES, pci_struct_e316ea91-d32a-4726-ba80-8fc6bd8e3163.xml, wdm/PCI_EXPRESS_AER_CAPABILITIES, wdm/PPCI_EXPRESS_AER_CAPABILITIES"
req.header: miniport.h
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
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: PCI_EXPRESS_AER_CAPABILITIES, *PPCI_EXPRESS_AER_CAPABILITIES
f1_keywords:
 - _PCI_EXPRESS_AER_CAPABILITIES
 - miniport/_PCI_EXPRESS_AER_CAPABILITIES
 - PPCI_EXPRESS_AER_CAPABILITIES
 - miniport/PPCI_EXPRESS_AER_CAPABILITIES
 - PCI_EXPRESS_AER_CAPABILITIES
 - miniport/PCI_EXPRESS_AER_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_AER_CAPABILITIES
 - PPCI_EXPRESS_AER_CAPABILITIES
 - PCI_EXPRESS_AER_CAPABILITIES
---

## -description

The **PCI_EXPRESS_AER_CAPABILITIES** union describes a PCI Express (PCIe) advanced error capabilities and control register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.FirstErrorPointer

The bit position of the first error that was reported in the PCIe uncorrectable error status register.

### -field DUMMYSTRUCTNAME.ECRCGenerationCapable

A single bit that indicates that the device is capable of generating end-to-end cyclic redundancy checks (ECRC).

### -field DUMMYSTRUCTNAME.ECRCGenerationEnable

A single bit that indicates that ECRC generation is enabled.

### -field DUMMYSTRUCTNAME.ECRCCheckCapable

A single bit that indicates that the device is capable of checking ECRC.

### -field DUMMYSTRUCTNAME.ECRCCheckEnable

A single bit that indicates that ECRC checking is enabled.

### -field DUMMYSTRUCTNAME.MultipleHeaderRecordingCapable

Defines the **ULONG** member **MultipleHeaderRecordingCapable**.

### -field DUMMYSTRUCTNAME.MultipleHeaderRecordingEnable

Defines the **ULONG** member **MultipleHeaderRecordingEnable**.

### -field DUMMYSTRUCTNAME.TlpPrefixLogPresent

Defines the **ULONG** member **TlpPrefixLogPresent**.

### -field DUMMYSTRUCTNAME.Reserved

Reserved for future use.

### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_AER_CAPABILITIES structure.

## -remarks

The PCI_EXPRESS_AER_CAPABILITIES structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_AER_CAPABILITIES structure is contained in the [PCI_EXPRESS_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability), [PCI_EXPRESS_BRIDGE_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability), and [PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability) structures.

## -see-also

[PCI_EXPRESS_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability)

[PCI_EXPRESS_BRIDGE_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability)

[PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability)
