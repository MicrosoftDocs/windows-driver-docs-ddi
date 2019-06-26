---
UID: NS:miniport._PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
title: _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK (miniport.h)
description: The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) secondary uncorrectable error mask register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_sec_uncorrectable_error_mask.htm
tech.root: PCI
ms.assetid: 99387bcc-301d-4406-bcff-fb5569c88c90
ms.date: 02/24/2018
ms.keywords: "*PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, PCI.pci_express_sec_uncorrectable_error_mask, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK union [Buses], PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK union pointer [Buses], _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, pci_struct_80f14fae-7c43-4a78-bdb7-211abd0e43fd.xml, wdm/PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, wdm/PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK"
ms.topic: struct
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
- PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
product:
- Windows
targetos: Windows
req.typenames: PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
---

# _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure


## -description


The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) secondary uncorrectable error mask register of a PCIe advanced error reporting capability structure.


## -syntax


```cpp
typedef union _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK {
  struct {
    ULONG TargetAbortOnSplitCompletion  :1;
    ULONG MasterAbortOnSplitCompletion  :1;
    ULONG ReceivedTargetAbort  :1;
    ULONG ReceivedMasterAbort  :1;
    ULONG RsvdZ  :1;
    ULONG UnexpectedSplitCompletionError  :1;
    ULONG UncorrectableSplitCompletion  :1;
    ULONG UncorrectableDataError  :1;
    ULONG UncorrectableAttributeError  :1;
    ULONG UncorrectableAddressError  :1;
    ULONG DelayedTransactionDiscardTimerExpired  :1;
    ULONG PERRAsserted  :1;
    ULONG SERRAsserted  :1;
    ULONG InternalBridgeError  :1;
    ULONG Reserved  :18;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK;
```


## -struct-fields




### -field DUMMYSTRUCTNAME




### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure.


#### - DelayedTransactionDiscardTimerExpired

A single bit that indicates that the reporting of the expiration of the delayed transaction discard timer is masked.


#### - InternalBridgeError

A single bit that indicates that the reporting of internal bridge errors is masked.


#### - MasterAbortOnSplitCompletion

A single bit that indicates that the reporting of master aborts on split completion is masked.


#### - PERRAsserted

A single bit that indicates that the reporting of PERR# assertions is masked.


#### - ReceivedMasterAbort

A single bit that indicates that the reporting of master aborts is masked.


#### - ReceivedTargetAbort

A single bit that indicates that the reporting of target aborts is masked.


#### - Reserved

Reserved for system use.


#### - RsvdZ

Reserved for system use.


#### - SERRAsserted

A single bit that indicates that the reporting of SERR# assertions is masked.


#### - TargetAbortOnSplitCompletion

A single bit that indicates that the reporting of target aborts on split completion is masked.


#### - UncorrectableAddressError

A single bit that indicates that the reporting of uncorrectable address errors is masked.


#### - UncorrectableAttributeError

A single bit that indicates that the reporting of uncorrectable attribute errors is masked.


#### - UncorrectableDataError

A single bit that indicates that the reporting of uncorrectable data errors is masked.


#### - UncorrectableSplitCompletion

A single bit that indicates that the reporting of uncorrectable split completion message data errors is masked.


#### - UnexpectedSplitCompletionError

A single bit that indicates that the reporting of unexpected split completion errors is masked.


## -remarks



The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure is contained in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a> structure.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>



 

 


