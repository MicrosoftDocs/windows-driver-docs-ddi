---
UID: NS:miniport._PCI_EXPRESS_CORRECTABLE_ERROR_MASK
title: PCI_EXPRESS_CORRECTABLE_ERROR_MASK (miniport.h)
description: The _PCI_EXPRESS_CORRECTABLE_ERROR_MASK union (miniport.h) describes a PCI Express (PCIe) correctable error mask register used in advanced error reporting.
tech.root: PCI
ms.date: 07/18/2022
keywords: ["PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure"]
ms.keywords: "*PPCI_CORRECTABLE_ERROR_MASK, PCI.pci_express_correctable_error_mask, PCI_EXPRESS_CORRECTABLE_ERROR_MASK, PCI_EXPRESS_CORRECTABLE_ERROR_MASK union [Buses], PPCI_CORRECTABLE_ERROR_MASK, PPCI_CORRECTABLE_ERROR_MASK union pointer [Buses], _PCI_EXPRESS_CORRECTABLE_ERROR_MASK, pci_struct_770185be-12f9-4519-8077-6d90e8344590.xml, wdm/PCI_EXPRESS_CORRECTABLE_ERROR_MASK, wdm/PPCI_CORRECTABLE_ERROR_MASK"
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
req.typenames: PCI_EXPRESS_CORRECTABLE_ERROR_MASK, *PPCI_CORRECTABLE_ERROR_MASK
f1_keywords:
 - _PCI_EXPRESS_CORRECTABLE_ERROR_MASK
 - miniport/_PCI_EXPRESS_CORRECTABLE_ERROR_MASK
 - PPCI_CORRECTABLE_ERROR_MASK
 - miniport/PPCI_CORRECTABLE_ERROR_MASK
 - PCI_EXPRESS_CORRECTABLE_ERROR_MASK
 - miniport/PCI_EXPRESS_CORRECTABLE_ERROR_MASK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_CORRECTABLE_ERROR_MASK
 - PPCI_CORRECTABLE_ERROR_MASK
 - PCI_EXPRESS_CORRECTABLE_ERROR_MASK
---

## -description

The PCI_EXPRESS_CORRECTABLE_ERROR_MASK union describes a PCI Express (PCIe) correctable error mask register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.ReceiverError

A single bit that indicates that the reporting of receiver errors is masked.

### -field DUMMYSTRUCTNAME.Reserved1

Reserved.

### -field DUMMYSTRUCTNAME.BadTLP

A single bit that indicates that the reporting of bad transaction layer packets (TLPs) is masked.

### -field DUMMYSTRUCTNAME.BadDLLP

A single bit that indicates that the reporting of bad data link layer packets (DLLPs) is masked.

### -field DUMMYSTRUCTNAME.ReplayNumRollover

A single bit that indicates that the reporting of rollovers of the counter that counts the number of times the retry buffer has been re-transmitted is masked.

### -field DUMMYSTRUCTNAME.Reserved2

Reserved.

### -field DUMMYSTRUCTNAME.ReplayTimerTimeout

A single bit that indicates that the reporting of timeouts of the replay timer is masked.

### -field DUMMYSTRUCTNAME.AdvisoryNonFatalError

A single bit that indicates that the reporting of advisory non-fatal errors is masked.

### -field DUMMYSTRUCTNAME.CorrectedInternalError

Defines the **ULONG** member **CorrectedInternalError**.

### -field DUMMYSTRUCTNAME.HeaderLogOverflow

Defines the **ULONG** member **HeaderLogOverflow**.

### -field DUMMYSTRUCTNAME.Reserved3

Reserved.

### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_CORRECTABLE_ERROR_MASK union.

## -remarks

The PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure is contained in the [PCI_EXPRESS_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_aer_capability.md), [PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md), and [PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_rootport_aer_capability.md) structures.

## -see-also

[PCI_EXPRESS_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_aer_capability.md)

[PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md)

[PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_rootport_aer_capability.md)