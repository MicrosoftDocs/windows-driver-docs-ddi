---
UID: NF:sensorsutils.PropKeyFindKeyGetNthUlong
title: PropKeyFindKeyGetNthUlong function
author: windows-driver-content
description: This routine gets the nth ULONG value from a PROPVARIANT within a collection list based on the PROPERTYKEY.
ms.assetid: d5e82a5a-0b6f-4246-9f4e-de40b1a5ce6c
ms.author: windowsdriverdev
ms.date: 08/08/18
ms.prod: windows-hardware
ms.technology: windows-devices
tech.root: sensors
ms.topic: function
ms.keywords: PropKeyFindKeyGetNthUlong
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
-	apiref
api_type: 
-	LibDef
api_location: 
-	sensorsutils.h
api_name: 
-	PropKeyFindKeyGetNthUlong
product:
  - Windows
targetos: Windows


---

# PropKeyFindKeyGetNthUlong function


## -description

This routine gets the nth ULONG value from a PROPVARIANT within a collection list based on the PROPERTYKEY.


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