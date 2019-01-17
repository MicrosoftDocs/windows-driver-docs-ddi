---
UID: NF:sensorsutils.CollectionsListCopyAndMarshall
title: CollectionsListCopyAndMarshall function
description: This routine copies and marshalls a collection list from source to target.
ms.assetid: 63abf500-d6c8-428c-b359-2041ee49091c
ms.date: 08/07/2018
ms.topic: function
tech.root: sensors
ms.keywords: CollectionsListCopyAndMarshall
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
-	apiref
api_type: 
-	LibDef
api_location: 
-	sensorsutils.h
api_name: 
-	CollectionsListCopyAndMarshall
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# CollectionsListCopyAndMarshall function


## -description

This routine copies and marshalls a collection list from source to target.

## -parameters

### -param Target

[in] A pointer to a collection list.

### -param Source

[out] A pointer to a collection list.

## -returns

This function returns NTSTATUS.

## -remarks

> [!WARNING]
> This method assumes the structure sizes stay the same during marshalling. Avoid using this method if passing the data between processes that can have different bit-ness values (e.g. 32 bit <-> 64 bit). Use [CollectionsListSerializeToBuffer](nf-sensorsutils-collectionslistserializetobuffer.md) instead.

## -see-also
