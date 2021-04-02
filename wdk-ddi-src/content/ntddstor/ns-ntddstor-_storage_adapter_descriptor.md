---
UID: NS:ntddstor._STORAGE_ADAPTER_DESCRIPTOR
title: STORAGE_ADAPTER_DESCRIPTOR (ntddstor.h)
description: The STORAGE_ADAPTER_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the storage adapter descriptor data for a device.
old-location: storage\storage_adapter_descriptor.htm
tech.root: storage
ms.date: 04/01/2021
keywords: ["STORAGE_ADAPTER_DESCRIPTOR structure"]
ms.keywords: PSTORAGE_ADAPTER_DESCRIPTOR, PSTORAGE_ADAPTER_DESCRIPTOR structure pointer [Storage Devices], SRB_TYPE_SCSI_REQUEST_BLOCK, SRB_TYPE_STORAGE_REQUEST_BLOCK, STORAGE_ADAPTER_DESCRIPTOR, STORAGE_ADAPTER_DESCRIPTOR structure [Storage Devices], STORAGE_ADDRESS_TYPE_BTL8, _STORAGE_ADAPTER_DESCRIPTOR, ntddstor/PSTORAGE_ADAPTER_DESCRIPTOR, ntddstor/STORAGE_ADAPTER_DESCRIPTOR, storage.storage_adapter_descriptor, structs-general_196c7640-0a2d-4567-8958-1244c46b84a6.xml
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
req.irql: 
targetos: Windows
req.typenames: STORAGE_ADAPTER_DESCRIPTOR, PSTORAGE_ADAPTER_DESCRIPTOR
f1_keywords:
 - _STORAGE_ADAPTER_DESCRIPTOR
 - ntddstor/_STORAGE_ADAPTER_DESCRIPTOR
 - PSTORAGE_ADAPTER_DESCRIPTOR
 - ntddstor/PSTORAGE_ADAPTER_DESCRIPTOR
 - STORAGE_ADAPTER_DESCRIPTOR
 - ntddstor/STORAGE_ADAPTER_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_ADAPTER_DESCRIPTOR
 - PSTORAGE_ADAPTER_DESCRIPTOR
 - STORAGE_ADAPTER_DESCRIPTOR
---

# STORAGE_ADAPTER_DESCRIPTOR structure

## -description

The **STORAGE_ADAPTER_DESCRIPTOR** structure is used in conjunction with the [**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) request to retrieve the storage adapter descriptor data for a device.

## -struct-fields

### -field Version

Contains the version of the structure **STORAGE_ADAPTER_DESCRIPTOR**. The value of this member will change as members are added to the structure.

### -field Size

Specifies the total size of the descriptor, in bytes.

### -field MaximumTransferLength

Specifies the maximum number of bytes the host bus adapter (HBA) can transfer in a single operation.

### -field MaximumPhysicalPages

Specifies the maximum number of discontinuous physical pages the HBA can manage in a single transfer (in other words, the extent of its scatter/gather support).

### -field AlignmentMask

Specifies the HBA's alignment requirements for transfers. A storage class driver sets the **AlignmentRequirement** field in its device objects to this value. The alignment mask indicates alignment restrictions for buffers required by the HBA for transfer operations. The valid mask values are 0 (byte aligned), 1 (word aligned), 3 (DWORD aligned), and 7 (double DWORD aligned).

### -field AdapterUsesPio

Indicates when **TRUE** that the HBA uses Programmed Input/Output (PIO) and requires the use of system-space virtual addresses mapped to physical memory for data buffers. When **FALSE**, the HBA does not use PIO.

### -field AdapterScansDown

Indicates when **TRUE** that the HBA scans down for BIOS devices, that is, the HBA begins scanning with the highest device number rather than the lowest. When **FALSE**, the HBA begins scanning with the lowest device number. This member is reserved for legacy miniport drivers.

### -field CommandQueueing

Indicates when **TRUE** that the HBA supports SCSI-tagged queuing and/or per-logical-unit internal queues, or the non-SCSI equivalent. When **FALSE**, the HBA neither supports SCSI-tagged queuing nor per-logical-unit internal queues.

### -field AcceleratedTransfer

Indicates when **TRUE** that the HBA supports synchronous transfers as a way of speeding up I/O. When **FALSE**, the HBA does not support synchronous transfers as a way of speeding up I/O.

### -field BusType

Specifies a value of type [**STORAGE_BUS_TYPE**](ne-ntddstor-storage_bus_type.md) that indicates the type of bus to which the device is connected.

### -field BusMajorVersion

Specifies the major version number, if any, of the HBA.

### -field BusMinorVersion

Specifies the minor version number, if any, of the HBA.

### -field SrbType

Specifies the SCSI request block (SRB) type used by the HBA. This member is valid starting with Windows 8.

| Value | Meaning |
| ----- | ------- |
| SRB_TYPE_SCSI_REQUEST_BLOCK | The HBA uses SCSI request blocks. |
| SRB_TYPE_STORAGE_REQUEST_BLOCK | The HBA uses extended SCSI request blocks. |

### -field AddressType

Specifies the address type of the HBA. This member is valid starting with Windows 8.

| Value | Meaning |
| ----- | ------- |
| STORAGE_ADDRESS_TYPE_BTL8 | The HBA uses 8-bit bus, target, and LUN addressing. |

## -remarks

Storage class drivers issue a device-control request with the I/O control code [**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) to retrieve this structure, which contains configuration information from the HBA for data transfer operations. The structure can be retrieved either from the device object for the bus or from a functional device object (FDO), which forwards the request to the underlying bus.

If excessive protocol errors occur on an HBA that supports synchronous transfers (**AcceleratedTransfer** is **TRUE**), the storage class driver can disable synchronous transfers by setting SRB_FLAGS_DISABLE_SYNCH_TRANSFER in SRBs.

## -see-also

[**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md)

[**IoBuildDeviceIoControlRequest**](../wdm/nf-wdm-iobuilddeviceiocontrolrequest.md)

[**STORAGE_ADAPTER_DESCRIPTOR**](ns-ntddstor-_storage_adapter_descriptor.md)

[**STORAGE_BUS_TYPE**](ne-ntddstor-storage_bus_type.md)

[**STORAGE_DESCRIPTOR_HEADER**](ns-ntddstor-_storage_descriptor_header.md)

[**STORAGE_DEVICE_DESCRIPTOR**](ns-ntddstor-_storage_device_descriptor.md)

[**STORAGE_DEVICE_ID_DESCRIPTOR**](ns-ntddstor-_storage_device_id_descriptor.md)
