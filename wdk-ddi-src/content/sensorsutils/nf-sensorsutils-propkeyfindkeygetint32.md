---
UID: NF:sensorsutils.PropKeyFindKeyGetInt32
title: PropKeyFindKeyGetInt32 function (sensorsutils.h)
description: This routine gets a INT32 value from a PROPVARIANT within a collection list based on the PROPERTYKEY.
ms.assetid: 324dc740-750d-4e93-9c1c-af4e77254672
ms.date: 08/08/2018
tech.root: sensors
f1_keywords:
 - "sensorsutils/PropKeyFindKeyGetInt32"
ms.keywords: PropKeyFindKeyGetInt32
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
- PropKeyFindKeyGetInt32
product:
  - Windows
targetos: Windows


ms.custom: RS5
---

# PropKeyFindKeyGetInt32 function


## -description

This routine gets a INT32 value from a PROPVARIANT within a collection list based on the PROPERTYKEY.


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
