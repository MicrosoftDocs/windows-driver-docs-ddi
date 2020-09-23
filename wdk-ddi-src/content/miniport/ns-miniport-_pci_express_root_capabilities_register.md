---
UID: NS:miniport._PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER
title: _PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER (miniport.h)
description: The PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) root capabilities register of a PCIe capability structure.
old-location: pci\pci_express_root_capabilities_register.htm
tech.root: PCI
ms.assetid: d4e6cc35-f6f1-4983-b4d6-2a524245fd15
ms.date: 02/24/2018
keywords: ["PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure"]
ms.keywords: "*PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, PCI.pci_express_root_capabilities_register, PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER union [Buses], PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER union pointer [Buses], _PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, ntddk/PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, ntddk/PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, pci_struct_5b1d9283-10c9-40dc-8dc2-552ab7a2cab5.xml"
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
req.typenames: PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, *PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER
f1_keywords:
 - _PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER
 - miniport/_PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER
 - PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER
 - miniport/PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER
 - PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER
 - miniport/PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER
---

# _PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure (miniport.h)


## -description

The PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) root capabilities register of a PCIe capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure.


#### - CRSSoftwareVisibility

A single bit that indicates that the root port is capable of returning configuration request retry status (CRS) completion status to software.


#### - Rsvd

Reserved.

## -syntax

```cpp
typedef union _PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER {
  struct {
    USHORT CRSSoftwareVisibility  :1;
    USHORT Rsvd  :15;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, *PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER;
```

## -remarks

The PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure is contained in the <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability">PCI_EXPRESS_CAPABILITY</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability">PCI_EXPRESS_CAPABILITY</a>