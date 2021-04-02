---
UID: NE:ntddstor._STORAGE_BUS_TYPE
tech.root: storage
title: STORAGE_BUS_TYPE
ms.date: 04/01/2021
targetos: Windows
description: The STORAGE_BUS_TYPE enumeration provides a symbolic means of representing the various types of storage buses.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_BUS_TYPE
 - PSTORAGE_BUS_TYPE
 - STORAGE_BUS_TYPE
f1_keywords:
 - _STORAGE_BUS_TYPE
 - ntddstor/_STORAGE_BUS_TYPE
 - PSTORAGE_BUS_TYPE
 - ntddstor/PSTORAGE_BUS_TYPE
 - STORAGE_BUS_TYPE
 - ntddstor/STORAGE_BUS_TYPE
dev_langs:
 - c++
---

## -description

The STORAGE_BUS_TYPE enumeration provides a symbolic means of representing the various types of storage buses.

## -enum-fields

### -field BusTypeUnknown

Indicates an unknown bus type.

### -field BusTypeScsi

Indicates a small computer system interface (SCSI) bus.

### -field BusTypeAtapi

Indicates an AT Attachment Packet Interface (ATAPI) bus.

### -field BusTypeAta

Indicates an advanced technology attachment (ATA) bus.

### -field BusType1394

Indicates an IEEE 1394 bus.

### -field BusTypeSsa

Indicates a serial storage architecture (SSA) bus.

### -field BusTypeFibre

Indicates a fibre channel bus type.

### -field BusTypeUsb

Indicates a USB bus type.

### -field BusTypeRAID

Indicates a bus for a redundant array of independent disks (RAID).

### -field BusTypeiScsi

Indicates an iSCSI bus.

### -field BusTypeSas

Indicates a serial-attached SCSI bus.

### -field BusTypeSata

Indicates a serial ATA bus.

### -field BusTypeSd

Indicates a secure digital bus.

### -field BusTypeMmc

Indicates a multimedia card bus.

### -field BusTypeVirtual

Indicates a virtual storage bus.

### -field BusTypeFileBackedVirtual

Indicates a virtual file backed storage bus.

### -field BusTypeSpaces

Indicates a storage spaces bus.

### -field BusTypeNvme

Indicates a non-volatile memory express (NVMe) bus.

### -field BusTypeSCM

Indicates a storage class memory (SCM) bus.

### -field BusTypeUfs

Indicates a universal flash storage (UFS) bus.

### -field BusTypeMax

Indicates the current maximum value for this enumeration. Do not use this value because it changes as new bus types are added.

### -field BusTypeMaxReserved

Reserved. Do not use.

## -remarks

## -see-also

[**DEVICE_MEDIA_INFO**](ns-ntddstor-_device_media_info.md)

[**STORAGE_ADAPTER_DESCRIPTOR**](ns-ntddstor-_storage_adapter_descriptor.md)
