---
UID: NE:storport._STORPORT_FEATURE_TYPE
title: STORPORT_FEATURE_TYPE
author: windows-driver-content
description: The STORPORT_FEATURE_TYPE enum identifies the features supported by a miniport.
tech.root: storage
ms.assetid: 2df639b5-27bc-430d-8208-d0613e46b6a5
ms.author: windowsdriverdev
ms.date: 12/15/2019
ms.topic: enum
ms.keywords: STORPORT_FEATURE_TYPE, STORPORT_FEATURE_TYPE, 
req.header: storport.h
f1_keywords:
 - "storport/STORPORT_FEATURE_TYPE"
req.include-header:
req.target-type:
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: STORPORT_FEATURE_TYPE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - storport.h
api_name: 
 - STORPORT_FEATURE_TYPE
product: 
 - Windows
targetos: Windows
---

# STORPORT_FEATURE_TYPE enumeration

## -description

The STORPORT_FEATURE_TYPE enum identifies the features supported by a miniport.

## -enum-fields

### -field StorportFeatureBusTypeUnitControl

Whether the ScsiUnitQueryBusType control type query is supported. <!-- this is an enum, but StorPortSetFeatureList takes a PBOOLEAN - how can more than one feature be identified at a time, and how is interpretation between enum and BOOLEAN done, eg: this enum's value is 0, which is FALSE? -->

### -field StorportFeatureMax

## -remarks

A miniport provides STORPORT_FEATURE_TYPE in a call to [**StorPortSetFeatureList**](nf-storport-storportsetfeaturelist.md).

## -see-also

[**StorPortSetFeatureList**](nf-storport-storportsetfeaturelist.md)
