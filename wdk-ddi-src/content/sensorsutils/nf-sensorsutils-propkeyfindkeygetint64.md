---
UID: NF:sensorsutils.PropKeyFindKeyGetInt64
title: PropKeyFindKeyGetInt64 function (sensorsutils.h)
description: This routine gets a INT64 value from a PROPVARIANT within a collection list based on the PROPERTYKEY.
ms.assetid: 61811522-9d31-4246-8cdd-71be1a8ff43e
ms.date: 08/08/2018
tech.root: sensors
ms.topic: function
f1_keywords:
 - "sensorsutils/PropKeyFindKeyGetInt64"
ms.keywords: PropKeyFindKeyGetInt64
req.header: sensorsutils.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- sensorsutils.h
api_name: 
- PropKeyFindKeyGetInt64
product:
  - Windows
targetos: Windows


ms.custom: RS5
---

# PropKeyFindKeyGetInt64 function


## -description

This routine gets a INT64 value from a PROPVARIANT within a collection list based on the PROPERTYKEY.


## -parameters

### -param pList

[in] Pointer to the list of PROPVARIANT collection.

### -param pKey

[in] Pointer to a PROPERTYKEY for the target PROPVARIANT.

### -param pRetValue

[out] Pointer to the output buffer.

## -returns

This function returns one of the following NTSTATUS codes:

* STATUS_INVALID_PARAMETER if *pList*, *pKey* or, *pRetValue* is nullptr.
* STATUS_NOT_FOUND if the element identified by *pKey* was not found.
* STATUS_SUCCESS on success.

## -remarks

## -see-also
