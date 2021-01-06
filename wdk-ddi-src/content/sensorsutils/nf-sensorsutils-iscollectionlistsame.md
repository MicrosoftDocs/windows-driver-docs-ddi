---
UID: NF:sensorsutils.IsCollectionListSame
title: IsCollectionListSame function (sensorsutils.h)
description: This routine compares two collection lists to see if they are the same.
ms.date: 08/08/2018
keywords: ["IsCollectionListSame function"]
tech.root: sensors
ms.keywords: IsCollectionListSame
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
 - IsCollectionListSame
 - sensorsutils/IsCollectionListSame
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - sensorsutils.h
api_name:
 - IsCollectionListSame
product:
 - Windows
---

# IsCollectionListSame function


## -description

This routine compares two collection lists and determines if they are the same.

## -parameters

### -param ListA

[in] Pointer to a collection list.

### -param ListB

[in] Pointer to a second collection list to compare against the first.

## -returns

This function returns TRUE if the two collection lists are the same, FALSE otherwise.

## -remarks

## -see-also

