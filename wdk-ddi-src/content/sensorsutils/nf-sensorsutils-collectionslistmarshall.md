---
UID: NF:sensorsutils.CollectionsListMarshall
title: CollectionsListMarshall function (sensorsutils.h)
description: This routine is similar to CollectionsListCopyAndMarshall, except that it marshalls a collection list in-place.
ms.date: 08/08/2018
keywords: ["CollectionsListMarshall function"]
tech.root: sensors
ms.keywords: CollectionsListMarshall
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
 - CollectionsListMarshall
 - sensorsutils/CollectionsListMarshall
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - sensorsutils.h
api_name:
 - CollectionsListMarshall
---

# CollectionsListMarshall function


## -description

This routine is similar to [CollectionsListCopyAndMarshall](nf-sensorsutils-collectionslistcopyandmarshall.md), except that it marshalls a collection list in-place.

## -parameters

### -param Target [in]

Pointer to a collection list.

## -returns

If the Source Collection list is not large enough to accommodate the marshalled/flattened list, this function fails with STATUS_BUFFER_TOO_SMALL. Returns STATUS_SUCCESS otherwise.

## -remarks

## -see-also

