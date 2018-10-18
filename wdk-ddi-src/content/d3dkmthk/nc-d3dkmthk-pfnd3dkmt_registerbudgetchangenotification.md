---
UID: NC:d3dkmthk.PFND3DKMT_REGISTERBUDGETCHANGENOTIFICATION
title: PFND3DKMT_REGISTERBUDGETCHANGENOTIFICATION
author: windows-driver-content
description: The PFND3DKMT_REGISTERBUDGETCHANGENOTIFICATION callback function receives notifications from a graphics framework (such as OpenGL).
ms.assetid: 687701f6-6188-4b9c-8011-51f2d9d1ebf5
ms.date: 
ms.topic: callback
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
-	PFND3DKMT_REGISTERBUDGETCHANGENOTIFICATION
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_REGISTERBUDGETCHANGENOTIFICATION callback function

## -description

The PFND3DKMT_REGISTERBUDGETCHANGENOTIFICATION callback function receives notifications from a graphics framework (such as OpenGL).

## -prototype

```cpp
//Declaration

PFND3DKMT_REGISTERBUDGETCHANGENOTIFICATION Pfnd3dkmtRegisterbudgetchangenotification; 

// Definition

NTSTATUS Pfnd3dkmtRegisterbudgetchangenotification 
(
	D3DKMT_REGISTERBUDGETCHANGENOTIFICATION *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_REGISTERBUDGETCHANGENOTIFICATION](ns-d3dkmthk-_d3dkmt_registerbudgetchangenotification.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
