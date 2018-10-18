---
UID: NF:sensorsutils.PropKeyFindKeyGetUlong
title: PropKeyFindKeyGetUlong function
author: windows-driver-content
description: This routine gets a ULONG value from a PROPVARIANT within a collection list based on the PROPERTYKEY.
ms.assetid: e3c390be-bebf-400d-9650-b7e3d0ff5a23
ms.date: 08/08/18
tech.root: sensors
ms.topic: function
ms.keywords: PropKeyFindKeyGetUlong
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
-	PropKeyFindKeyGetUlong
product:
 - Windows
targetos: Windows


---

# PropKeyFindKeyGetUlong function


## -description

This routine gets a ULONG value from a PROPVARIANT within a collection list based on the PROPERTYKEY.



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
