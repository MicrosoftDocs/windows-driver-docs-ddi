---
UID: NF:ntddk.HalSetBusDataByOffset
tech.root: kernel
title: HalSetBusDataByOffset
ms.date: 01/17/2024
targetos: Windows
description: This function sets bus-configuration data for a device on a dynamically configurable I/O bus with a published, standard interface.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.idl: 
req.include-header: Ntddk.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - HalSetBusDataByOffset
f1_keywords:
 - HalSetBusDataByOffset
 - ntddk/HalSetBusDataByOffset
dev_langs:
 - c++
helpviewer_keywords:
 - HalSetBusDataByOffset
---

## -description

>[!WARNING]
>[**HalGetBusDataByOffset**](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-halgetbusdatabyoffset) and **HalSetBusDataByOffset** are provided for backward compatibility but should be used only if the methods recommended in [Accessing Device Configuration Space](/windows-hardware/drivers/kernel/accessing-device-configuration-space) cannot be used.

This function sets bus-configuration data for a device on a dynamically configurable I/O bus with a published, standard interface.

## -parameters

### -param BusDataType [in]

Bus data to set. This value can be PCIConfiguration. The upper bound on the types supported is always MaximumBusDataType.

### -param BusNumber [in]

Zero-based and system-assigned number of the bus in systems with several buses of the same BusDataType. This argument also carries the segment number. To specify the segment number, use (Segment << 8) | BusNumber

### -param SlotNumber [in]

Logical slot number or location of the device. If you specify PCIConfiguration as the BusDataType, this value is specified as a PCI_SLOT_NUMBER value, which is the slot and function numbers combined.

### -param Buffer [in]

Pointer to a caller-supplied buffer for configuration information specific to BusDataType.

If you specify PCIConfiguration, the buffer contains the PCI config space information for the specifed SlotNumber and function number. The specified Offset and Length determine how much information to supply. Certain members of PCI config space have read-only values The caller is responsible for preserving the system-supplied values of read-only members. Note that for a Type-1 PCI device, HalSetBusDataByOffset prevents writes to registers inside the common header (first 256bytes of the config space).

### -param Offset [in]

Byte offset in the PCI_COMMON_CONFIG structure where the caller-supplied configuration values begin. Callers can use the system-defined constant PCI_COMMON_HDR_LENGTH to specify the device-specific area of PCI_COMMON_CONFIG.

### -param Length [in]

Number of bytes in Buffer.

## -returns

The return value is the actual length written to the config space.

## -remarks

A driver can call this function or HalSetBusData if unusual circumstances or the nature of its device requires such a call. For example, a driver might call either of these functions to clear a bit in the PCI status register if its device signals a target abort during initialization. Usually, the hardware or startup code configures the device appropriately.

When accessing the device-specific area of the PCI configuration space, HalSetBusDataByOffset guarantees that this function never reads or writes data outside the range specified by the input Offset and Length and even if the input Length is exactly a byte or a two-byte word, this function never accesses any data outside the requested range.

## -see-also

[BUS_DATA_TYPE](/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_bus_data_type)

[HalGetBusData](/previous-versions/windows/embedded/ms899356(v=msdn.10))

[HalGetBusDataByOffset](./nf-ntddk-halgetbusdatabyoffset.md)

[HalSetBusData](/previous-versions/windows/embedded/ms899359(v=msdn.10))

[HalTranslateBusAddress](/previous-versions/windows/embedded/ms899361(v=msdn.10))

[**PCI_COMMON_CONFIG**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_common_config)
