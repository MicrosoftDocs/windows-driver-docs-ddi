---
UID: NS:ntddstor._STORAGE_PHYSICAL_DEVICE_DATA
title: STORAGE_PHYSICAL_DEVICE_DATA (ntddstor.h)
description: Specifies the physical device data of a storage device.
old-location: storage\storage_physical_device_data.htm
tech.root: storage
ms.date: 08/18/2022
keywords: ["STORAGE_PHYSICAL_DEVICE_DATA structure"]
ms.keywords: "*PSTORAGE_PHYSICAL_DEVICE_DATA, PSTORAGE_PHYSICAL_DEVICE_DATA, PSTORAGE_PHYSICAL_DEVICE_DATA structure pointer [Storage Devices], STORAGE_PHYSICAL_DEVICE_DATA, STORAGE_PHYSICAL_DEVICE_DATA structure [Storage Devices], _STORAGE_PHYSICAL_DEVICE_DATA, ntddstor/PSTORAGE_PHYSICAL_DEVICE_DATA, ntddstor/STORAGE_PHYSICAL_DEVICE_DATA, storage.storage_physical_device_data"
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
req.typenames: STORAGE_PHYSICAL_DEVICE_DATA, *PSTORAGE_PHYSICAL_DEVICE_DATA
f1_keywords:
 - _STORAGE_PHYSICAL_DEVICE_DATA
 - ntddstor/_STORAGE_PHYSICAL_DEVICE_DATA
 - PSTORAGE_PHYSICAL_DEVICE_DATA
 - ntddstor/PSTORAGE_PHYSICAL_DEVICE_DATA
 - STORAGE_PHYSICAL_DEVICE_DATA
 - ntddstor/STORAGE_PHYSICAL_DEVICE_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - _STORAGE_PHYSICAL_DEVICE_DATA
 - PSTORAGE_PHYSICAL_DEVICE_DATA
 - STORAGE_PHYSICAL_DEVICE_DATA
---

# STORAGE_PHYSICAL_DEVICE_DATA structure

## -description

Specifies the physical data of a storage device.

## -struct-fields

### -field DeviceId

The hardware ID of the storage device.

### -field Role

The role of the storage device. This value can be a bitmask of the following values to specify multiple roles:

* STORAGE_COMPONENT_ROLE_CACHE (0x00000001)
* STORAGE_COMPONENT_ROLE_TIERING (0x00000002)
* STORAGE_COMPONENT_ROLE_DATA (0x00000004)

### -field HealthStatus

A [**STORAGE_COMPONENT_HEALTH_STATUS**](ne-ntddstor-_storage_component_health_status.md) value that indicates the health status of a storage device.

### -field CommandProtocol

A [**STORAGE_PROTOCOL_TYPE**](ne-ntddstor-_storage_protocol_type.md) value that specifies the storage command protocols that are used between software and hardware.

### -field SpecVersion

A [**STORAGE_SPEC_VERSION**](ns-ntddstor-_storage_spec_version.md) structure that specifies the storage specification version of the storage device.

### -field FormFactor

A [**STORAGE_DEVICE_FORM_FACTOR**](ne-ntddstor-_storage_device_form_factor.md) value that indicates the form factor of a storage device.

### -field Vendor[8]

The vendor name of the storage device.

### -field Model[40]

The model name of the storage device.

### -field FirmwareRevision[16]

The revision number of the storage device.

### -field Capacity

The capacity of the storage device in units of kilobytes (1024 bytes).

### -field PhysicalLocation[32]

This member is reserved for future use.

### -field Reserved[2]

Reserved; do not use.

## -see-also

[**STORAGE_PHYSICAL_NODE_DATA**](ns-ntddstor-_storage_physical_node_data.md)
