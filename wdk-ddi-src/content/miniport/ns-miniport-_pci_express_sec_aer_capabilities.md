---
UID: NS:miniport._PCI_EXPRESS_SEC_AER_CAPABILITIES
title: PCI_EXPRESS_SEC_AER_CAPABILITIES (miniport.h)
description: The _PCI_EXPRESS_SEC_AER_CAPABILITIES union (miniport.h) describes a PCI Express (PCIe) secondary error capabilities and control register.
tech.root: PCI
ms.date: 07/19/2022
keywords: ["PCI_EXPRESS_SEC_AER_CAPABILITIES structure"]
ms.keywords: "*PPCI_EXPRESS_SEC_AER_CAPABILITIES, PCI.pci_express_sec_aer_capabilities, PCI_EXPRESS_SEC_AER_CAPABILITIES, PCI_EXPRESS_SEC_AER_CAPABILITIES union [Buses], PPCI_EXPRESS_SEC_AER_CAPABILITIES, PPCI_EXPRESS_SEC_AER_CAPABILITIES union pointer [Buses], _PCI_EXPRESS_SEC_AER_CAPABILITIES, pci_struct_22bcb7f0-e690-414b-ba51-37c8783a6fad.xml, wdm/PCI_EXPRESS_SEC_AER_CAPABILITIES, wdm/PPCI_EXPRESS_SEC_AER_CAPABILITIES"
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
req.typenames: PCI_EXPRESS_SEC_AER_CAPABILITIES, *PPCI_EXPRESS_SEC_AER_CAPABILITIES
f1_keywords:
 - _PCI_EXPRESS_SEC_AER_CAPABILITIES
 - miniport/_PCI_EXPRESS_SEC_AER_CAPABILITIES
 - PPCI_EXPRESS_SEC_AER_CAPABILITIES
 - miniport/PPCI_EXPRESS_SEC_AER_CAPABILITIES
 - PCI_EXPRESS_SEC_AER_CAPABILITIES
 - miniport/PCI_EXPRESS_SEC_AER_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_SEC_AER_CAPABILITIES
 - PPCI_EXPRESS_SEC_AER_CAPABILITIES
 - PCI_EXPRESS_SEC_AER_CAPABILITIES
---

## -description

The **PCI_EXPRESS_SEC_AER_CAPABILITIES** union describes a PCI Express (PCIe) secondary error capabilities and control register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.SecondaryUncorrectableFirstErrorPtr

The bit position of the first error that was reported in the PCIe secondary uncorrectable error status register.

### -field DUMMYSTRUCTNAME.Reserved

Reserved.

### -field AsULONG

A ULONG representation of the contents of the **PCI_EXPRESS_SEC_AER_CAPABILITIES** union.

## -remarks

The **PCI_EXPRESS_SEC_AER_CAPABILITIES** union is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_SEC_AER_CAPABILITIES** union is contained in the [PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md) structure.

## -see-also

[PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md)