---
UID: NF:sensorsutils.PropKeyFindKeyGetNthInt64
title: PropKeyFindKeyGetNthInt64 function (sensorsutils.h)
description: This routine gets the nth INT64 value from a PROPVARIANT within a collection list based on the PROPERTYKEY.
ms.date: 08/08/2018
keywords: ["PropKeyFindKeyGetNthInt64 function"]
tech.root: sensors
ms.keywords: PropKeyFindKeyGetNthInt64
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - PropKeyFindKeyGetNthInt64
 - sensorsutils/PropKeyFindKeyGetNthInt64
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - sensorsutils.h
api_name:
 - PropKeyFindKeyGetNthInt64
product:
 - Windows
---

# PropKeyFindKeyGetNthInt64 function


## -description

This routine gets the nth INT64 value from a PROPVARIANT within a collection list based on the PROPERTYKEY.

## -parameters

### -param pList

[in] Pointer to the list of PROPVARIANT collection.

### -param pKey

[in] Pointer to a PROPERTYKEY for the target PROPVARIANT.

### -param Occurrence

[in] Zero based number of occurrence the PROPERTYKEY must be found before returning the value.

### -param pRetValue

[out] Pointer to the output buffer.

## -returns

This function returns one of the following NTSTATUS codes:

* STATUS_INVALID_PARAMETER if *pList*, *pKey* or, *pRetValue* is nullptr.
* STATUS_NOT_FOUND if the element at *Occurrence* was not found.
* STATUS_SUCCESS on success.

## -remarks

## -see-also

