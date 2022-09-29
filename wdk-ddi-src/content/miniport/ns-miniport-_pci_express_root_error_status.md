---
UID: NS:miniport._PCI_EXPRESS_ROOT_ERROR_STATUS
title: PCI_EXPRESS_ROOT_ERROR_STATUS (miniport.h)
description: The _PCI_EXPRESS_ROOT_ERROR_STATUS union (miniport.h) describes a PCI Express (PCIe) root error status register for advanced error reporting.
tech.root: PCI
ms.date: 07/18/2022
keywords: ["PCI_EXPRESS_ROOT_ERROR_STATUS structure"]
ms.keywords: "*PPCI_EXPRESS_ROOT_ERROR_STATUS, PCI.pci_express_root_error_status, PCI_EXPRESS_ROOT_ERROR_STATUS, PCI_EXPRESS_ROOT_ERROR_STATUS union [Buses], PPCI_EXPRESS_ROOT_ERROR_STATUS, PPCI_EXPRESS_ROOT_ERROR_STATUS union pointer [Buses], _PCI_EXPRESS_ROOT_ERROR_STATUS, pci_struct_8b730780-dc4a-4873-8efd-fb6df47f7c8f.xml, wdm/PCI_EXPRESS_ROOT_ERROR_STATUS, wdm/PPCI_EXPRESS_ROOT_ERROR_STATUS"
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
req.typenames: PCI_EXPRESS_ROOT_ERROR_STATUS, *PPCI_EXPRESS_ROOT_ERROR_STATUS
f1_keywords:
 - _PCI_EXPRESS_ROOT_ERROR_STATUS
 - miniport/_PCI_EXPRESS_ROOT_ERROR_STATUS
 - PPCI_EXPRESS_ROOT_ERROR_STATUS
 - miniport/PPCI_EXPRESS_ROOT_ERROR_STATUS
 - PCI_EXPRESS_ROOT_ERROR_STATUS
 - miniport/PCI_EXPRESS_ROOT_ERROR_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_ROOT_ERROR_STATUS
 - PPCI_EXPRESS_ROOT_ERROR_STATUS
 - PCI_EXPRESS_ROOT_ERROR_STATUS
---

## -description

The **PCI_EXPRESS_ROOT_ERROR_STATUS** structure describes a PCI Express (PCIe) root error status register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.CorrectableErrorReceived

A single bit that indicates that a correctable error message has been received.

### -field DUMMYSTRUCTNAME.MultipleCorrectableErrorsReceived

A single bit that indicates that multiple correctable error messages have been received.

### -field DUMMYSTRUCTNAME.UncorrectableErrorReceived

A single bit that indicates that an uncorrectable error message has been received.

### -field DUMMYSTRUCTNAME.MultipleUncorrectableErrorsReceived

A single bit that indicates that multiple uncorrectable error messages have been received.

### -field DUMMYSTRUCTNAME.FirstUncorrectableFatal

A single bit that indicates that the first uncorrectable error message that was received was for a fatal error.

### -field DUMMYSTRUCTNAME.NonFatalErrorMessagesReceived

A single bit that indicates that one or more non-fatal uncorrectable error messages have been received.

### -field DUMMYSTRUCTNAME.FatalErrorMessagesReceived

A single bit that indicates that one or more non-fatal uncorrectable error messages have been received.

### -field DUMMYSTRUCTNAME.Reserved

Reserved.

### -field DUMMYSTRUCTNAME.AdvancedErrorInterruptMessageNumber

The MSI/MSI-X vector that is used for the interrupt messages that are generated in association with any of the status bits of the advanced error reporting capability.

### -field AsULONG

A **ULONG** representation of the contents of the **PCI_EXPRESS_ROOT_ERROR_STATUS** structure.

## -remarks

The **PCI_EXPRESS_ROOT_ERROR_STATUS** union is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_ROOT_ERROR_STATUS** union is contained in the [PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability) structure.

## -see-also

[PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability)
