---
UID: NE:ehstorbandmgmt.LOCKSTATE
tech.root: storage
title: LOCKSTATE
ms.date: 03/12/2024
targetos: Windows
description: Indicates the current lock state of the device.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ehstorbandmgmt.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: true
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ehstorbandmgmt.h
api_name:
 - LOCKSTATE
f1_keywords:
 - LOCKSTATE
 - ehstorbandmgmt/LOCKSTATE
dev_langs:
 - c++
helpviewer_keywords:
 - LOCKSTATE
---

# LOCKSTATE enumeration (ehstorbandmgmt.h)

## -description

Indicates the current lock state of the device.

## -enum-fields

### -field INVALID_LOCK_STATE

The device is in an invalid lock state.

### -field PERSISTENT_UNLOCK

The device is unlocked and remains unlocked on power reset.

### -field NONPERSISTENT_UNLOCK

The device is unlocked but gets locked on power reset.

### -field PERSISTENT_LOCK

The device is locked and remains locked on power reset.

## -remarks

## -see-also
