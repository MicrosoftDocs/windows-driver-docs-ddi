---
UID: NF:sensorsutils.PropKeyFindKeyGetGuid
title: PropKeyFindKeyGetGuid function
author: windows-driver-content
description: This routine gets a GUID value from a PROPVARIANT within a collection list based on the PROPERTYKEY.
ms.assetid: 56740950-e6d3-4f3a-83ab-546fda013b81
ms.author: windowsdriverdev
ms.date: 08/08/18
ms.prod: windows-hardware
ms.technology: windows-devices
tech.root: sensors
ms.topic: function
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
-	apiref
api_type: 
-	LibDef
api_location: 
-	sensorsutils.h
api_name: 
-	PropKeyFindKeyGetGuid
product:
  - Windows
targetos: Windows


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