---
UID: NE:ntddstor._STORAGE_COMPONENT_HEALTH_STATUS
title: _STORAGE_COMPONENT_HEALTH_STATUS (ntddstor.h)
description: Indicates the health status of a storage device.
old-location: storage\storage_component_health_status.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["STORAGE_COMPONENT_HEALTH_STATUS enumeration"]
ms.keywords: "*PSTORAGE_COMPONENT_HEALTH_STATUS, HealthStatusDisabled, HealthStatusFailed, HealthStatusNormal, HealthStatusThrottled, HealthStatusUnknown, HealthStatusWarning, PSTORAGE_COMPONENT_HEALTH_STATUS, PSTORAGE_COMPONENT_HEALTH_STATUS enumeration pointer [Storage Devices], STORAGE_COMPONENT_HEALTH_STATUS, STORAGE_COMPONENT_HEALTH_STATUS enumeration [Storage Devices], _STORAGE_COMPONENT_HEALTH_STATUS, ntddstor/HealthStatusDisabled, ntddstor/HealthStatusFailed, ntddstor/HealthStatusNormal, ntddstor/HealthStatusThrottled, ntddstor/HealthStatusUnknown, ntddstor/HealthStatusWarning, ntddstor/PSTORAGE_COMPONENT_HEALTH_STATUS, ntddstor/STORAGE_COMPONENT_HEALTH_STATUS, storage.storage_component_health_status"
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
req.typenames: STORAGE_COMPONENT_HEALTH_STATUS, *PSTORAGE_COMPONENT_HEALTH_STATUS
f1_keywords:
 - _STORAGE_COMPONENT_HEALTH_STATUS
 - ntddstor/_STORAGE_COMPONENT_HEALTH_STATUS
 - PSTORAGE_COMPONENT_HEALTH_STATUS
 - ntddstor/PSTORAGE_COMPONENT_HEALTH_STATUS
 - STORAGE_COMPONENT_HEALTH_STATUS
 - ntddstor/STORAGE_COMPONENT_HEALTH_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - _STORAGE_COMPONENT_HEALTH_STATUS
 - PSTORAGE_COMPONENT_HEALTH_STATUS
 - STORAGE_COMPONENT_HEALTH_STATUS
---

# _STORAGE_COMPONENT_HEALTH_STATUS enumeration


## -description

Indicates the health status of a storage device.

## -enum-fields

### -field HealthStatusUnknown

The storage device health status is unknown.

### -field HealthStatusNormal

The storage device is operating normally.

### -field HealthStatusThrottled

The storage device has been throttled.

### -field HealthStatusWarning

The storage device has issued a warning.

### -field HealthStatusDisabled

The storage device has been disabled.

### -field HealthStatusFailed

The storage device has failed.

