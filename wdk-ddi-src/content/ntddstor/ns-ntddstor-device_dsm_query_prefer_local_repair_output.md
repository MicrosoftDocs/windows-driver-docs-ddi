---
UID: NS:ntddstor._DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT
tech.root: storage
title: DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT
ms.date: 03/15/2024
targetos: Windows
description: The DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT structure indicates if the device prefers local repair of storage spaces.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT, *PDEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT
 - PDEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT
 - DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT
f1_keywords:
 - _DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT
 - ntddstor/_DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT
 - PDEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT
 - ntddstor/PDEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT
 - DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT
 - ntddstor/DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT
dev_langs:
 - c++
helpviewer_keywords:
 - _DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT
---

# DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT structure (ntddstor.h)

## -description

The **DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT** structure indicates if the device prefers local repair of storage spaces.

## -struct-fields

### -field Version

The size of this structure. This is set to `sizeof(DEVICE_DSM_QUERY_PREFER_LOCAL_REPAIR_OUTPUT)`.

### -field PreferLocalRepair

Indicates if the device prefers local repair of storage spaces.

## -remarks

## -see-also
