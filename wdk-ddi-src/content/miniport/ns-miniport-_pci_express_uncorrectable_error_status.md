---
UID: NS:miniport._PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
title: PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS (miniport.h)
description: The _PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS union (miniport.h) describes a PCI Express (PCIe) uncorrectable error status register.
tech.root: PCI
ms.date: 07/20/2022
keywords: ["PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure"]
ms.keywords: "*PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, PCI.pci_express_uncorrectable_error_status, PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS union [Buses], PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS union pointer [Buses], _PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, pci_struct_9341a010-06c8-46ee-931f-2a67756c12d2.xml, wdm/PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, wdm/PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS"
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
req.typenames: PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
f1_keywords:
 - _PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
 - miniport/_PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
 - PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
 - miniport/PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
 - PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
 - miniport/PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
 - PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
 - PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
---

## -description

The PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS union describes a PCI Express (PCIe) uncorrectable error status register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.Undefined

A single bit that contains an undefined value. In versions of the *PCIe Specification* prior to version 1.1, this bit indicates that a link training error has occurred.

### -field DUMMYSTRUCTNAME.Reserved1

Reserved.

### -field DUMMYSTRUCTNAME.DataLinkProtocolError

A single bit that indicates that a data link protocol error has occurred.

### -field DUMMYSTRUCTNAME.SurpriseDownError

A single bit that indicates that a surprise down error has occurred.

### -field DUMMYSTRUCTNAME.Reserved2

Reserved.

### -field DUMMYSTRUCTNAME.PoisonedTLP

A single bit that indicates that a poisoned transaction layer packet (TLP) has been detected.

### -field DUMMYSTRUCTNAME.FlowControlProtocolError

A single bit that indicates that a flow control protocol error has occurred.

### -field DUMMYSTRUCTNAME.CompletionTimeout

A single bit that indicates that a completion timeout has occurred.

### -field DUMMYSTRUCTNAME.CompleterAbort

A single bit that indicates that a completer abort has occurred.

### -field DUMMYSTRUCTNAME.UnexpectedCompletion

A single bit that indicates that an unexpected completion has occurred.

### -field DUMMYSTRUCTNAME.ReceiverOverflow

A single bit that indicates that the receiver has overflowed.

### -field DUMMYSTRUCTNAME.MalformedTLP

A single bit that indicates that a malformed transaction layer packet (TLP) has been detected.

### -field DUMMYSTRUCTNAME.ECRCError

A single bit that indicates that an end-to-end cyclic redundancy check (ECRC) error has occurred.

### -field DUMMYSTRUCTNAME.UnsupportedRequestError

A single bit that indicates that an unsupported request error has occurred.

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

A **ULONG** representation of the contents of the **PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS** structure.

## -remarks

The **PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS** structure is contained in the [PCI_EXPRESS_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_aer_capability.md), [PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md), and [PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_rootport_aer_capability.md) structures.

## -see-also

[PCI_EXPRESS_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_aer_capability.md)

[PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md)

[PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_rootport_aer_capability.md)