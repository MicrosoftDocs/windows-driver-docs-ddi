---
UID: NS:ntddk._PCI_EXPRESS_LINK_STATUS_2_REGISTER
tech.root: kernel
title: PCI_EXPRESS_LINK_STATUS_2_REGISTER (ntddk.h)
ms.date: 03/28/2022
targetos: Windows
description: This topic describes the PCI_EXPRESS_LINK_STATUS_2_REGISTER union.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.include-header: Ntddk.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: PCI_EXPRESS_LINK_STATUS_2_REGISTER, *PPCI_EXPRESS_LINK_STATUS_2_REGISTER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_LINK_STATUS_2_REGISTER
 - PPCI_EXPRESS_LINK_STATUS_2_REGISTER
 - PCI_EXPRESS_LINK_STATUS_2_REGISTER
f1_keywords:
 - _PCI_EXPRESS_LINK_STATUS_2_REGISTER
 - ntddk/_PCI_EXPRESS_LINK_STATUS_2_REGISTER
 - PPCI_EXPRESS_LINK_STATUS_2_REGISTER
 - ntddk/PPCI_EXPRESS_LINK_STATUS_2_REGISTER
 - PCI_EXPRESS_LINK_STATUS_2_REGISTER
 - ntddk/PCI_EXPRESS_LINK_STATUS_2_REGISTER
dev_langs:
 - c++
helpviewer_keywords:
 - _PCI_EXPRESS_LINK_STATUS_2_REGISTER
---

## -description

**PCI_EXPRESS_LINK_STATUS_2_REGISTER** describes a PCI Express (PCIe) link status 2 register of a PCIe capability structure. Currently, all fields are reserved and not supported in Windows.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field DUMMYSTRUCTNAME.Rsvd0_15

### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_LINK_STATUS_2_REGISTER structure.

## -remarks

A **PCI_EXPRESS_LINK_STATUS_2_REGISTER** structure is contained in the [PCI_EXPRESS_CAPABILITY_REGISTER](ns-ntddk-_pci_express_capability.md) structure.

## -see-also

[PCI_EXPRESS_CAPABILITY_REGISTER](ns-ntddk-_pci_express_capability.md)

[PCI_EXPRESS_LINK_STATUS_REGISTER](./ns-ntddk-_pci_express_link_status_register.md)

