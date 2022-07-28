---
UID: NS:miniport._PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
title: PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY (miniport.h)
description: The _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY union (miniport.h) describes a PCI Express (PCIe) secondary uncorrectable error severity register.
tech.root: PCI
ms.date: 07/19/2022
keywords: ["PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY structure"]
ms.keywords: "*PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, PCI.pci_express_sec_uncorrectable_error_severity, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY union [Buses], PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY union pointer [Buses], _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, pci_struct_94eb07f5-9b90-414b-a331-075c61f507a4.xml, wdm/PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, wdm/PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY"
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
req.typenames: PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
f1_keywords:
 - _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
 - miniport/_PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
 - PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
 - miniport/PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
 - PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
 - miniport/PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
 - PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
 - PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
---

## -description

The **PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY** union describes a PCI Express (PCIe) secondary uncorrectable error severity register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.TargetAbortOnSplitCompletion

A single bit that indicates that a reported target abort on split completion is a fatal error.

### -field DUMMYSTRUCTNAME.MasterAbortOnSplitCompletion

A single bit that indicates that a reported master abort on split completion is a fatal error.

### -field DUMMYSTRUCTNAME.ReceivedTargetAbort

A single bit that indicates that a reported target abort is a fatal error.

### -field DUMMYSTRUCTNAME.ReceivedMasterAbort

A single bit that indicates that a reported master abort is a fatal error.

### -field DUMMYSTRUCTNAME.RsvdZ

Reserved.

### -field DUMMYSTRUCTNAME.UnexpectedSplitCompletionError

A single bit that indicates that a reported unexpected split completion error is a fatal error.

### -field DUMMYSTRUCTNAME.UncorrectableSplitCompletion

A single bit that indicates that a reported uncorrectable split completion message data error is a fatal error.

### -field DUMMYSTRUCTNAME.UncorrectableDataError

A single bit that indicates that a reported uncorrectable data error is a fatal error.

### -field DUMMYSTRUCTNAME.UncorrectableAttributeError

A single bit that indicates that a reported uncorrectable attribute error is a fatal error.

### -field DUMMYSTRUCTNAME.UncorrectableAddressError

A single bit that indicates that a reported uncorrectable address error is a fatal error.

### -field DUMMYSTRUCTNAME.DelayedTransactionDiscardTimerExpired

A single bit that indicates that an expiration of the delayed transaction discard timer is a fatal error.

### -field DUMMYSTRUCTNAME.PERRAsserted

A single bit that indicates that a reported PERR# assertion is a fatal error.

### -field DUMMYSTRUCTNAME.SERRAsserted

A single bit that indicates that a reported SERR# assertion is a fatal error.

### -field DUMMYSTRUCTNAME.InternalBridgeError

A single bit that indicates that a reported internal bridge error is a fatal error.

### -field DUMMYSTRUCTNAME.Reserved

Reserved.

### -field AsULONG

A ULONG representation of the contents of the **PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS** structure.

## -remarks

The **PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY** structure is contained in the [PCI_EXPRESS_BRIDGE_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability) structure.

## -see-also

[PCI_EXPRESS_BRIDGE_AER_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability)
