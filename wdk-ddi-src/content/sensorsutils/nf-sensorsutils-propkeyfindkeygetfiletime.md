---
UID: NF:sensorsutils.PropKeyFindKeyGetFileTime
title: PropKeyFindKeyGetFileTime function (sensorsutils.h)
description: This routine gets a FILETIME value from a PROPVARIANT within a collection list based on the PROPERTYKEY.
ms.assetid: 87d6d150-2b52-468a-b6da-45179bf823cb
ms.date: 08/08/2018
tech.root: sensors
ms.topic: function
ms.keywords: PropKeyFindKeyGetFileTime
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
- PropKeyFindKeyGetFileTime
product:
  - Windows
targetos: Windows


ms.custom: RS5
---

# PropKeyFindKeyGetFileTime function


## -description

This routine gets a FILETIME value from a PROPVARIANT within a collection list based on the PROPERTYKEY.


## -parameters

### -param pList

[in] Pointer to the list of PROPVARIANT collection.

### -param pKey

[in] Pointer to a PROPERTYKEY for the target PROPVARIANT.

### -param pRetValue

[out] Pointer to the output buffer.

## -returns

This function returns the following NTSTATUS codes:

* STATUS_INVALID_PARAMETER if pList, pKey or, pRetValue is nullptr.
* STATUS_NOT_FOUND if the element identified by pKey was not found.
* STATUS_SUCCESS on success.

## -remarks

## -see-also
