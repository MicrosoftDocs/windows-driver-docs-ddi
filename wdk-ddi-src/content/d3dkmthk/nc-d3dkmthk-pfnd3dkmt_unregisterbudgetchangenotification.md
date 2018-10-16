---
UID: NC:d3dkmthk.PFND3DKMT_UNREGISTERBUDGETCHANGENOTIFICATION
title: PFND3DKMT_UNREGISTERBUDGETCHANGENOTIFICATION
author: windows-driver-content
description: The PFND3DKMT_UNREGISTERBUDGETCHANGENOTIFICATION callback function unregisters budget change notification.
ms.assetid: 265eba32-7c02-4323-8e21-b22120960940
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3dkmthk.h
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
-	UserDefined
api_location: 
-	d3dkmthk.h
api_name: 
-	PFND3DKMT_UNREGISTERBUDGETCHANGENOTIFICATION
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_UNREGISTERBUDGETCHANGENOTIFICATION callback function

## -description

The PFND3DKMT_UNREGISTERBUDGETCHANGENOTIFICATION callback function unregisters budget change notification.

## -prototype

```cpp
//Declaration

PFND3DKMT_UNREGISTERBUDGETCHANGENOTIFICATION Pfnd3dkmtUnregisterbudgetchangenotification; 

// Definition

NTSTATUS Pfnd3dkmtUnregisterbudgetchangenotification 
(
	D3DKMT_UNREGISTERBUDGETCHANGENOTIFICATION *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_UNREGISTERBUDGETCHANGENOTIFICATION](ns-d3dkmthk-_d3dkmt_unregisterbudgetchangenotification.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
