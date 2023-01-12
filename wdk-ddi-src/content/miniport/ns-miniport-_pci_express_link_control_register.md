---
UID: NS:miniport._PCI_EXPRESS_LINK_CONTROL_REGISTER
title: PCI_EXPRESS_LINK_CONTROL_REGISTER (miniport.h)
description: The _PCI_EXPRESS_LINK_CONTROL_REGISTER union (miniport.h) describes a PCI Express (PCIe) link control register of a PCIe capability structure.
tech.root: PCI
ms.date: 07/18/2022
keywords: ["PCI_EXPRESS_LINK_CONTROL_REGISTER structure"]
ms.keywords: "*PPCI_EXPRESS_LINK_CONTROL_REGISTER, PCI.pci_express_link_control_register, PCI_EXPRESS_LINK_CONTROL_REGISTER, PCI_EXPRESS_LINK_CONTROL_REGISTER union [Buses], PPCI_EXPRESS_LINK_CONTROL_REGISTER, PPCI_EXPRESS_LINK_CONTROL_REGISTER union pointer [Buses], _PCI_EXPRESS_LINK_CONTROL_REGISTER, ntddk/PCI_EXPRESS_LINK_CONTROL_REGISTER, ntddk/PPCI_EXPRESS_LINK_CONTROL_REGISTER, pci_struct_0fc5be0f-aae8-4d59-a569-030eb593e927.xml"
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
req.typenames: PCI_EXPRESS_LINK_CONTROL_REGISTER, *PPCI_EXPRESS_LINK_CONTROL_REGISTER
f1_keywords:
 - _PCI_EXPRESS_LINK_CONTROL_REGISTER
 - miniport/_PCI_EXPRESS_LINK_CONTROL_REGISTER
 - PPCI_EXPRESS_LINK_CONTROL_REGISTER
 - miniport/PPCI_EXPRESS_LINK_CONTROL_REGISTER
 - PCI_EXPRESS_LINK_CONTROL_REGISTER
 - miniport/PCI_EXPRESS_LINK_CONTROL_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_LINK_CONTROL_REGISTER
 - PPCI_EXPRESS_LINK_CONTROL_REGISTER
 - PCI_EXPRESS_LINK_CONTROL_REGISTER
---

## -description

The **PCI_EXPRESS_LINK_CONTROL_REGISTER** union describes a PCI Express (PCIe) link control register of a PCIe capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.ActiveStatePMControl

The level of active state power management that is enabled on the PCIe link. Possible values are:

**L0sAndL1EntryDisabled**  
L0s and L1 are both disabled.

**L0sEntryEnabled**  
L0s is enabled.

**L1EntryEnabled**  
L1 is enabled.

**L0sAndL1EntryEnabled**  
L0s and L1 are both enabled.

### -field DUMMYSTRUCTNAME.Rsvd1

Reserved.

### -field DUMMYSTRUCTNAME.ReadCompletionBoundary

The read completion boundary (RCB) value for the root port or the root port upstream from the endpoint. If the bit is clear, the RCB is 64 byte. If the bit is set, the RCB is 128 byte. This member is not applicable for switch ports.

### -field DUMMYSTRUCTNAME.LinkDisable

A single bit that indicates that the link is disabled. This member is not applicable for endpoint devices, PCIe-to-PCI or PCI-X bridges, and upstream ports of switches.

### -field DUMMYSTRUCTNAME.RetrainLink

A single bit that is used to initiate retraining of the link. Reads of this bit always return zero. This member is not applicable for endpoint devices, PCIe-to-PCI or PCI-X bridges, and upstream ports of switches.

### -field DUMMYSTRUCTNAME.CommonClockConfig

A single bit that indicates that this component and the component at the opposite end of the link are operating with a distributed common reference clock. If this bit is clear, this component and the component at the opposite end of the link are operating with an asynchronous reference clock.

### -field DUMMYSTRUCTNAME.ExtendedSynch

A single bit that indicates that additional ordered sets are transmitted when exiting the L0s state and when in the recovery state.

### -field DUMMYSTRUCTNAME.EnableClockPowerManagement

A single bit that indicates that clock power management is enabled.

### -field DUMMYSTRUCTNAME.Rsvd2

Reserved.

### -field AsUSHORT

A **USHORT** representation of the contents of the **PCI_EXPRESS_LINK_CONTROL_REGISTER** structure.

## -remarks

The **PCI_EXPRESS_LINK_CONTROL_REGISTER** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_LINK_CONTROL_REGISTER** structure is contained in the [PCI_EXPRESS_CAPABILITY](../ntddk/ns-ntddk-_pci_express_capability.md) structure.

## -see-also

[PCI_EXPRESS_CAPABILITY](../ntddk/ns-ntddk-_pci_express_capability.md)