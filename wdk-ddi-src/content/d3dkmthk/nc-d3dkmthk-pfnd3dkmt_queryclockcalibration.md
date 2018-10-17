---
UID: NC:d3dkmthk.PFND3DKMT_QUERYCLOCKCALIBRATION
title: PFND3DKMT_QUERYCLOCKCALIBRATION
author: windows-driver-content
description: The PFND3DKMT_QUERYCLOCKCALIBRATION callback function queries clock calibration.
ms.assetid: 1bbde800-aeee-4460-92e5-8097bf0349f9
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
-	PFND3DKMT_QUERYCLOCKCALIBRATION
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_QUERYCLOCKCALIBRATION callback function

## -description

The PFND3DKMT_QUERYCLOCKCALIBRATION callback function queries clock calibration. 

## -prototype

```
//Declaration

PFND3DKMT_QUERYCLOCKCALIBRATION Pfnd3dkmtQueryclockcalibration; 

// Definition

NTSTATUS Pfnd3dkmtQueryclockcalibration 
(
	D3DKMT_QUERYCLOCKCALIBRATION *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_QUERYCLOCKCALIBRATION](../d3dkmdt/ns-d3dkmdt-_d3dkmt_queryclockcalibration.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
