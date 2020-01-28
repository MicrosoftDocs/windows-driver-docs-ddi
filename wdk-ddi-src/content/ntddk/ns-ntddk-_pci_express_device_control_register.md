---
UID: NS:ntddk._PCI_EXPRESS_DEVICE_CONTROL_REGISTER
title: _PCI_EXPRESS_DEVICE_CONTROL_REGISTER (ntddk.h)
description: The PCI_EXPRESS_DEVICE_CONTROL_REGISTER structure describes a PCI Express (PCIe) device control register of a PCIe capability structure.
old-location: pci\pci_express_device_control_register.htm
tech.root: PCI
ms.assetid: 888f88db-2149-4da2-acdb-4bf88a5362dd
ms.date: 02/24/2018
ms.keywords: "*PPCI_EXPRESS_DEVICE_CONTROL_REGISTER, PCI.pci_express_device_control_register, PCI_EXPRESS_DEVICE_CONTROL_REGISTER, PCI_EXPRESS_DEVICE_CONTROL_REGISTER union [Buses], PPCI_EXPRESS_DEVICE_CONTROL_REGISTER, PPCI_EXPRESS_DEVICE_CONTROL_REGISTER union pointer [Buses], _PCI_EXPRESS_DEVICE_CONTROL_REGISTER, ntddk/PCI_EXPRESS_DEVICE_CONTROL_REGISTER, ntddk/PPCI_EXPRESS_DEVICE_CONTROL_REGISTER, pci_struct_344c5f1d-566f-4755-ba52-57635c4fabfe.xml"
f1_keywords:
 - "ntddk/PCI_EXPRESS_DEVICE_CONTROL_REGISTER"
req.header: ntddk.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- PCI_EXPRESS_DEVICE_CONTROL_REGISTER
product:
- Windows
targetos: Windows
req.typenames: PCI_EXPRESS_DEVICE_CONTROL_REGISTER, *PPCI_EXPRESS_DEVICE_CONTROL_REGISTER
---

# _PCI_EXPRESS_DEVICE_CONTROL_REGISTER structure


## -description


The PCI_EXPRESS_DEVICE_CONTROL_REGISTER structure describes a PCI Express (PCIe) device control register of a PCIe capability structure.


## -syntax


```cpp
typedef union _PCI_EXPRESS_DEVICE_CONTROL_REGISTER {
  struct {
    USHORT CorrectableErrorEnable  :1;
    USHORT NonFatalErrorEnable  :1;
    USHORT FatalErrorEnable  :1;
    USHORT UnsupportedRequestErrorEnable  :1;
    USHORT EnableRelaxedOrder  :1;
    USHORT MaxPayloadSize  :3;
    USHORT ExtendedTagEnable  :1;
    USHORT PhantomFunctionsEnable  :1;
    USHORT AuxPowerEnable  :1;
    USHORT NoSnoopEnable  :1;
    USHORT MaxReadRequestSize  :3;
    USHORT BridgeConfigRetryEnable  :1;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_DEVICE_CONTROL_REGISTER, *PPCI_EXPRESS_DEVICE_CONTROL_REGISTER;
```


## -struct-fields




### -field DUMMYSTRUCTNAME




### -field DUMMYSTRUCTNAME2




### -field AsUSHORT

A USHORT representation of the contents of the <b>PCI_EXPRESS_DEVICE_CONTROL_REGISTER</b> structure.


#### - AuxPowerEnable

A single bit that indicates that the device is enabled to draw AUX power independent of power management events (PME) AUX power.


#### - BridgeConfigRetryEnable

Reserved.


#### - CorrectableErrorEnable

A single bit that indicates that reporting of correctable errors is enabled for the device.


#### - EnableRelaxedOrder

A single bit that indicates that the device is permitted to set the relaxed ordering bit in the attributes field for any transactions that it initiates that do not require strong write ordering.


#### - ExtendedTagEnable

A single bit that indicates that the device is enabled to use an 8-bit Tag field in a PCIe transaction descriptor when the device is a requester. This bit can be set only if the PCIe device capabilities register of the PCIe capability structure indicates that the extended tag size is supported.


#### - FatalErrorEnable

A single bit that indicates that reporting of non-fatal uncorrectable errors is enabled for the device.


#### - MaxPayloadSize

The maximum payload size for the device. Possible values are:





#### MaxPayload128Bytes

128 byte maximum payload size



#### MaxPayload256Bytes

256 byte maximum payload size



#### MaxPayload512Bytes

512 byte maximum payload size



#### MaxPayload1024Bytes

1024 byte maximum payload size



#### MaxPayload2048Bytes

2048 byte maximum payload size



#### MaxPayload4096Bytes

4096 byte maximum payload size

This value must not exceed the maximum payload size that is specified in the PCIe device capabilities register of the PCIe capability structure.


#### - MaxReadRequestSize

The maximum read request size for the device as a requester. Possible values are:





#### MaxPayload128Bytes

128 byte maximum read request size



#### MaxPayload256Bytes

256 byte maximum read request size



#### MaxPayload512Bytes

512 byte maximum read request size



#### MaxPayload1024Bytes

1024 byte maximum read request size



#### MaxPayload2048Bytes

2048 byte maximum read request size



#### MaxPayload4096Bytes

4096 byte maximum read request size


#### - NoSnoopEnable

A single bit that indicates that the device is permitted to set the No Snoop bit in the Requester Attributes field of transactions that it initiates that do not require hardware enforced cache coherency.


#### - NonFatalErrorEnable

A single bit that indicates that reporting of non-fatal uncorrectable errors is enabled for the device.


#### - PhantomFunctionsEnable

A single bit that indicates that the device is enabled to use unused function numbers (phantom functions) to extend the number of outstanding transactions that are allowed for the device. This bit can be set only if the PCIe device capabilities register of the PCIe capability structure indicates that phantom functions are supported.


#### - UnsupportedRequestErrorEnable

A single bit that indicates that reporting of unsupported requests is enabled for the device.


## -remarks



The PCI_EXPRESS_DEVICE_CONTROL_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_DEVICE_CONTROL_REGISTER structure is contained in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability">PCI_EXPRESS_CAPABILITY</a> structure.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability">PCI_EXPRESS_CAPABILITY</a>



 

 


