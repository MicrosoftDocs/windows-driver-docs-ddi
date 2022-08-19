---
UID: NS:miniport._PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
title: PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK (miniport.h)
description: The _PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure (miniport.h) describes a PCI Express (PCIe) uncorrectable error mask register.
tech.root: PCI
ms.date: 07/19/2022
keywords: ["PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure"]
ms.keywords: "*PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, PCI.pci_express_uncorrectable_error_mask, PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK union [Buses], PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK union pointer [Buses], _PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, pci_struct_309db853-f6d7-4f88-9a73-861d63a1e927.xml, wdm/PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, wdm/PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK"
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
req.typenames: PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
f1_keywords:
 - _PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
 - miniport/_PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
 - PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
 - miniport/PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
 - PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
 - miniport/PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
 - PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
 - PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
---

## -description

The **PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK** union describes a PCI Express (PCIe) uncorrectable error mask register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.Undefined

A single bit that contains an undefined value. In versions of the *PCIe Specification* prior to version 1.1, this bit indicates that the reporting of link training errors is masked.

### -field DUMMYSTRUCTNAME.Reserved1

Reserved.

### -field DUMMYSTRUCTNAME.DataLinkProtocolError

A single bit that indicates that the reporting of data link protocol errors is masked.

### -field DUMMYSTRUCTNAME.SurpriseDownError

A single bit that indicates that the reporting of surprise down errors is masked.

### -field DUMMYSTRUCTNAME.Reserved2

Reserved.

### -field DUMMYSTRUCTNAME.PoisonedTLP

A single bit that indicates that the reporting of poisoned transaction layer packets (TLPs) is masked.

### -field DUMMYSTRUCTNAME.FlowControlProtocolError

A single bit that indicates that the reporting of flow control protocol errors is masked.

### -field DUMMYSTRUCTNAME.CompletionTimeout

A single bit that indicates that the reporting of completion timeouts is masked.

### -field DUMMYSTRUCTNAME.CompleterAbort

A single bit that indicates that the reporting of completer aborts is masked.

### -field DUMMYSTRUCTNAME.UnexpectedCompletion

A single bit that indicates that the reporting of unexpected completions is masked.

### -field DUMMYSTRUCTNAME.ReceiverOverflow

A single bit that indicates that the reporting of receiver overflows is masked.

### -field DUMMYSTRUCTNAME.MalformedTLP

A single bit that indicates that the reporting of malformed transaction layer packets (TLPs) is masked.

### -field DUMMYSTRUCTNAME.ECRCError

A single bit that indicates that the reporting of end-to-end cyclic redundancy check (ECRC) errors is masked.

### -field DUMMYSTRUCTNAME.UnsupportedRequestError

A single bit that indicates that the reporting of unsupported request errors is masked.

### -field DUMMYSTRUCTNAME.AcsViolation

Defines the **ULONG** member **AcsViolation**.

### -field DUMMYSTRUCTNAME.UncorrectableInternalError

Defines the **ULONG** member **UncorrectableInternalError**.

### -field DUMMYSTRUCTNAME.MCBlockedTlp

Defines the **ULONG** member **MCBlockedTlp**.

### -field DUMMYSTRUCTNAME.AtomicOpEgressBlocked

Defines the **ULONG** member **AtomicOpEgressBlocked**.

### -field DUMMYSTRUCTNAME.TlpPrefixBlocked

Defines the **ULONG** member **TlpPrefixBlocked**.

### -field DUMMYSTRUCTNAME.Reserved3

Reserved.

### -field AsULONG

A **ULONG** representation of the contents of the **PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK** structure.

## -remarks

The **PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK** structure is contained in the [PCI_EXPRESS_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_aer_capability.md), [PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md), and [PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_rootport_aer_capability.md) structures.

## -see-also

[PCI_EXPRESS_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_aer_capability.md)

[PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md)

[PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_rootport_aer_capability.md)