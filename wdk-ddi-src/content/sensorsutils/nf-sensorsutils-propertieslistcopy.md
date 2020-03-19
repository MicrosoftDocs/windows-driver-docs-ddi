---
UID: NF:sensorsutils.PropertiesListCopy
title: PropertiesListCopy function (sensorsutils.h)
description: This routine copies a properties list from source to target.
ms.assetid: 75d16f0b-ded0-49fe-b2a3-ee751f05391c
ms.date: 08/08/2018
keywords: ["PropertiesListCopy function"]
tech.root: sensors
f1_keywords:
 - "sensorsutils/PropertiesListCopy"
ms.keywords: PropertiesListCopy
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
- PropertiesListCopy
product:
  - Windows
targetos: Windows


ms.custom: RS5
---

# PropertiesListCopy function


## -description

This routine copies a properties list from source to target.


## -parameters

### -param Target

[in] Pointer to a collection list to copy to.

### -param Source

[in] Pointer to a collection list to copy.

## -returns

This function returns:

* STATUS_INVALID_PARAMETER if the Target or Source is nullptr.
* STATUS_BUFFER_TOO_SMALL if the Target collection list is not large enough to contain the content of the Source collection list.
* STATUS_SUCCESS if the copy was successful.

## -remarks

## -see-also
