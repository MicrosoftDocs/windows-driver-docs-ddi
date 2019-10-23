---
UID: NS:miniport._PCI_EXPRESS_DEVICE_STATUS_REGISTER
title: _PCI_EXPRESS_DEVICE_STATUS_REGISTER (miniport.h)
description: The PCI_EXPRESS_DEVICE_STATUS_REGISTER structure describes a PCI Express (PCIe) device status register of a PCIe capability structure.
old-location: pci\pci_express_device_status_register.htm
tech.root: PCI
ms.assetid: a4c92364-59d4-442c-879b-fba770d8d612
ms.date: 02/24/2018
ms.keywords: "*PPCI_EXPRESS_DEVICE_STATUS_REGISTER, PCI.pci_express_device_status_register, PCI_EXPRESS_DEVICE_STATUS_REGISTER, PCI_EXPRESS_DEVICE_STATUS_REGISTER union [Buses], PPCI_EXPRESS_DEVICE_STATUS_REGISTER, PPCI_EXPRESS_DEVICE_STATUS_REGISTER union pointer [Buses], _PCI_EXPRESS_DEVICE_STATUS_REGISTER, ntddk/PCI_EXPRESS_DEVICE_STATUS_REGISTER, ntddk/PPCI_EXPRESS_DEVICE_STATUS_REGISTER, pci_struct_90e0cf73-2c43-444d-bdaa-77fd00d483a7.xml"
ms.topic: struct
f1_keywords:
 - "miniport/PCI_EXPRESS_DEVICE_STATUS_REGISTER"
req.header: miniport.h
req.include-header: Ntddk.h, Miniport.h
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
- ntddk.h
api_name:
- PCI_EXPRESS_DEVICE_STATUS_REGISTER
product:
- Windows
targetos: Windows
req.typenames: PCI_EXPRESS_DEVICE_STATUS_REGISTER, *PPCI_EXPRESS_DEVICE_STATUS_REGISTER
---

# _PCI_EXPRESS_DEVICE_STATUS_REGISTER structure


## -description


The PCI_EXPRESS_DEVICE_STATUS_REGISTER structure describes a PCI Express (PCIe) device status register of a PCIe capability structure.


## -syntax


```cpp
typedef union _PCI_EXPRESS_DEVICE_STATUS_REGISTER {
  struct {
    USHORT CorrectableErrorDetected  :1;
    USHORT NonFatalErrorDetected  :1;
    USHORT FatalErrorDetected  :1;
    USHORT UnsupportedRequestDetected  :1;
    USHORT AuxPowerDetected  :1;
    USHORT TransactionsPending  :1;
    USHORT Rsvd  :10;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_DEVICE_STATUS_REGISTER, *PPCI_EXPRESS_DEVICE_STATUS_REGISTER;
```


## -struct-fields




### -field DUMMYSTRUCTNAME




### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_DEVICE_STATUS_REGISTER structure.


#### - AuxPowerDetected

A single bit that indicates that AUX power has been detected.


#### - CorrectableErrorDetected

A single bit that indicates that a correctable error has been detected.


#### - FatalErrorDetected

A single bit that indicates that a non-fatal uncorrectable error has been detected.


#### - NonFatalErrorDetected

A single bit that indicates that a non-fatal uncorrectable error has been detected.


#### - Rsvd

Reserved.


#### - TransactionsPending

A single bit that indicates that the device has issued non-posted requests that have not been completed. The device clears this bit when all outstanding non-posted requests have completed or have been terminated by the completion timeout mechanism.


#### - UnsupportedRequestDetected

A single bit that indicates that an unsupported request has been detected.


## -remarks



The <b>PCI_EXPRESS_DEVICE_STATUS_REGISTER</b> structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_DEVICE_STATUS_REGISTER structure is contained in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability">PCI_EXPRESS_CAPABILITY</a> structure.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability">PCI_EXPRESS_CAPABILITY</a>



 

 


