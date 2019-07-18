---
UID: NS:ntddstor._STORAGE_PROPERTY_SET
title: STORAGE_PROPERTY_SET
author: windows-driver-content
description: The STORAGE_PROPERTY_SET structure describes the details of the property set associated with IOCTL_STORAGE_SET_PROPERTY.
tech.root: storage
ms.assetid: c1b43348-1372-4dfd-9ee7-448c35e6a0b6
ms.author: windowsdriverdev
ms.date: 03-07-2019
ms.topic: struct
f1_keywords:
 - "ntddstor/STORAGE_PROPERTY_SET"
ms.keywords: STORAGE_PROPERTY_SET, STORAGE_PROPERTY_SET, *PSTORAGE_PROPERTY_SET, 
req.header: ntddstor.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: STORAGE_PROPERTY_SET, *PSTORAGE_PROPERTY_SET
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddstor.h
api_name: 
 - STORAGE_PROPERTY_SET
product: Windows
targetos: Windows
ms.custom: 19H1
---

# STORAGE_PROPERTY_SET structure

## -description

The STORAGE_PROPERTY_SET structure describes the details of the property set associated with [IOCTL_STORAGE_SET_PROPERTY](ni-ntddstor-ioctl_storage_set_property.md).

## -struct-fields

### -field PropertyId

A [STORAGE_PROPERTY_ID](ne-ntddstor-storage_property_id.md) enum value that specifies which property is being set. Currently, should be set to **StorageAdapterProtocolSpecificProperty**.

### -field SetType

A [STORAGE_SET_TYPE](ne-ntddstor-storage_set_type.md) enum value that describes the type of set operation being performed.

### -field AdditionalParameters

Space for additional parameters if necessary, depending on **PropertyId**.

## -remarks

## -see-also

[IOCTL_STORAGE_SET_PROPERTY](ni-ntddstor-ioctl_storage_set_property.md)

[STORAGE_PROPERTY_ID](ne-ntddstor-storage_property_id.md)

[STORAGE_SET_TYPE](ne-ntddstor-storage_set_type.md)
