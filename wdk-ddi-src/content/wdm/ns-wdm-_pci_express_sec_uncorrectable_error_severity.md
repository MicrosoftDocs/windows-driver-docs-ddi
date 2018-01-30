---
UID: NS:wdm._PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
title: "_PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY"
author: windows-driver-content
description: The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY structure describes a PCI Express (PCIe) secondary uncorrectable error severity register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_sec_uncorrectable_error_severity.htm
old-project: PCI
ms.assetid: b00aeced-037b-4bc5-97b7-96501262700f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PCI.pci_express_sec_uncorrectable_error_severity, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY union [Buses], PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY union pointer [Buses], PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, wdm/PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, wdm/PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, pci_struct_94eb07f5-9b90-414b-a331-075c61f507a4.xml
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
-	PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
product: Windows
targetos: Windows
req.typenames: PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY structure


## -description


The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY structure describes a PCI Express (PCIe) secondary uncorrectable error severity register of a PCIe advanced error reporting capability structure.


## -syntax


````
typedef union _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY {
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
} PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY, *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY;
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

 


### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure.


#### - TargetAbortOnSplitCompletion

A single bit that indicates that a reported target abort on split completion is a fatal error.


#### - MasterAbortOnSplitCompletion

A single bit that indicates that a reported master abort on split completion is a fatal error.


#### - ReceivedTargetAbort

A single bit that indicates that a reported target abort is a fatal error.


#### - ReceivedMasterAbort

A single bit that indicates that a reported master abort is a fatal error.


#### - RsvdZ

Reserved for system use.


#### - UnexpectedSplitCompletionError

A single bit that indicates that a reported unexpected split completion error is a fatal error.


#### - UncorrectableSplitCompletion

A single bit that indicates that a reported uncorrectable split completion message data error is a fatal error.


#### - UncorrectableDataError

A single bit that indicates that a reported uncorrectable data error is a fatal error.


#### - UncorrectableAttributeError

A single bit that indicates that a reported uncorrectable attribute error is a fatal error.


#### - UncorrectableAddressError

A single bit that indicates that a reported uncorrectable address error is a fatal error.


#### - DelayedTransactionDiscardTimerExpired

A single bit that indicates that an expiration of the delayed transaction discard timer is a fatal error.


#### - PERRAsserted

A single bit that indicates that a reported PERR# assertion is a fatal error.


#### - SERRAsserted

A single bit that indicates that a reported SERR# assertion is a fatal error.


#### - InternalBridgeError

A single bit that indicates that a reported internal bridge error is a fatal error.


#### - Reserved

Reserved for system use.


## -remarks


The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a> structure.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

