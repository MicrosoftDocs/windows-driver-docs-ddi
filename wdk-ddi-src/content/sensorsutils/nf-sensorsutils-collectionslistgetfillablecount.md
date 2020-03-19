---
UID: NF:sensorsutils.CollectionsListGetFillableCount
title: CollectionsListGetFillableCount function (sensorsutils.h)
description: Returns the number of elements a SENSOR_COLLECTION_LIST buffer of a certain size can possibly hold.
ms.assetid: 36d2a3c0-ee27-4620-a783-9d910907d2fa
ms.date: 08/08/2018
keywords: ["CollectionsListGetFillableCount function"]
f1_keywords:
 - "sensorsutils/CollectionsListGetFillableCount"
tech.root: sensors
ms.keywords: CollectionsListGetFillableCount
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
- CollectionsListGetFillableCount
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# CollectionsListGetFillableCount function


## -description

Returns the number of elements a SENSOR_COLLECTION_LIST buffer of a certain size can possibly hold.

## -parameters

### -param BufferSizeBytes

Size of the buffer in bytes.

## -returns

The number of SENSOR_VALUE_PAIR that is acceptable for a SENSOR_COLLECTION_LIST of BufferSizeBytes size.

## -remarks

## -see-also
