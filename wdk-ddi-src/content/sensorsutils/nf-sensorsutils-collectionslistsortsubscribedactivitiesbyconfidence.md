---
UID: NF:sensorsutils.CollectionsListSortSubscribedActivitiesByConfidence
title: CollectionsListSortSubscribedActivitiesByConfidence function (sensorsutils.h)
description: This routine rearranges activity data collection under certain conditions.
ms.assetid: 10616185-a9af-4b35-a7b7-d3288c319121
ms.date: 08/08/2018
ms.topic: function
tech.root: sensors
ms.keywords: CollectionsListSortSubscribedActivitiesByConfidence
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
- CollectionsListSortSubscribedActivitiesByConfidence
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# CollectionsListSortSubscribedActivitiesByConfidence function


## -description

This routine rearranges activity data collection for following:

1. Remove state that is not subscribed
2. Sort state based on confidence from high to low
3. If there are multiple states with the same confidence, use state precedence order. The routine returns and error if one of the following conditions apply:

    * There is invalid state, or
    * There is confidence that is 0 or greater than 100, or
    * There are multiple entries of the same state

> [!Caution] 
> This routine assumes that there is no embedded pointer in the collection list.


## -parameters

### -param thresholds

[in] A pointer to a sensor collection list that contains the activity detection thresholds.

### -param pCollection

[in] A pointer to a sensor collection list.

## -returns

Returns STATUS_INVALID_PARAMETER if one of the following conditions apply:

* *pCollection* is null.
* The AllocatedSizeInBytes member of Collection is less than the acceptable minimum size (in bytes).
* *pCollection* contains less than 3 elements (1 timestamp and one pair of state and confidence) for a sensor collection list.

Returns STATUS_SUCCESS when the collection list was properly sorted.

## -remarks

## -see-also
