---
UID: NS:miniport._PCI_EXPRESS_ROOT_ERROR_COMMAND
title: PCI_EXPRESS_ROOT_ERROR_COMMAND (miniport.h)
description: The _PCI_EXPRESS_ROOT_ERROR_COMMAND union (miniport.h) describes a PCI Express (PCIe) root error command register for advanced error reporting.
tech.root: PCI
ms.date: 07/18/2022
keywords: ["PCI_EXPRESS_ROOT_ERROR_COMMAND structure"]
ms.keywords: "*PPCI_EXPRESS_ROOT_ERROR_COMMAND, PCI.pci_express_root_error_command, PCI_EXPRESS_ROOT_ERROR_COMMAND, PCI_EXPRESS_ROOT_ERROR_COMMAND union [Buses], PPCI_EXPRESS_ROOT_ERROR_COMMAND, PPCI_EXPRESS_ROOT_ERROR_COMMAND union pointer [Buses], _PCI_EXPRESS_ROOT_ERROR_COMMAND, pci_struct_f7834746-d8b5-4765-8434-8f7837a47871.xml, wdm/PCI_EXPRESS_ROOT_ERROR_COMMAND, wdm/PPCI_EXPRESS_ROOT_ERROR_COMMAND"
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
req.typenames: PCI_EXPRESS_ROOT_ERROR_COMMAND, *PPCI_EXPRESS_ROOT_ERROR_COMMAND
f1_keywords:
 - _PCI_EXPRESS_ROOT_ERROR_COMMAND
 - miniport/_PCI_EXPRESS_ROOT_ERROR_COMMAND
 - PPCI_EXPRESS_ROOT_ERROR_COMMAND
 - miniport/PPCI_EXPRESS_ROOT_ERROR_COMMAND
 - PCI_EXPRESS_ROOT_ERROR_COMMAND
 - miniport/PCI_EXPRESS_ROOT_ERROR_COMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_ROOT_ERROR_COMMAND
 - PPCI_EXPRESS_ROOT_ERROR_COMMAND
 - PCI_EXPRESS_ROOT_ERROR_COMMAND
---

## -description

The **PCI_EXPRESS_ROOT_ERROR_COMMAND** union describes a PCI Express (PCIe) root error command register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.CorrectableErrorReportingEnable

A single bit that indicates that interrupts are enabled for when a correctable error is reported by any of the devices in the hierarchy that are associated with this root port.

### -field DUMMYSTRUCTNAME.NonFatalErrorReportingEnable

A single bit that indicates that interrupts are enabled for when a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port.

### -field DUMMYSTRUCTNAME.FatalErrorReportingEnable

A single bit that indicates that interrupts are enabled for when a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port.

### -field DUMMYSTRUCTNAME.Reserved

Reserved.

### -field AsULONG

A **ULONG** representation of the contents of the **PCI_EXPRESS_ROOT_ERROR_COMMAND** structure.

## -remarks

The **PCI_EXPRESS_ROOT_ERROR_COMMAND** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_ROOT_ERROR_COMMAND** structure is contained in the [PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability) structure.

## -see-also

[PCI_EXPRESS_ROOTPORT_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability)
