---
UID: NS:ntddstor._STORAGE_DEVICE_LED_STATE_DESCRIPTOR
tech.root: storage
title: STORAGE_DEVICE_LED_STATE_DESCRIPTOR
ms.date: 05/13/2021
targetos: Windows
description: The STORAGE_DEVICE_LED_STATE_DESCRIPTOR structure describes the LED state of a device.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: STORAGE_DEVICE_LED_STATE_DESCRIPTOR, *PSTORAGE_DEVICE_LED_STATE_DESCRIPTOR
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_DEVICE_LED_STATE_DESCRIPTOR
 - PSTORAGE_DEVICE_LED_STATE_DESCRIPTOR
 - STORAGE_DEVICE_LED_STATE_DESCRIPTOR
f1_keywords:
 - _STORAGE_DEVICE_LED_STATE_DESCRIPTOR
 - ntddstor/_STORAGE_DEVICE_LED_STATE_DESCRIPTOR
 - PSTORAGE_DEVICE_LED_STATE_DESCRIPTOR
 - ntddstor/PSTORAGE_DEVICE_LED_STATE_DESCRIPTOR
 - STORAGE_DEVICE_LED_STATE_DESCRIPTOR
 - ntddstor/STORAGE_DEVICE_LED_STATE_DESCRIPTOR
dev_langs:
 - c++
---

## -description

The STORAGE_DEVICE_LED_STATE_DESCRIPTOR structure describes the LED state of a device.

## -struct-fields

### -field Version

Version of this structure. Set to ```sizeof(STORAGE_DEVICE_LED_STATE_DESCRIPTOR)```.

### -field Size

Size of this structure, in bytes. Must be >= ```sizeof(STORAGE_DEVICE_LED_STATE_DESCRIPTOR)```.

### -field State

Opaque structure that contains the unit's LED state.

## -remarks

The unit's LED state is returned in a **STORAGE_DEVICE_LED_STATE_DESCRIPTOR** structure during an [**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) request with a **PropertyId** of **StorageDeviceLedStateProperty**.

## -see-also

[**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md)

[**STORAGE_PROPERTY_ID**](ne-ntddstor-storage_property_id.md)

[**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md)
