---
UID: NS:wdm._PCI_EXPRESS_ERROR_SOURCE_ID
title: _PCI_EXPRESS_ERROR_SOURCE_ID (wdm.h)
description: The PCI_EXPRESS_ERROR_SOURCE_ID structure describes the identifiers of the first correctable error and the first uncorrectable error that are reported in the PCI Express (PCIe) root error status register.
old-location: pci\pci_express_error_source_id.htm
tech.root: PCI
ms.assetid: 53efddbc-0e65-487c-b406-c7d093ca5667
ms.date: 02/24/2018
keywords: ["_PCI_EXPRESS_ERROR_SOURCE_ID structure"]
ms.keywords: "*PPCI_EXPRESS_ERROR_SOURCE_ID, PCI.pci_express_error_source_id, PCI_EXPRESS_ERROR_SOURCE_ID, PCI_EXPRESS_ERROR_SOURCE_ID union [Buses], PPCI_EXPRESS_ERROR_SOURCE_ID, PPCI_EXPRESS_ERROR_SOURCE_ID union pointer [Buses], _PCI_EXPRESS_ERROR_SOURCE_ID, pci_struct_f111f61b-46a0-450d-bbce-172f125a6903.xml, wdm/PCI_EXPRESS_ERROR_SOURCE_ID, wdm/PPCI_EXPRESS_ERROR_SOURCE_ID"
f1_keywords:
 - "wdm/PCI_EXPRESS_ERROR_SOURCE_ID"
req.header: wdm.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- PCI_EXPRESS_ERROR_SOURCE_ID
product:
- Windows
targetos: Windows
req.typenames: PCI_EXPRESS_ERROR_SOURCE_ID, *PPCI_EXPRESS_ERROR_SOURCE_ID
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_ERROR_SOURCE_ID structure


## -description


The PCI_EXPRESS_ERROR_SOURCE_ID structure describes the identifiers of the first correctable error and the first uncorrectable error that are reported in the PCI Express (PCIe) root error status register.


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


## -remarks



The PCI_EXPRESS_ERROR_SOURCE_ID structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_ERROR_SOURCE_ID structure is contained in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structure.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>



 

 


