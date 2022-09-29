---
UID: NS:miniport._PCI_EXPRESS_ROOT_CONTROL_REGISTER
title: PCI_EXPRESS_ROOT_CONTROL_REGISTER (miniport.h)
description: The _PCI_EXPRESS_ROOT_CONTROL_REGISTER union (miniport.h) describes a PCI Express (PCIe) root control register of a PCIe capability structure.
tech.root: PCI
ms.date: 07/18/2022
keywords: ["PCI_EXPRESS_ROOT_CONTROL_REGISTER structure"]
ms.keywords: "*PPCI_EXPRESS_ROOT_CONTROL_REGISTER, PCI.pci_express_root_control_register, PCI_EXPRESS_ROOT_CONTROL_REGISTER, PCI_EXPRESS_ROOT_CONTROL_REGISTER union [Buses], PPCI_EXPRESS_ROOT_CONTROL_REGISTER, PPCI_EXPRESS_ROOT_CONTROL_REGISTER union pointer [Buses], _PCI_EXPRESS_ROOT_CONTROL_REGISTER, ntddk/PCI_EXPRESS_ROOT_CONTROL_REGISTER, ntddk/PPCI_EXPRESS_ROOT_CONTROL_REGISTER, pci_struct_ef335e30-c046-4066-8411-27bf96cbcd08.xml"
req.header: miniport.h
req.include-header: Ntddk.h, Miniport.h
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
req.typenames: PCI_EXPRESS_ROOT_CONTROL_REGISTER, *PPCI_EXPRESS_ROOT_CONTROL_REGISTER
f1_keywords:
 - _PCI_EXPRESS_ROOT_CONTROL_REGISTER
 - miniport/_PCI_EXPRESS_ROOT_CONTROL_REGISTER
 - PPCI_EXPRESS_ROOT_CONTROL_REGISTER
 - miniport/PPCI_EXPRESS_ROOT_CONTROL_REGISTER
 - PCI_EXPRESS_ROOT_CONTROL_REGISTER
 - miniport/PCI_EXPRESS_ROOT_CONTROL_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_ROOT_CONTROL_REGISTER
 - PPCI_EXPRESS_ROOT_CONTROL_REGISTER
 - PCI_EXPRESS_ROOT_CONTROL_REGISTER
---

## -description

The **PCI_EXPRESS_ROOT_CONTROL_REGISTER** union describes a PCI Express (PCIe) root control register of a PCIe capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.CorrectableSerrEnable

A single bit that indicates that a system error should be generated if a correctable error is reported by any of the devices in the hierarchy that are associated with this root port or by the root port itself.

### -field DUMMYSTRUCTNAME.NonFatalSerrEnable

A single bit that indicates that a system error should be generated if a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port or by the root port itself.

### -field DUMMYSTRUCTNAME.FatalSerrEnable

A single bit that indicates that a system error should be generated if a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port or by the root port itself.

### -field DUMMYSTRUCTNAME.PMEInterruptEnable

A single bit that indicates that interrupts are enabled for power management events.

### -field DUMMYSTRUCTNAME.CRSSoftwareVisibilityEnable

A single bit that indicates that the root port is enabled to return configuration request retry status (CRS) completion status to software.

### -field DUMMYSTRUCTNAME.Rsvd

Reserved.

### -field AsUSHORT

A **USHORT** representation of the contents of the **PCI_EXPRESS_ROOT_CONTROL_REGISTER** structure.

## -remarks

The **PCI_EXPRESS_ROOT_CONTROL_REGISTER** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_ROOT_CONTROL_REGISTER** structure is contained in the [PCI_EXPRESS_CAPABILITY](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability) structure.

## -see-also

[PCI_EXPRESS_CAPABILITY](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability)
