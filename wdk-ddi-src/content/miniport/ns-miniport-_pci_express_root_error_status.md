---
UID: NS:miniport._PCI_EXPRESS_ROOT_ERROR_STATUS
title: _PCI_EXPRESS_ROOT_ERROR_STATUS (miniport.h)
description: The PCI_EXPRESS_ROOT_ERROR_STATUS structure describes a PCI Express (PCIe) root error status register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_root_error_status.htm
tech.root: PCI
ms.assetid: 1af0c877-e634-474e-9b4d-a28991fb3f66
ms.date: 02/24/2018
keywords: ["_PCI_EXPRESS_ROOT_ERROR_STATUS structure"]
ms.keywords: "*PPCI_EXPRESS_ROOT_ERROR_STATUS, PCI.pci_express_root_error_status, PCI_EXPRESS_ROOT_ERROR_STATUS, PCI_EXPRESS_ROOT_ERROR_STATUS union [Buses], PPCI_EXPRESS_ROOT_ERROR_STATUS, PPCI_EXPRESS_ROOT_ERROR_STATUS union pointer [Buses], _PCI_EXPRESS_ROOT_ERROR_STATUS, pci_struct_8b730780-dc4a-4873-8efd-fb6df47f7c8f.xml, wdm/PCI_EXPRESS_ROOT_ERROR_STATUS, wdm/PPCI_EXPRESS_ROOT_ERROR_STATUS"
f1_keywords:
 - "miniport/PCI_EXPRESS_ROOT_ERROR_STATUS"
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
- PCI_EXPRESS_ROOT_ERROR_STATUS
product:
- Windows
targetos: Windows
req.typenames: PCI_EXPRESS_ROOT_ERROR_STATUS, *PPCI_EXPRESS_ROOT_ERROR_STATUS
---

# _PCI_EXPRESS_ROOT_ERROR_STATUS structure


## -description


The PCI_EXPRESS_ROOT_ERROR_STATUS structure describes a PCI Express (PCIe) root error status register of a PCIe advanced error reporting capability structure.


## -syntax


```cpp
typedef union _PCI_EXPRESS_ROOT_ERROR_STATUS {
  struct {
    ULONG CorrectableErrorReceived  :1;
    ULONG MultipleCorrectableErrorsReceived  :1;
    ULONG UncorrectableErrorReceived  :1;
    ULONG MultipleUncorrectableErrorsReceived  :1;
    ULONG FirstUncorrectableFatal  :1;
    ULONG NonFatalErrorMessagesReceived  :1;
    ULONG FatalErrorMessagesReceived  :1;
    ULONG Reserved  :20;
    ULONG AdvancedErrorInterruptMessageNumber  :5;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_ROOT_ERROR_STATUS, *PPCI_EXPRESS_ROOT_ERROR_STATUS;
```


## -struct-fields




### -field DUMMYSTRUCTNAME




### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_ROOT_ERROR_STATUS structure.


#### - AdvancedErrorInterruptMessageNumber

The MSI/MSI-X vector that is used for the interrupt messages that are generated in association with any of the status bits of the advanced error reporting capability.


#### - CorrectableErrorReceived

A single bit that indicates that a correctable error message has been received.


#### - FatalErrorMessagesReceived

A single bit that indicates that one or more non-fatal uncorrectable error messages have been received.


#### - FirstUncorrectableFatal

A single bit that indicates that the first uncorrectable error message that was received was for a fatal error.


#### - MultipleCorrectableErrorsReceived

A single bit that indicates that multiple correctable error messages have been received.


#### - MultipleUncorrectableErrorsReceived

A single bit that indicates that multiple uncorrectable error messages have been received.


#### - NonFatalErrorMessagesReceived

A single bit that indicates that one or more non-fatal uncorrectable error messages have been received.


#### - Reserved

Reserved.


#### - UncorrectableErrorReceived

A single bit that indicates that an uncorrectable error message has been received.


## -remarks



The PCI_EXPRESS_ROOT_ERROR_STATUS structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_ROOT_ERROR_STATUS structure is contained in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structure.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>



 

 


