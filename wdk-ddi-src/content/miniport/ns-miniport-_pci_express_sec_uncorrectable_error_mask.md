---
UID: NS:miniport._PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
title: PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK (miniport.h)
description: The _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK union (miniport.h) describes a PCI Express (PCIe) secondary uncorrectable error mask register.
tech.root: PCI
ms.date: 07/19/2022
keywords: ["PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure"]
ms.keywords: "*PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, PCI.pci_express_sec_uncorrectable_error_mask, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK union [Buses], PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK union pointer [Buses], _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, pci_struct_80f14fae-7c43-4a78-bdb7-211abd0e43fd.xml, wdm/PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, wdm/PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK"
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
req.typenames: PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
f1_keywords:
 - _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
 - miniport/_PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
 - PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
 - miniport/PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
 - PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
 - miniport/PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
 - PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
 - PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
---

## -description

The **PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK** union describes a PCI Express (PCIe) secondary uncorrectable error mask register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.TargetAbortOnSplitCompletion

A single bit that indicates that the reporting of target aborts on split completion is masked.

### -field DUMMYSTRUCTNAME.MasterAbortOnSplitCompletion

A single bit that indicates that the reporting of master aborts on split completion is masked.

### -field DUMMYSTRUCTNAME.ReceivedTargetAbort

A single bit that indicates that the reporting of target aborts is masked.

### -field DUMMYSTRUCTNAME.ReceivedMasterAbort

A single bit that indicates that the reporting of master aborts is masked.

### -field DUMMYSTRUCTNAME.RsvdZ

Reserved.

### -field DUMMYSTRUCTNAME.UnexpectedSplitCompletionError

A single bit that indicates that the reporting of unexpected split completion errors is masked.

### -field DUMMYSTRUCTNAME.UncorrectableSplitCompletion

A single bit that indicates that the reporting of uncorrectable split completion message data errors is masked.

### -field DUMMYSTRUCTNAME.UncorrectableDataError

A single bit that indicates that the reporting of uncorrectable data errors is masked.

### -field DUMMYSTRUCTNAME.UncorrectableAttributeError

A single bit that indicates that the reporting of uncorrectable attribute errors is masked.

### -field DUMMYSTRUCTNAME.UncorrectableAddressError

A single bit that indicates that the reporting of uncorrectable address errors is masked.

### -field DUMMYSTRUCTNAME.DelayedTransactionDiscardTimerExpired

A single bit that indicates that the reporting of the expiration of the delayed transaction discard timer is masked.

### -field DUMMYSTRUCTNAME.PERRAsserted

A single bit that indicates that the reporting of PERR# assertions is masked.

### -field DUMMYSTRUCTNAME.SERRAsserted

A single bit that indicates that the reporting of SERR# assertions is masked.

### -field DUMMYSTRUCTNAME.InternalBridgeError

A single bit that indicates that the reporting of internal bridge errors is masked.

### -field DUMMYSTRUCTNAME.Reserved

Reserved.

### -field AsULONG

A ULONG representation of the contents of the **PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK** structure.

## -remarks

The **PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK** structure is contained in the [PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md) structure.

## -see-also

[PCI_EXPRESS_BRIDGE_AER_CAPABILITY](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md)