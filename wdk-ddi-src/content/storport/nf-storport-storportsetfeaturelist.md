---
UID: NF:storport.StorPortSetFeatureList
title: StorPortSetFeatureList function
description: StorPortSetFeatureList sets the Storport features that a miniport supports.
tech.root: storage
ms.date: 05/13/2021
ms.topic: function
ms.keywords: StorPortSetFeatureList
req.header: storport.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
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
f1_keywords:
 - StorPortSetFeatureList
 - storport/StorPortSetFeatureList
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortSetFeatureList
product:
 - Windows
---

# StorPortSetFeatureList function

## -description

**StorPortSetFeatureList** sets the *StorPort* features that a miniport supports.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport's device extension.

### -param FeatureCount

Number of features that *FeatureList* points to.

### -param FeatureList

Pointer to an array of [**STORPORT_FEATURE_TYPE**](ne-storport-storport_feature_type.md) enum values that identify the *StorPort* features supported by the miniport.

## -returns

**StorPortSetFeatureList** returns a status code such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The feature list was set successfully. |
| STOR_STATUS_INVALID_PARAMETER | An input parameter is invalid; for example, *FeatureList* is NULL or *FeatureCount* is out of range. |
| STOR_STATUS_UNSUCCESSFUL | The operation failed. |

## -remarks

A miniport calls **StorPortSetFeatureList** to set the *StorPort* features that it supports. A miniport should call this function for each adapter in the beginning of its [*HwFindAdapter*](./nc-storport-hw_initialize.md) routine.

## -see-also

[*HwFindAdapter*](./nc-storport-hw_initialize.md)

[**STORPORT_FEATURE_TYPE**](ne-storport-storport_feature_type.md)
