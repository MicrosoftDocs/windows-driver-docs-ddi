---
UID: NE:ntifs._VIRTUAL_STORAGE_BEHAVIOR_CODE
title: _VIRTUAL_STORAGE_BEHAVIOR_CODE (ntifs.h)
description: Configures file system-specific behaviors used on virtual storage devices.
ms.assetid: 36f84aed-a906-4c02-bde0-0313f361bf78
tech.root: ifsk
ms.date: 10/19/2018
keywords: ["VIRTUAL_STORAGE_BEHAVIOR_CODE enumeration"]
ms.keywords: _VIRTUAL_STORAGE_BEHAVIOR_CODE, VIRTUAL_STORAGE_BEHAVIOR_CODE, *PVIRTUAL_STORAGE_BEHAVIOR_CODE,
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10 (Version 1803)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: VIRTUAL_STORAGE_BEHAVIOR_CODE, *PVIRTUAL_STORAGE_BEHAVIOR_CODE
targetos: Windows
f1_keywords:
 - _VIRTUAL_STORAGE_BEHAVIOR_CODE
 - ntifs/_VIRTUAL_STORAGE_BEHAVIOR_CODE
 - PVIRTUAL_STORAGE_BEHAVIOR_CODE
 - ntifs/PVIRTUAL_STORAGE_BEHAVIOR_CODE
 - VIRTUAL_STORAGE_BEHAVIOR_CODE
 - ntifs/VIRTUAL_STORAGE_BEHAVIOR_CODE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _VIRTUAL_STORAGE_BEHAVIOR_CODE
---

# _VIRTUAL_STORAGE_BEHAVIOR_CODE enumeration


## -description

Configures file system-specific behaviors used on virtual storage devices.

## -enum-fields

### -field VirtualStorageBehaviorUndefined 

Specifies the behavior of the virtual storage device is undefined.

### -field VirtualStorageBehaviorCacheWriteThrough 

Specifies to use Write-Through caching on the virtual storage device.

### -field VirtualStorageBehaviorCacheWriteBack 

Specifies to use Write-Back caching on the virtual storage device.

## -remarks

## -see-also

