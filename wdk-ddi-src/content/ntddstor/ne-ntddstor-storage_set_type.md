---
UID: NE:ntddstor._STORAGE_SET_TYPE
title: STORAGE_SET_TYPE
author: windows-driver-content
description: 
tech.root: storage
ms.assetid: 0567d57c-b136-48f4-9f70-b076b6625b7d
ms.author: windowsdriverdev
ms.date: 3/21/2019
ms.topic: enum
ms.keywords: STORAGE_SET_TYPE, STORAGE_SET_TYPE, *PSTORAGE_SET_TYPE, STORAGE_PROPERTY_SET, IOCTL_STORAGE_SET_PROPERTY
req.header: ntddstor.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: STORAGE_SET_TYPE, *PSTORAGE_SET_TYPE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddstor.h
api_name: 
 - STORAGE_SET_TYPE
product: Windows
targetos: Windows
---

# STORAGE_SET_TYPE enumeration

## -description

STORAGE_SET_TYPE describes the type of set operation that is being performed via an [IOCTL_STORAGE_SET_PROPERTY](ni-ntddstor-ioctl_storage_set_property.md) IOCTL.

## -enum-fields

### -field PropertyStandardSet

Use **PropertyStandardSet** to change the value of a property.

### -field PropertyExistsSet

Use **PropertyExistsSet** to test whether a property is supported.

### -field PropertySetMaxDefined

Do not use.

## -remarks

**STORAGE_SET_TYPE** is a member of the [STORAGE_PROPERTY_SET](ns-ntddstor-storage_property_set.md) structure, which describes the details of the property set associated with an IOCTL_STORAGE_SET_PROPERTY IOCTL.

## -see-also

[IOCTL_STORAGE_SET_PROPERTY](ni-ntddstor-ioctl_storage_set_property.md)

[STORAGE_PROPERTY_SET](ns-ntddstor-storage_property_set.md)
