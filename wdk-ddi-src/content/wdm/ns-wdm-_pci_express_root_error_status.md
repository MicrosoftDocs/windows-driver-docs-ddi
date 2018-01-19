---
UID: NS:wdm._PCI_EXPRESS_ROOT_ERROR_STATUS
title: _PCI_EXPRESS_ROOT_ERROR_STATUS
author: windows-driver-content
description: The PCI_EXPRESS_ROOT_ERROR_STATUS structure describes a PCI Express (PCIe) root error status register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_root_error_status.htm
old-project: PCI
ms.assetid: 1af0c877-e634-474e-9b4d-a28991fb3f66
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _PCI_EXPRESS_ROOT_ERROR_STATUS, PCI_EXPRESS_ROOT_ERROR_STATUS, *PPCI_EXPRESS_ROOT_ERROR_STATUS
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
req.alt-api: PCI_EXPRESS_ROOT_ERROR_STATUS
req.alt-loc: wdm.h
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
req.typenames: PCI_EXPRESS_ROOT_ERROR_STATUS, *PPCI_EXPRESS_ROOT_ERROR_STATUS
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_ROOT_ERROR_STATUS structure



## -description
The PCI_EXPRESS_ROOT_ERROR_STATUS structure describes a PCI Express (PCIe) root error status register of a PCIe advanced error reporting capability structure.



## -syntax

````
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
````


## -struct-fields

### -field CorrectableErrorReceived

A single bit that indicates that a correctable error message has been received.


### -field MultipleCorrectableErrorsReceived

A single bit that indicates that multiple correctable error messages have been received.


### -field UncorrectableErrorReceived

A single bit that indicates that an uncorrectable error message has been received.


### -field MultipleUncorrectableErrorsReceived

A single bit that indicates that multiple uncorrectable error messages have been received.


### -field FirstUncorrectableFatal

A single bit that indicates that the first uncorrectable error message that was received was for a fatal error.


### -field NonFatalErrorMessagesReceived

A single bit that indicates that one or more non-fatal uncorrectable error messages have been received.


### -field FatalErrorMessagesReceived

A single bit that indicates that one or more non-fatal uncorrectable error messages have been received.


### -field Reserved

Reserved.


### -field AdvancedErrorInterruptMessageNumber

The MSI/MSI-X vector that is used for the interrupt messages that are generated in association with any of the status bits of the advanced error reporting capability.


### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_ROOT_ERROR_STATUS structure.


## -remarks
The PCI_EXPRESS_ROOT_ERROR_STATUS structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_ROOT_ERROR_STATUS structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structure.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_ROOT_ERROR_STATUS union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

