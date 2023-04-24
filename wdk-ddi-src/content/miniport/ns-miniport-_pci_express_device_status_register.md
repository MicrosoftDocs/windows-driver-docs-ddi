---
UID: NS:miniport._PCI_EXPRESS_DEVICE_STATUS_REGISTER
title: PCI_EXPRESS_DEVICE_STATUS_REGISTER (miniport.h)
description: The _PCI_EXPRESS_DEVICE_STATUS_REGISTER union (miniport.h) describes a PCI Express (PCIe) device status register of a PCIe capability structure.
tech.root: PCI
ms.date: 07/18/2022
keywords: ["PCI_EXPRESS_DEVICE_STATUS_REGISTER structure"]
ms.keywords: "*PPCI_EXPRESS_DEVICE_STATUS_REGISTER, PCI.pci_express_device_status_register, PCI_EXPRESS_DEVICE_STATUS_REGISTER, PCI_EXPRESS_DEVICE_STATUS_REGISTER union [Buses], PPCI_EXPRESS_DEVICE_STATUS_REGISTER, PPCI_EXPRESS_DEVICE_STATUS_REGISTER union pointer [Buses], _PCI_EXPRESS_DEVICE_STATUS_REGISTER, ntddk/PCI_EXPRESS_DEVICE_STATUS_REGISTER, ntddk/PPCI_EXPRESS_DEVICE_STATUS_REGISTER, pci_struct_90e0cf73-2c43-444d-bdaa-77fd00d483a7.xml"
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
req.typenames: PCI_EXPRESS_DEVICE_STATUS_REGISTER, *PPCI_EXPRESS_DEVICE_STATUS_REGISTER
f1_keywords:
 - _PCI_EXPRESS_DEVICE_STATUS_REGISTER
 - miniport/_PCI_EXPRESS_DEVICE_STATUS_REGISTER
 - PPCI_EXPRESS_DEVICE_STATUS_REGISTER
 - miniport/PPCI_EXPRESS_DEVICE_STATUS_REGISTER
 - PCI_EXPRESS_DEVICE_STATUS_REGISTER
 - miniport/PCI_EXPRESS_DEVICE_STATUS_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_DEVICE_STATUS_REGISTER
 - PPCI_EXPRESS_DEVICE_STATUS_REGISTER
 - PCI_EXPRESS_DEVICE_STATUS_REGISTER
---

## -description

The **PCI_EXPRESS_DEVICE_STATUS_REGISTER** union describes a PCI Express (PCIe) device status register of a PCIe capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.CorrectableErrorDetected

A single bit that indicates that a correctable error has been detected.

### -field DUMMYSTRUCTNAME.NonFatalErrorDetected

A single bit that indicates that a non-fatal uncorrectable error has been detected.

### -field DUMMYSTRUCTNAME.FatalErrorDetected

A single bit that indicates that a non-fatal uncorrectable error has been detected.

### -field DUMMYSTRUCTNAME.UnsupportedRequestDetected

A single bit that indicates that an unsupported request has been detected.

### -field DUMMYSTRUCTNAME.AuxPowerDetected

A single bit that indicates that AUX power has been detected.

### -field DUMMYSTRUCTNAME.TransactionsPending

A single bit that indicates that the device has issued non-posted requests that have not been completed. The device clears this bit when all outstanding non-posted requests have completed or have been terminated by the completion timeout mechanism.

### -field DUMMYSTRUCTNAME.Rsvd

Reserved.

### -field AsUSHORT

A **USHORT** representation of the contents of the **PCI_EXPRESS_DEVICE_STATUS_REGISTER** structure.

## -remarks

The **PCI_EXPRESS_DEVICE_STATUS_REGISTER** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_DEVICE_STATUS_REGISTER** structure is contained in the [PCI_EXPRESS_CAPABILITY](../ntddk/ns-ntddk-_pci_express_capability.md) structure.

## -see-also

[PCI_EXPRESS_CAPABILITY](../ntddk/ns-ntddk-_pci_express_capability.md)