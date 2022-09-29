---
UID: NS:miniport._PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
title: PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS (miniport.h)
description: The _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS union (miniport.h) describes a PCI Express (PCIe) secondary uncorrectable error status register.
tech.root: PCI
ms.date: 07/19/2022
keywords: ["PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure"]
ms.keywords: "*PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, PCI.pci_express_sec_uncorrectable_error_status, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS union [Buses], PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS union pointer [Buses], _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, pci_struct_cb52bea2-b001-47a7-bad9-9816787133d3.xml, wdm/PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, wdm/PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS"
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
req.typenames: PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
f1_keywords:
 - _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
 - miniport/_PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
 - PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
 - miniport/PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
 - PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
 - miniport/PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
 - PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
 - PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
---

## -description

The **PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS** union describes a PCI Express (PCIe) secondary uncorrectable error status register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.TargetAbortOnSplitCompletion

A single bit that indicates that a target abort on split completion has occurred.

### -field DUMMYSTRUCTNAME.MasterAbortOnSplitCompletion

A single bit that indicates that a master abort on split completion has occurred.

### -field DUMMYSTRUCTNAME.ReceivedTargetAbort

A single bit that indicates that a target abort has been received.

### -field DUMMYSTRUCTNAME.ReceivedMasterAbort

A single bit that indicates that a master abort has been received.

### -field DUMMYSTRUCTNAME.RsvdZ

Reserved.

### -field DUMMYSTRUCTNAME.UnexpectedSplitCompletionError

A single bit that indicates that an unexpected split completion error has occurred.

### -field DUMMYSTRUCTNAME.UncorrectableSplitCompletion

A single bit that indicates that an uncorrectable split completion message data error has occurred.

### -field DUMMYSTRUCTNAME.UncorrectableDataError

A single bit that indicates that an uncorrectable data error has occurred.

### -field DUMMYSTRUCTNAME.UncorrectableAttributeError

A single bit that indicates that an uncorrectable attribute error has occurred.

### -field DUMMYSTRUCTNAME.UncorrectableAddressError

A single bit that indicates that an uncorrectable address error has occurred.

### -field DUMMYSTRUCTNAME.DelayedTransactionDiscardTimerExpired

A single bit that indicates that the delayed transaction discard timer has expired.

### -field DUMMYSTRUCTNAME.PERRAsserted

A single bit that indicates that a PERR# assertion was detected.

### -field DUMMYSTRUCTNAME.SERRAsserted

A single bit that indicates that a SERR# assertion was detected.

### -field DUMMYSTRUCTNAME.InternalBridgeError

A single bit that indicates that an internal bridge error has occurred.

### -field DUMMYSTRUCTNAME.Reserved

Reserved.

### -field AsULONG

A ULONG representation of the contents of the **PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS** structure.

## -remarks

The **PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS** structure is contained in the [PCI_EXPRESS_BRIDGE_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability) structure.

## -see-also

[PCI_EXPRESS_BRIDGE_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability)
