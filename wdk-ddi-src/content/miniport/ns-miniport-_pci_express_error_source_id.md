---
UID: NS:miniport._PCI_EXPRESS_ERROR_SOURCE_ID
title: _PCI_EXPRESS_ERROR_SOURCE_ID (miniport.h)
description: The PCI_EXPRESS_ERROR_SOURCE_ID structure describes the identifiers of the first correctable error and the first uncorrectable error that are reported in the PCI Express (PCIe) root error status register.
old-location: pci\pci_express_error_source_id.htm
tech.root: PCI
ms.date: 02/24/2018
keywords: ["PCI_EXPRESS_ERROR_SOURCE_ID structure"]
ms.keywords: "*PPCI_EXPRESS_ERROR_SOURCE_ID, PCI.pci_express_error_source_id, PCI_EXPRESS_ERROR_SOURCE_ID, PCI_EXPRESS_ERROR_SOURCE_ID union [Buses], PPCI_EXPRESS_ERROR_SOURCE_ID, PPCI_EXPRESS_ERROR_SOURCE_ID union pointer [Buses], _PCI_EXPRESS_ERROR_SOURCE_ID, pci_struct_f111f61b-46a0-450d-bbce-172f125a6903.xml, wdm/PCI_EXPRESS_ERROR_SOURCE_ID, wdm/PPCI_EXPRESS_ERROR_SOURCE_ID"
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
req.typenames: PCI_EXPRESS_ERROR_SOURCE_ID, *PPCI_EXPRESS_ERROR_SOURCE_ID
f1_keywords:
 - _PCI_EXPRESS_ERROR_SOURCE_ID
 - miniport/_PCI_EXPRESS_ERROR_SOURCE_ID
 - PPCI_EXPRESS_ERROR_SOURCE_ID
 - miniport/PPCI_EXPRESS_ERROR_SOURCE_ID
 - PCI_EXPRESS_ERROR_SOURCE_ID
 - miniport/PCI_EXPRESS_ERROR_SOURCE_ID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PCI_EXPRESS_ERROR_SOURCE_ID
---

# _PCI_EXPRESS_ERROR_SOURCE_ID structure (miniport.h)


## -description

The PCI_EXPRESS_ERROR_SOURCE_ID structure describes the identifiers of the first correctable error and the first uncorrectable error that are reported in the PCI Express (PCIe) root error status register.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_ERROR_SOURCE_ID structure.


#### - CorrectableSourceIdBus

The bus number of the requester that reported the first correctable error.


#### - CorrectableSourceIdDev

The device number of the requester that reported the first correctable error.


#### - CorrectableSourceIdFun

The function number of the requester that reported the first correctable error.


#### - UncorrectableSourceIdBus

The bus number of the requester that reported the first uncorrectable error.


#### - UncorrectableSourceIdDev

The device number of the requester that reported the first uncorrectable error.


#### - UncorrectableSourceIdFun

The function number of the requester that reported the first uncorrectable error.

## -syntax

```cpp
typedef union _PCI_EXPRESS_ERROR_SOURCE_ID {
  struct {
    USHORT CorrectableSourceIdFun  :3;
    USHORT CorrectableSourceIdDev  :5;
    USHORT CorrectableSourceIdBus  :8;
    USHORT UncorrectableSourceIdFun  :3;
    USHORT UncorrectableSourceIdDev  :5;
    USHORT UncorrectableSourceIdBus  :8;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_ERROR_SOURCE_ID, *PPCI_EXPRESS_ERROR_SOURCE_ID;
```

## -remarks

The PCI_EXPRESS_ERROR_SOURCE_ID structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_ERROR_SOURCE_ID structure is contained in the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>
