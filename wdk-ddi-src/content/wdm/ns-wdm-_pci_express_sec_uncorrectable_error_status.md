---
UID: NS:wdm._PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
title: "_PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS"
author: windows-driver-content
description: The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) secondary uncorrectable error status register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_sec_uncorrectable_error_status.htm
old-project: PCI
ms.assetid: 8f6b1764-e2c0-4c9e-a2ec-56cc19520d2e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS union [Buses], *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS union pointer [Buses], _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, wdm/PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, wdm/PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, pci_struct_cb52bea2-b001-47a7-bad9-9816787133d3.xml, PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, PCI.pci_express_sec_uncorrectable_error_status, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
product: Windows
targetos: Windows
req.typenames: PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure


## -description


The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) secondary uncorrectable error status register of a PCIe advanced error reporting capability structure.


## -syntax


````
typedef union _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS {
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
} PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.TargetAbortOnSplitCompletion

A single bit that indicates that a target abort on split completion has occurred.


### -field DUMMYSTRUCTNAME.MasterAbortOnSplitCompletion

A single bit that indicates that a master abort on split completion has occurred.


### -field DUMMYSTRUCTNAME.ReceivedTargetAbort

A single bit that indicates that a target abort has been received.


### -field DUMMYSTRUCTNAME.ReceivedMasterAbort

A single bit that indicates that a master abort has been received.


### -field DUMMYSTRUCTNAME.RsvdZ

Reserved for system use.


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

Reserved for system use.


### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure.


## -remarks



The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a> structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

