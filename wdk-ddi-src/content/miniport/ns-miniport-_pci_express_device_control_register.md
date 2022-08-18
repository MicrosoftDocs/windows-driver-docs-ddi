---
UID: NS:miniport._PCI_EXPRESS_DEVICE_CONTROL_REGISTER
title: PCI_EXPRESS_DEVICE_CONTROL_REGISTER (miniport.h)
description: The _PCI_EXPRESS_DEVICE_CONTROL_REGISTER union (miniport.h) describes a PCI Express (PCIe) device control register of a PCIe capability structure.
tech.root: PCI
ms.date: 07/18/2022
keywords: ["PCI_EXPRESS_DEVICE_CONTROL_REGISTER structure"]
ms.keywords: "*PPCI_EXPRESS_DEVICE_CONTROL_REGISTER, PCI.pci_express_device_control_register, PCI_EXPRESS_DEVICE_CONTROL_REGISTER, PCI_EXPRESS_DEVICE_CONTROL_REGISTER union [Buses], PPCI_EXPRESS_DEVICE_CONTROL_REGISTER, PPCI_EXPRESS_DEVICE_CONTROL_REGISTER union pointer [Buses], _PCI_EXPRESS_DEVICE_CONTROL_REGISTER, ntddk/PCI_EXPRESS_DEVICE_CONTROL_REGISTER, ntddk/PPCI_EXPRESS_DEVICE_CONTROL_REGISTER, pci_struct_344c5f1d-566f-4755-ba52-57635c4fabfe.xml"
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
targetos: Windows
req.typenames: PCI_EXPRESS_DEVICE_CONTROL_REGISTER, *PPCI_EXPRESS_DEVICE_CONTROL_REGISTER
f1_keywords:
 - _PCI_EXPRESS_DEVICE_CONTROL_REGISTER
 - miniport/_PCI_EXPRESS_DEVICE_CONTROL_REGISTER
 - PPCI_EXPRESS_DEVICE_CONTROL_REGISTER
 - miniport/PPCI_EXPRESS_DEVICE_CONTROL_REGISTER
 - PCI_EXPRESS_DEVICE_CONTROL_REGISTER
 - miniport/PCI_EXPRESS_DEVICE_CONTROL_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_DEVICE_CONTROL_REGISTER
 - PPCI_EXPRESS_DEVICE_CONTROL_REGISTER
 - PCI_EXPRESS_DEVICE_CONTROL_REGISTER
---

## -description

The **PCI_EXPRESS_DEVICE_CONTROL_REGISTER** union describes a PCI Express (PCIe) device control register of a PCIe capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.CorrectableErrorEnable

A single bit that indicates that reporting of correctable errors is enabled for the device.

### -field DUMMYSTRUCTNAME.NonFatalErrorEnable

A single bit that indicates that reporting of non-fatal uncorrectable errors is enabled for the device.

### -field DUMMYSTRUCTNAME.FatalErrorEnable

A single bit that indicates that reporting of non-fatal uncorrectable errors is enabled for the device.

### -field DUMMYSTRUCTNAME.UnsupportedRequestErrorEnable

A single bit that indicates that reporting of unsupported requests is enabled for the device.

### -field DUMMYSTRUCTNAME.EnableRelaxedOrder

A single bit that indicates that the device is permitted to set the relaxed ordering bit in the attributes field for any transactions that it initiates that do not require strong write ordering.

### -field DUMMYSTRUCTNAME.MaxPayloadSize

The maximum payload size for the device. Possible values are:

**MaxPayload128Bytes**  
128 byte maximum payload size

**MaxPayload256Bytes**  
256 byte maximum payload size

**MaxPayload512Bytes**  
512 byte maximum payload size

**MaxPayload1024Bytes**  
1024 byte maximum payload size

**MaxPayload2048Bytes**  
2048 byte maximum payload size

**MaxPayload4096Bytes**  
4096 byte maximum payload size

This value must not exceed the maximum payload size that is specified in the PCIe device capabilities register of the PCIe capability structure.

### -field DUMMYSTRUCTNAME.ExtendedTagEnable

A single bit that indicates that the device is enabled to use an 8-bit Tag field in a PCIe transaction descriptor when the device is a requester. This bit can be set only if the PCIe device capabilities register of the PCIe capability structure indicates that the extended tag size is supported.

### -field DUMMYSTRUCTNAME.PhantomFunctionsEnable

A single bit that indicates that the device is enabled to use unused function numbers (phantom functions) to extend the number of outstanding transactions that are allowed for the device. This bit can be set only if the PCIe device capabilities register of the PCIe capability structure indicates that phantom functions are supported.

### -field DUMMYSTRUCTNAME.AuxPowerEnable

A single bit that indicates that the device is enabled to draw AUX power independent of power management events (PME) AUX power.

### -field DUMMYSTRUCTNAME.NoSnoopEnable

A single bit that indicates that the device is permitted to set the No Snoop bit in the Requester Attributes field of transactions that it initiates that do not require hardware enforced cache coherency.

### -field DUMMYSTRUCTNAME.MaxReadRequestSize

The maximum read request size for the device as a requester. Possible values are:

**MaxPayload128Bytes**  
128 byte maximum read request size

**MaxPayload256Bytes**  
256 byte maximum read request size

**MaxPayload512Bytes**  
512 byte maximum read request size

**MaxPayload1024Bytes**  
1024 byte maximum read request size

**MaxPayload2048Bytes**  
2048 byte maximum read request size

**MaxPayload4096Bytes**  
4096 byte maximum read request size

### -field DUMMYSTRUCTNAME.BridgeConfigRetryEnable

Reserved.

### -field DUMMYSTRUCTNAME2

The **DUMMYSTRUCTNAME2** structure.

### -field DUMMYSTRUCTNAME2.InitiateFunctionLevelReset

### -field AsUSHORT

A **USHORT** representation of the contents of the **PCI_EXPRESS_DEVICE_CONTROL_REGISTER** structure.

## -remarks

The **PCI_EXPRESS_DEVICE_CONTROL_REGISTER** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_DEVICE_CONTROL_REGISTER** structure is contained in the [PCI_EXPRESS_CAPABILITY](../ntddk/ns-ntddk-_pci_express_capability.md) structure.

## -see-also

[PCI_EXPRESS_CAPABILITY](../ntddk/ns-ntddk-_pci_express_capability.md)