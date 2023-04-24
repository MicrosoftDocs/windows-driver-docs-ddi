---
UID: NF:ntddk.HalGetBusDataByOffset
tech.root: kernel
title: HalGetBusDataByOffset
ms.date: 09/22/2022
targetos: Windows
description: This function retrieves information, starting at the offset, about a slot or address on an I/O bus.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.idl: 
req.include-header:  Ntddk.h
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
 - HalGetBusDataByOffset
f1_keywords:
 - HalGetBusDataByOffset
 - ntddk/HalGetBusDataByOffset
dev_langs:
 - c++
helpviewer_keywords:
 - HalGetBusDataByOffset
---

## -description

This function retrieves information, starting at the offset, about a slot or address on an I/O bus.

## -parameters

### -param BusDataType [in]

Bus data to retrieve. The upper bound on the bus types supported is always MaximumBusDataType. The only supported BusDataType is `PCIConfiguration` All other types are deprecated.

### -param BusNumber [in]

Zero-based and system-assigned number of the bus in systems with several buses of the same BusDataType. This argument also carries the segment number. To specify the segment number, use (Segment << 8) | BusNumber

### -param SlotNumber [in]

Logical slot number or location of the device. If you specify PCIConfiguration as the BusDataType, this value is a PCI_SLOT_NUMBER value, which is the slot and function numbers combined.

### -param Buffer [in]

Pointer to a caller-supplied buffer for configuration information specific to BusDataType.

If you specify PCIConfiguration, the buffer contains the PCI config space information for the specified SlotNumber and function number. The specified Offset and Length determine how much information to supply. Certain members of PCI config space have read-only values The caller is responsible for preserving the system-supplied values of read-only members. Note that for a Type-1 PCI device, HalSetBusDataByOffset prevents writes to registers inside the common header (first 256bytes of the config space).

### -param Offset [in]

Byte offset in the PCI_COMMON_CONFIG structure for which the requested information should be returned. Callers can use the system-defined constant PCI_COMMON_HDR_LENGTH to specify the device-specific area of PCI_COMMON_CONFIG.

### -param Length [in]

Maximum number of bytes in the Buffer.

## -returns

The return value is the actual length read from the config space.

## -remarks

Device drivers call this function during initialization to locate their devices on a particular I/O bus. You can use the returned bus-type-specific configuration data in later calls to other configuration and initialization functions, such as HalTranslateBusAddress.

When accessing the device-specific area of the PCI configuration space, HalGetBusDataByOffset guarantees that this function never reads or writes data outside the range specified by the input Offset and Length. Even if the input Length is exactly a 1-byte or 2-byte word, this function never accesses any data outside the requested range.

## -see-also

[BUS_DATA_TYPE](/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_bus_data_type)

[HalGetBusData](/previous-versions/windows/embedded/ms899356(v=msdn.10))

[HalSetBusDataByOffset](./nf-ntddk-halsetbusdatabyoffset.md)

[HalSetBusData](/previous-versions/windows/embedded/ms899359(v=msdn.10))

[HalTranslateBusAddress](/previous-versions/windows/embedded/ms899361(v=msdn.10))

[**PCI_COMMON_CONFIG**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_common_config)
