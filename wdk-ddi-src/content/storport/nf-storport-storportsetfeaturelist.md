---
UID: NF:storport.StorPortSetFeatureList
title: StorPortSetFeatureList function
author: windows-driver-content
description: A miniport can call StorPortSetFeatureList to set the Storport feature list that it supports.
tech.root: storage
ms.assetid: 1426766a-5575-42ba-8a64-53d2e6c23be7
ms.author: windowsdriverdev
ms.date: 03/24/2020
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

A miniport can call **StorPortSetFeatureList** to set the *StorPort* feature list that it supports.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport's device extension.

### -param FeatureCount

Number of features in *FeatureList*.

### -param FeatureList

List of *StorPort* features supported by the miniport. This value is based on [**STORPORT_FEATURE_TYPE**](ne-storport-storport_feature_type.md) enum values.

## -returns

**StorPortSetFeatureList** returns a status code such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The feature list was set successfully. |
| STOR_STATUS_INVALID_PARAMETER | An input parameter is invalid. |
| STOR_STATUS_UNSUCCESSFUL | The operation failed. |

## -remarks

A miniport should call **StorPortSetFeatureList** for each adapter in the beginning of its [*HwFindAdapter*](./nc-storport-hw_initialize.md) routine.

## -see-also

[*HwFindAdapter*](./nc-storport-hw_initialize.md)

[**STORPORT_FEATURE_TYPE**](ne-storport-storport_feature_type.md)