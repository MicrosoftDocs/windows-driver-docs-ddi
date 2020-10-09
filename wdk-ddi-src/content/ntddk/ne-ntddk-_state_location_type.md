---
UID: NE:ntddk._STATE_LOCATION_TYPE
title: _STATE_LOCATION_TYPE (ntddk.h)
description: Defines values for persisted state locations for device and driver files.
ms.assetid: b1f859c2-ea58-4c37-9451-4521b83e3e8b
ms.date: 10/19/2018
keywords: ["STATE_LOCATION_TYPE enumeration"]
ms.keywords: _STATE_LOCATION_TYPE, STATE_LOCATION_TYPE,
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: STATE_LOCATION_TYPE
targetos: Windows
f1_keywords:
 - _STATE_LOCATION_TYPE
 - ntddk/_STATE_LOCATION_TYPE
 - STATE_LOCATION_TYPE
 - ntddk/STATE_LOCATION_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _STATE_LOCATION_TYPE
---

# _STATE_LOCATION_TYPE enumeration


## -description

Defines values for persisted state locations for device and driver files. This enumeration is used by [**RtlGetPersistedStateLocation**](nf-ntddk-rtlgetpersistedstatelocation.md).

## -enum-fields

### -field LocationTypeRegistry

The device and driver files are stored in the registry.

### -field LocationTypeFileSystem

The device and driver files are stored in the file system.

### -field LocationTypeMaximum

Reserved.

## -remarks

## -see-also

[**RtlGetPersistedStateLocation**](nf-ntddk-rtlgetpersistedstatelocation.md)

