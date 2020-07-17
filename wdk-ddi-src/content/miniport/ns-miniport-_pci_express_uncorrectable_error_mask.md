---
UID: NS:miniport._PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
title: _PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK (miniport.h)
description: The PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) uncorrectable error mask register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_uncorrectable_error_mask.htm
tech.root: PCI
ms.assetid: 0dfc6e49-5556-4163-abef-b00a26a7a2ad
ms.date: 02/24/2018
keywords: ["_PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure"]
ms.keywords: "*PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, PCI.pci_express_uncorrectable_error_mask, PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK union [Buses], PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK union pointer [Buses], _PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, pci_struct_309db853-f6d7-4f88-9a73-861d63a1e927.xml, wdm/PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, wdm/PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK"
f1_keywords:
 - "miniport/PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK"
 - "PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
product:
- Windows
targetos: Windows
req.typenames: PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
---

# _PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure


## -description


The PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) uncorrectable error mask register of a PCIe advanced error reporting capability structure.


## -syntax


```cpp
typedef union _PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK {
  struct {
    ULONG Undefined  :1;
    ULONG Reserved1  :3;
    ULONG DataLinkProtocolError  :1;
    ULONG SurpriseDownError  :1;
    ULONG Reserved2  :6;
    ULONG PoisonedTLP  :1;
    ULONG FlowControlProtocolError  :1;
    ULONG CompletionTimeout  :1;
    ULONG CompleterAbort  :1;
    ULONG UnexpectedCompletion  :1;
    ULONG ReceiverOverflow  :1;
    ULONG MalformedTLP  :1;
    ULONG ECRCError  :1;
    ULONG UnsupportedRequestError  :1;
    ULONG Reserved3  :11;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK;
```


## -struct-fields




### -field DUMMYSTRUCTNAME




### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure.


#### - CompleterAbort

A single bit that indicates that the reporting of completer aborts is masked.


#### - CompletionTimeout

A single bit that indicates that the reporting of completion timeouts is masked.


#### - DataLinkProtocolError

A single bit that indicates that the reporting of data link protocol errors is masked.


#### - ECRCError

A single bit that indicates that the reporting of end-to-end cyclic redundancy check (ECRC) errors is masked.


#### - FlowControlProtocolError

A single bit that indicates that the reporting of flow control protocol errors is masked.


#### - MalformedTLP

A single bit that indicates that the reporting of malformed transaction layer packets (TLPs) is masked.


#### - PoisonedTLP

A single bit that indicates that the reporting of poisoned transaction layer packets (TLPs) is masked.


#### - ReceiverOverflow

A single bit that indicates that the reporting of receiver overflows is masked.


#### - Reserved1

Reserved.


#### - Reserved2

Reserved.


#### - Reserved3

Reserved.


#### - SurpriseDownError

A single bit that indicates that the reporting of surprise down errors is masked.


#### - Undefined

A single bit that contains an undefined value. In versions of the <i>PCIe Specification</i> prior to version 1.1, this bit indicates that the reporting of link training errors is masked.


#### - UnexpectedCompletion

A single bit that indicates that the reporting of unexpected completions is masked.


#### - UnsupportedRequestError

A single bit that indicates that the reporting of unsupported request errors is masked.


## -remarks



The PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure is contained in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structures.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability">PCI_EXPRESS_AER_CAPABILITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>



 

 


