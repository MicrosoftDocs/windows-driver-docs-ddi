---
UID: NS:wdm._PCI_EXPRESS_ROOT_ERROR_COMMAND
title: _PCI_EXPRESS_ROOT_ERROR_COMMAND (wdm.h)
description: The PCI_EXPRESS_ROOT_ERROR_COMMAND structure describes a PCI Express (PCIe) root error command register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_root_error_command.htm
tech.root: PCI
ms.assetid: 659c0612-5623-4615-b9c5-6d2656097b89
ms.date: 02/24/2018
ms.keywords: "*PPCI_EXPRESS_ROOT_ERROR_COMMAND, PCI.pci_express_root_error_command, PCI_EXPRESS_ROOT_ERROR_COMMAND, PCI_EXPRESS_ROOT_ERROR_COMMAND union [Buses], PPCI_EXPRESS_ROOT_ERROR_COMMAND, PPCI_EXPRESS_ROOT_ERROR_COMMAND union pointer [Buses], _PCI_EXPRESS_ROOT_ERROR_COMMAND, pci_struct_f7834746-d8b5-4765-8434-8f7837a47871.xml, wdm/PCI_EXPRESS_ROOT_ERROR_COMMAND, wdm/PPCI_EXPRESS_ROOT_ERROR_COMMAND"
ms.topic: struct
req.header: wdm.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	PCI_EXPRESS_ROOT_ERROR_COMMAND
product:
- Windows
targetos: Windows
req.typenames: PCI_EXPRESS_ROOT_ERROR_COMMAND, *PPCI_EXPRESS_ROOT_ERROR_COMMAND
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_ROOT_ERROR_COMMAND structure


## -description


The PCI_EXPRESS_ROOT_ERROR_COMMAND structure describes a PCI Express (PCIe) root error command register of a PCIe advanced error reporting capability structure.


## -syntax


```cpp
typedef union _PCI_EXPRESS_ROOT_ERROR_COMMAND {
  struct {
    ULONG CorrectableErrorReportingEnable  :1;
    ULONG NonFatalErrorReportingEnable  :1;
    ULONG FatalErrorReportingEnable  :1;
    ULONG Reserved  :29;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_ROOT_ERROR_COMMAND, *PPCI_EXPRESS_ROOT_ERROR_COMMAND;
```


## -struct-fields




### -field DUMMYSTRUCTNAME




### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_ROOT_ERROR_COMMAND structure.


#### - CorrectableErrorReportingEnable

A single bit that indicates that interrupts are enabled for when a correctable error is reported by any of the devices in the hierarchy that are associated with this root port.


#### - FatalErrorReportingEnable

A single bit that indicates that interrupts are enabled for when a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port.


#### - NonFatalErrorReportingEnable

A single bit that indicates that interrupts are enabled for when a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port.


#### - Reserved

Reserved.


## -remarks



The PCI_EXPRESS_ROOT_ERROR_COMMAND structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_ROOT_ERROR_COMMAND structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>



 

 


