---
UID: NS:miniport._PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
title: "_PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY"
author: windows-driver-content
description: The PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure describes a PCI Express (PCIe) uncorrectable error severity register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_uncorrectable_error_severity.htm
tech.root: PCI
ms.assetid: de2a908a-a032-4b61-963e-e5028ccdba11
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, PCI.pci_express_uncorrectable_error_severity, PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY union [Buses], PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY union pointer [Buses], _PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, pci_struct_49aec790-2c99-489c-b0ca-0653ebe5b52c.xml, wdm/PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, wdm/PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
product:
- Windows
targetos: Windows
req.typenames: PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
---

# _PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure


## -description


The PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure describes a PCI Express (PCIe) uncorrectable error severity register of a PCIe advanced error reporting capability structure.


## -syntax


```cpp
typedef union _PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY {
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
} PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY;
```


## -struct-fields




### -field DUMMYSTRUCTNAME




### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure.


#### - CompleterAbort

A single bit that indicates that a reported completer abort is a fatal error.


#### - CompletionTimeout

A single bit that indicates that a reported completion timeout is a fatal error.


#### - DataLinkProtocolError

A single bit that indicates that a reported data link protocol error is a fatal error.


#### - ECRCError

A single bit that indicates that a reported end-to-end cyclic redundancy check (ECRC) error is a fatal error.


#### - FlowControlProtocolError

A single bit that indicates that a reported flow control protocol error is a fatal error.


#### - MalformedTLP

A single bit that indicates that a reported malformed transaction layer packet (TLP) is a fatal error.


#### - PoisonedTLP

A single bit that indicates that a reported poisoned transaction layer packet (TLP) is a fatal error.


#### - ReceiverOverflow

A single bit that indicates that a reported receiver overflow is a fatal error.


#### - Reserved1

Reserved.


#### - Reserved2

Reserved.


#### - Reserved3

Reserved.


#### - SurpriseDownError

A single bit that indicates that a reported surprise down error is a fatal error.


#### - Undefined

A single bit that contains an undefined value. In versions of the <i>PCIe Specification</i> prior to version 1.1, this bit indicates that a reported link training error is a fatal error.


#### - UnexpectedCompletion

A single bit that indicates that a reported unexpected completion is a fatal error.


#### - UnsupportedRequestError

A single bit that indicates that a reported unsupported request error is a fatal error.


## -remarks



The PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structures.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>



 

 


