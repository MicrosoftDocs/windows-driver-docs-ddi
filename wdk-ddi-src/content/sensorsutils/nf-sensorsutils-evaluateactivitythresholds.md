---
UID: NF:sensorsutils.EvaluateActivityThresholds
title: EvaluateActivityThresholds function (sensorsutils.h)
description: This routine determines whether the new incoming activity data meets the threshold.
ms.assetid: f2a211f5-90ab-4665-856a-cd9b007c8efa
ms.date: 08/08/2018
keywords: ["EvaluateActivityThresholds function"]
tech.root: sensors
f1_keywords:
 - "sensorsutils/EvaluateActivityThresholds"
 - "EvaluateActivityThresholds"
ms.keywords: EvaluateActivityThresholds
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
- EvaluateActivityThresholds
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# EvaluateActivityThresholds function


## -description

This routine determines whether the new incoming activity data meets the threshold.

Note that the samples must be sorted and filtered data. Use CollectionsListSortSubscribedActivitiesByConfidence function to sort and filter data.


## -parameters

### -param newSample

[in] Incoming activity data, as a sensor collection list.

### -param oldSample

[in] Last reported activity data, as a sensor collection list.

### -param thresholds

[in] Activity detection thresholds, as a sensor collection list.

## -returns

This function returns TRUE if succeeded, FALSE otherwise.

## -remarks

## -see-also
