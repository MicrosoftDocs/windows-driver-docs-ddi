---
UID: NS:miniport._PCI_EXPRESS_ROOT_STATUS_REGISTER
title: PCI_EXPRESS_ROOT_STATUS_REGISTER (miniport.h)
description: The _PCI_EXPRESS_ROOT_STATUS_REGISTER union (miniport.h) describes a PCI Express (PCIe) root status register of a PCIe capability structure.
tech.root: PCI
ms.date: 07/18/2022
keywords: ["PCI_EXPRESS_ROOT_STATUS_REGISTER structure"]
ms.keywords: "*PPCI_EXPRESS_ROOT_STATUS_REGISTER, PCI.pci_express_root_status_register, PCI_EXPRESS_ROOT_STATUS_REGISTER, PCI_EXPRESS_ROOT_STATUS_REGISTER union [Buses], PPCI_EXPRESS_ROOT_STATUS_REGISTER, PPCI_EXPRESS_ROOT_STATUS_REGISTER union pointer [Buses], _PCI_EXPRESS_ROOT_STATUS_REGISTER, ntddk/PCI_EXPRESS_ROOT_STATUS_REGISTER, ntddk/PPCI_EXPRESS_ROOT_STATUS_REGISTER, pci_struct_ff3a211f-421b-41f3-9250-d658636bfe49.xml"
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
req.typenames: PCI_EXPRESS_ROOT_STATUS_REGISTER, *PPCI_EXPRESS_ROOT_STATUS_REGISTER
f1_keywords:
 - _PCI_EXPRESS_ROOT_STATUS_REGISTER
 - miniport/_PCI_EXPRESS_ROOT_STATUS_REGISTER
 - PPCI_EXPRESS_ROOT_STATUS_REGISTER
 - miniport/PPCI_EXPRESS_ROOT_STATUS_REGISTER
 - PCI_EXPRESS_ROOT_STATUS_REGISTER
 - miniport/PCI_EXPRESS_ROOT_STATUS_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_ROOT_STATUS_REGISTER
 - PPCI_EXPRESS_ROOT_STATUS_REGISTER
 - PCI_EXPRESS_ROOT_STATUS_REGISTER
---

## -description

The **PCI_EXPRESS_ROOT_STATUS_REGISTER** union describes a PCI Express (PCIe) root status register of a PCIe capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.PMERequestorId

A [PCI_EXPRESS_PME_REQUESTOR_ID](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_pme_requestor_id) structure that describes the power management event (PME) requester identifier of the last PME requester.

### -field DUMMYSTRUCTNAME.PMEStatus

A single bit that indicates that a power management event (PME) was asserted by the requester identified by the **PMERequestorId** member.

### -field DUMMYSTRUCTNAME.PMEPending

A single bit that indicates that another power management event (PME) is pending while the **PMEStatus** bit is set.

### -field DUMMYSTRUCTNAME.Rsvd

Reserved.

### -field AsULONG

A **ULONG** representation of the contents of the **PCI_EXPRESS_ROOT_STATUS_REGISTER** structure.

## -remarks

The **PCI_EXPRESS_ROOT_STATUS_REGISTER** union is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_ROOT_STATUS_REGISTER** union is contained in the [PCI_EXPRESS_CAPABILITY](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability) structure.

## -see-also

[PCI_EXPRESS_CAPABILITY](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability)

[PCI_EXPRESS_PME_REQUESTOR_ID](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_pme_requestor_id)
