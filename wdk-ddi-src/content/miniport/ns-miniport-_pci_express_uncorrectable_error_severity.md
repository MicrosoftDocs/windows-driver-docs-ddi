---
UID: NS:miniport._PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
title: PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY (miniport.h)
description: The _PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY union (miniport.h) describes a PCI Express (PCIe) uncorrectable error severity register.
tech.root: PCI
ms.date: 07/19/2022
keywords: ["PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure"]
ms.keywords: "*PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, PCI.pci_express_uncorrectable_error_severity, PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY union [Buses], PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY union pointer [Buses], _PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, pci_struct_49aec790-2c99-489c-b0ca-0653ebe5b52c.xml, wdm/PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, wdm/PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY"
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
req.typenames: PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
f1_keywords:
 - _PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
 - miniport/_PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
 - PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
 - miniport/PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
 - PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
 - miniport/PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
 - PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
 - PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
---

## -description

The **PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY** union describes a PCI Express (PCIe) uncorrectable error severity register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.Undefined

A single bit that contains an undefined value. In versions of the <i>PCIe Specification</i> prior to version 1.1, this bit indicates that a reported link training error is a fatal error.

### -field DUMMYSTRUCTNAME.Reserved1

Reserved.

### -field DUMMYSTRUCTNAME.DataLinkProtocolError

A single bit that indicates that a reported data link protocol error is a fatal error.

### -field DUMMYSTRUCTNAME.SurpriseDownError

A single bit that indicates that a reported surprise down error is a fatal error.

### -field DUMMYSTRUCTNAME.Reserved2

Reserved.

### -field DUMMYSTRUCTNAME.PoisonedTLP

A single bit that indicates that a reported poisoned transaction layer packet (TLP) is a fatal error.

### -field DUMMYSTRUCTNAME.FlowControlProtocolError

A single bit that indicates that a reported flow control protocol error is a fatal error.

### -field DUMMYSTRUCTNAME.CompletionTimeout

A single bit that indicates that a reported completion timeout is a fatal error.

### -field DUMMYSTRUCTNAME.CompleterAbort

A single bit that indicates that a reported completer abort is a fatal error.

### -field DUMMYSTRUCTNAME.UnexpectedCompletion

A single bit that indicates that a reported unexpected completion is a fatal error.

### -field DUMMYSTRUCTNAME.ReceiverOverflow

A single bit that indicates that a reported receiver overflow is a fatal error.

### -field DUMMYSTRUCTNAME.MalformedTLP

A single bit that indicates that a reported malformed transaction layer packet (TLP) is a fatal error.

### -field DUMMYSTRUCTNAME.ECRCError

A single bit that indicates that a reported end-to-end cyclic redundancy check (ECRC) error is a fatal error.

### -field DUMMYSTRUCTNAME.UnsupportedRequestError

A single bit that indicates that a reported unsupported request error is a fatal error.

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

A **ULONG** representation of the contents of the **PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY** structure.

## -remarks

The PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure is contained in the [PCI_EXPRESS_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_aer_capability.md), [PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md), and [PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_rootport_aer_capability.md) structures.

## -see-also

[PCI_EXPRESS_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_aer_capability.md)

[PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md)

[PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_rootport_aer_capability.md)