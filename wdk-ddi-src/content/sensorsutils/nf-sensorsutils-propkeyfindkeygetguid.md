---
UID: NF:sensorsutils.PropKeyFindKeyGetGuid
title: PropKeyFindKeyGetGuid function (sensorsutils.h)
description: This routine gets a GUID value from a PROPVARIANT within a collection list based on the PROPERTYKEY.
ms.assetid: 56740950-e6d3-4f3a-83ab-546fda013b81
ms.date: 08/08/2018
keywords: ["PropKeyFindKeyGetGuid function"]
tech.root: sensors
f1_keywords:
 - "sensorsutils/PropKeyFindKeyGetGuid"
ms.keywords: PropKeyFindKeyGetGuid
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
- PropKeyFindKeyGetGuid
product:
  - Windows
targetos: Windows


ms.custom: RS5
---

# PropKeyFindKeyGetGuid function


## -description

This routine gets a GUID value from a PROPVARIANT within a collection list based on the PROPERTYKEY.


## -parameters

### -param pList

[in] Pointer to the list of PROPVARIANT collection.

### -param pKey

[in] Pointer to a PROPERTYKEY for the target PROPVARIANT.

### -param pRetValue

[out] Pointer to the output buffer.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also
