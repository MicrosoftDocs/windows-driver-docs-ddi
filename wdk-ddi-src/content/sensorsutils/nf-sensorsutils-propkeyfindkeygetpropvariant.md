---
UID: NF:sensorsutils.PropKeyFindKeyGetPropVariant
title: PropKeyFindKeyGetPropVariant function (sensorsutils.h)
description: This routine finds the PROPVARIANT from a collection list based on the PROPERTYKEY.
ms.assetid: f649dbee-d3c5-4fd0-afa8-1afa64a97cf6
ms.date: 08/08/2018
tech.root: sensors
ms.topic: function
f1_keywords:
 - "sensorsutils/PropKeyFindKeyGetPropVariant"
ms.keywords: PropKeyFindKeyGetPropVariant
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
- PropKeyFindKeyGetPropVariant
product:
  - Windows
targetos: Windows


ms.custom: RS5
---

# PropKeyFindKeyGetPropVariant function


## -description

This routine finds the PROPVARIANT from a collection list based on the PROPERTYKEY.



## -parameters

### -param pList

[in] Pointer to the list of PROPVARIANT collection.

### -param pKey

[in] Pointer to a PROPERTYKEY for the target PROPVARIANT.

### -param TypeCheck

[in] If TRUE, the function validates whether a  *pValue* type matches one of the value types found in *pList*.

### -param pValue

[in/out] Pointer to the target PROPVARIANT.

## -returns

This function returns one of the following NTSTATUS codes:

* STATUS_INVALID_PARAMETER if *pList*, *pKey* or, *pValue* is nullptr.
* STATUS_NOT_FOUND if the element associated with the propertyKey was not found.
* STATUS_SUCCESS on success.

## -remarks

## -see-also
