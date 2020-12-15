---
UID: NF:sensorsutils.PropKeyFindKeyGetUshort
title: PropKeyFindKeyGetUshort function (sensorsutils.h)
description: This routine gets a USHORT value from a PROPVARIANT within a collection list based on the PROPERTYKEY.
ms.date: 08/08/2018
keywords: ["PropKeyFindKeyGetUshort function"]
tech.root: sensors
ms.keywords: PropKeyFindKeyGetUshort
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
 - PropKeyFindKeyGetUshort
 - sensorsutils/PropKeyFindKeyGetUshort
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - sensorsutils.h
api_name:
 - PropKeyFindKeyGetUshort
product:
 - Windows
---

# PropKeyFindKeyGetUshort function


## -description

This routine gets a USHORT value from a PROPVARIANT within a collection list based on the PROPERTYKEY.

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

