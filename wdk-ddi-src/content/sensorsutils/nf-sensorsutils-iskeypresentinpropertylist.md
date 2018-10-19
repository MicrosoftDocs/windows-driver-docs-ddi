---
UID: NF:sensorsutils.IsKeyPresentInPropertyList
title: IsKeyPresentInPropertyList function
author: windows-driver-content
description: This routine determine if a key is present in a property list.
ms.assetid: 4a565915-3f6d-45ff-8912-0a4e80910a8b
ms.date: 08/08/2018
tech.root: sensors
ms.topic: function
ms.keywords: IsKeyPresentInPropertyList
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
-	IsKeyPresentInPropertyList
product:
 - Windows
targetos: Windows


---

# IsKeyPresentInPropertyList function


## -description

This routine determine if a key is present in a property list.


## -parameters

### -param pList

[in] Pointer to the list of PROPERTYKEYs

### -param pKey

[in] Pointer to a PROPERTYKEY.

## -returns

This function returns TRUE if the key is present, FALSE otherwise.

## -remarks

## -see-also
