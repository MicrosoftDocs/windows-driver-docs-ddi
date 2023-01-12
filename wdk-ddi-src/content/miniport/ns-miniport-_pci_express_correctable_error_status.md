---
UID: NS:miniport._PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
title: PCI_EXPRESS_CORRECTABLE_ERROR_STATUS (miniport.h)
description: The _PCI_EXPRESS_CORRECTABLE_ERROR_STATUS union (miniport.h) describes a PCI Express (PCIe) correctable error status register for advanced error reporting.
tech.root: PCI
ms.date: 07/18/2022
keywords: ["PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure"]
ms.keywords: "*PPCI_CORRECTABLE_ERROR_STATUS, PCI.pci_express_correctable_error_status, PCI_EXPRESS_CORRECTABLE_ERROR_STATUS, PCI_EXPRESS_CORRECTABLE_ERROR_STATUS union [Buses], PPCI_CORRECTABLE_ERROR_STATUS, PPCI_CORRECTABLE_ERROR_STATUS union pointer [Buses], _PCI_EXPRESS_CORRECTABLE_ERROR_STATUS, pci_struct_1366a090-7405-4cd8-b725-19753a248441.xml, wdm/PCI_EXPRESS_CORRECTABLE_ERROR_STATUS, wdm/PPCI_CORRECTABLE_ERROR_STATUS"
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
req.typenames: PCI_EXPRESS_CORRECTABLE_ERROR_STATUS, *PPCI_CORRECTABLE_ERROR_STATUS
f1_keywords:
 - _PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
 - miniport/_PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
 - PPCI_CORRECTABLE_ERROR_STATUS
 - miniport/PPCI_CORRECTABLE_ERROR_STATUS
 - PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
 - miniport/PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
 - PPCI_CORRECTABLE_ERROR_STATUS
 - PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
---

## -description

The **PCI_EXPRESS_CORRECTABLE_ERROR_STATUS** union describes a PCI Express (PCIe) correctable error status register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.ReceiverError

A single bit that indicates that a receiver error has occurred.

### -field DUMMYSTRUCTNAME.Reserved1

Reserved.

### -field DUMMYSTRUCTNAME.BadTLP

A single bit that indicates that a bad transaction layer packet (TLP) error has occurred.

### -field DUMMYSTRUCTNAME.BadDLLP

A single bit that indicates that a bad data link layer packet (DLLP) error has occurred.

### -field DUMMYSTRUCTNAME.ReplayNumRollover

A single bit that indicates that the counter that counts the number of times the retry buffer has been re-transmitted has rolled over.

### -field DUMMYSTRUCTNAME.Reserved2

Reserved.

### -field DUMMYSTRUCTNAME.ReplayTimerTimeout

A single bit that indicates that the replay timer has timed out.

### -field DUMMYSTRUCTNAME.AdvisoryNonFatalError

A single bit that indicates that an advisory non-fatal error has occurred.

### -field DUMMYSTRUCTNAME.CorrectedInternalError

Defines the **ULONG** member **CorrectedInternalError**.

### -field DUMMYSTRUCTNAME.HeaderLogOverflow

Defines the **ULONG** member **HeaderLogOverflow**.

### -field DUMMYSTRUCTNAME.Reserved3

Reserved.

### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure.

## -remarks

The PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure is contained in the [PCI_EXPRESS_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_aer_capability.md), [PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md), and [PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_rootport_aer_capability.md) structures.

## -see-also

[PCI_EXPRESS_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_aer_capability.md)

[PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md)

[PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_rootport_aer_capability.md)