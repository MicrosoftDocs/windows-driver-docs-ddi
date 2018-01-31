---
UID: NS:wdm._PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
title: "_PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK"
author: windows-driver-content
description: The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) secondary uncorrectable error mask register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_sec_uncorrectable_error_mask.htm
old-project: PCI
ms.assetid: 99387bcc-301d-4406-bcff-fb5569c88c90
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: wdm/PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK union [Buses], _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK union pointer [Buses], wdm/PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, PCI.pci_express_sec_uncorrectable_error_mask, *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, pci_struct_80f14fae-7c43-4a78-bdb7-211abd0e43fd.xml
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
-	PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK
product: Windows
targetos: Windows
req.typenames: "*PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK"
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure


## -description


The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) secondary uncorrectable error mask register of a PCIe advanced error reporting capability structure.


## -syntax


````
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
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.TargetAbortOnSplitCompletion

 


### -field DUMMYSTRUCTNAME.MasterAbortOnSplitCompletion

 


### -field DUMMYSTRUCTNAME.ReceivedTargetAbort

 


### -field DUMMYSTRUCTNAME.ReceivedMasterAbort

 


### -field DUMMYSTRUCTNAME.RsvdZ

 


### -field DUMMYSTRUCTNAME.UnexpectedSplitCompletionError

 


### -field DUMMYSTRUCTNAME.UncorrectableSplitCompletion

 


### -field DUMMYSTRUCTNAME.UncorrectableDataError

 


### -field DUMMYSTRUCTNAME.UncorrectableAttributeError

 


### -field DUMMYSTRUCTNAME.UncorrectableAddressError

 


### -field DUMMYSTRUCTNAME.DelayedTransactionDiscardTimerExpired

 


### -field DUMMYSTRUCTNAME.PERRAsserted

 


### -field DUMMYSTRUCTNAME.SERRAsserted

 


### -field DUMMYSTRUCTNAME.InternalBridgeError

 


### -field DUMMYSTRUCTNAME.Reserved

 


#### - AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure.


#### - TargetAbortOnSplitCompletion

A single bit that indicates that the reporting of target aborts on split completion is masked.


#### - MasterAbortOnSplitCompletion

A single bit that indicates that the reporting of master aborts on split completion is masked.


#### - ReceivedTargetAbort

A single bit that indicates that the reporting of target aborts is masked.


#### - ReceivedMasterAbort

A single bit that indicates that the reporting of master aborts is masked.


#### - RsvdZ

Reserved for system use.


#### - UnexpectedSplitCompletionError

A single bit that indicates that the reporting of unexpected split completion errors is masked.


#### - UncorrectableSplitCompletion

A single bit that indicates that the reporting of uncorrectable split completion message data errors is masked.


#### - UncorrectableDataError

A single bit that indicates that the reporting of uncorrectable data errors is masked.


#### - UncorrectableAttributeError

A single bit that indicates that the reporting of uncorrectable attribute errors is masked.


#### - UncorrectableAddressError

A single bit that indicates that the reporting of uncorrectable address errors is masked.


#### - DelayedTransactionDiscardTimerExpired

A single bit that indicates that the reporting of the expiration of the delayed transaction discard timer is masked.


#### - PERRAsserted

A single bit that indicates that the reporting of PERR# assertions is masked.


#### - SERRAsserted

A single bit that indicates that the reporting of SERR# assertions is masked.


#### - InternalBridgeError

A single bit that indicates that the reporting of internal bridge errors is masked.


#### - Reserved

Reserved for system use.


## -remarks


The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a> structure.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

