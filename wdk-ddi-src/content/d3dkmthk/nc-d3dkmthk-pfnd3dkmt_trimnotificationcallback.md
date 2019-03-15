---
UID: NC:d3dkmthk.PFND3DKMT_TRIMNOTIFICATIONCALLBACK
title: PFND3DKMT_TRIMNOTIFICATIONCALLBACK (d3dkmthk.h)
description: Trim notification.
ms.assetid: cc23539a-b74d-40d5-b03a-6d1f0b70b71c
ms.date: 10/19/2018
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3dkmthk.h
api_name: 
- PFND3DKMT_TRIMNOTIFICATIONCALLBACK
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_TRIMNOTIFICATIONCALLBACK callback function

## -description

Trim notification.

## -prototype

```cpp
//Declaration

PFND3DKMT_TRIMNOTIFICATIONCALLBACK Pfnd3dkmtTrimnotificationcallback; 

// Definition

VOID Pfnd3dkmtTrimnotificationcallback 
(
	D3DKMT_TRIMNOTIFICATION *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_TRIMNOTIFICATION](ns-d3dkmthk-_d3dkmt_trimnotification.md) structure.

## -returns

Returns VOID that ...

## -remarks




## -see-also
