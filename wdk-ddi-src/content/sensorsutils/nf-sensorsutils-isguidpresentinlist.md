---
UID: NF:sensorsutils.IsGUIDPresentInList
title: IsGUIDPresentInList function (sensorsutils.h)
description: This routine looks for a GUID in a list of GUIDs.
ms.assetid: e6209d36-e01c-4922-9dfa-c3e41eb0285e
ms.date: 08/08/2018
keywords: ["IsGUIDPresentInList function"]
tech.root: sensors
ms.keywords: IsGUIDPresentInList
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
 - IsGUIDPresentInList
 - sensorsutils/IsGUIDPresentInList
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - sensorsutils.h
api_name:
 - IsGUIDPresentInList
product:
 - Windows
---

# IsGUIDPresentInList function


## -description

This routine looks for a GUID in a list of GUIDs.

## -parameters

### -param guidArray

[in] GUID Array to search in.

### -param arrayLength

[in] Length of GUID Array to search in.

### -param guidElem

[in] GUID Element to search for.

## -returns

This function returns TRUE if the element is present in the list, FALSE otherwise.

## -remarks

## -see-also

