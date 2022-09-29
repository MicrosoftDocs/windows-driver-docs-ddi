---
UID: NS:ntddstor._STORAGE_PHYSICAL_ADAPTER_DATA
title: STORAGE_PHYSICAL_ADAPTER_DATA (ntddstor.h)
description: Specifies the physical device data of a storage adapter.
old-location: storage\storage_physical_adapter_data.htm
tech.root: storage
ms.date: 08/18/2022
keywords: ["STORAGE_PHYSICAL_ADAPTER_DATA structure"]
ms.keywords: "*PSTORAGE_PHYSICAL_ADAPTER_DATA, PSTORAGE_PHYSICAL_ADAPTER_DATA, PSTORAGE_PHYSICAL_ADAPTER_DATA structure pointer [Storage Devices], STORAGE_PHYSICAL_ADAPTER_DATA, STORAGE_PHYSICAL_ADAPTER_DATA structure [Storage Devices], _STORAGE_PHYSICAL_ADAPTER_DATA, ntddstor/PSTORAGE_PHYSICAL_ADAPTER_DATA, ntddstor/STORAGE_PHYSICAL_ADAPTER_DATA, storage.storage_physical_adapter_data"
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
req.typenames: STORAGE_PHYSICAL_ADAPTER_DATA, *PSTORAGE_PHYSICAL_ADAPTER_DATA
f1_keywords:
 - _STORAGE_PHYSICAL_ADAPTER_DATA
 - ntddstor/_STORAGE_PHYSICAL_ADAPTER_DATA
 - PSTORAGE_PHYSICAL_ADAPTER_DATA
 - ntddstor/PSTORAGE_PHYSICAL_ADAPTER_DATA
 - STORAGE_PHYSICAL_ADAPTER_DATA
 - ntddstor/STORAGE_PHYSICAL_ADAPTER_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - _STORAGE_PHYSICAL_ADAPTER_DATA
 - PSTORAGE_PHYSICAL_ADAPTER_DATA
 - STORAGE_PHYSICAL_ADAPTER_DATA
---

# STORAGE_PHYSICAL_ADAPTER_DATA structure

## -description

Specifies the physical data of a storage adapter.

## -struct-fields

### -field AdapterId

The hardware ID of the storage adapter.

### -field HealthStatus

A [**STORAGE_COMPONENT_HEALTH_STATUS**](ne-ntddstor-_storage_component_health_status.md) value that indicates the health status of a storage adapter.

### -field CommandProtocol

A [**STORAGE_PROTOCOL_TYPE**](ne-ntddstor-_storage_protocol_type.md) value that specifies the storage command protocols that are used between software and hardware.

### -field SpecVersion

A [**STORAGE_SPEC_VERSION**](ns-ntddstor-_storage_spec_version.md) structure that specifies the storage specification version of the storage adapter.

### -field Vendor[8]

The vendor name of the storage adapter

### -field Model[40]

The model name of the storage adapter.

### -field FirmwareRevision[16]

The firmware revision number of the storage adapter.

### -field PhysicalLocation[32]

This member is reserved for future use.

### -field ExpanderConnected

Indicates whether a storage expander is connected to the storage adapter.

### -field Reserved0[3]

Reserved; do not use.

### -field Reserved1[3]

Reserved; do not use.

## -see-also

[**STORAGE_PHYSICAL_NODE_DATA**](ns-ntddstor-_storage_physical_node_data.md)
