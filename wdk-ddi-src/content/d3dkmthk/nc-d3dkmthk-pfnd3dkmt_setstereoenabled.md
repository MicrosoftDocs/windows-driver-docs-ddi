---
UID: NC:d3dkmthk.PFND3DKMT_SETSTEREOENABLED
title: PFND3DKMT_SETSTEREOENABLED
author: windows-driver-content
description: The PFND3DKMT_SETSTEREOENABLED callback function sets stereo enabled.
ms.assetid: ee87c614-07b4-47a3-a6f5-afb2fdae9772
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
-	PFND3DKMT_SETSTEREOENABLED
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_SETSTEREOENABLED callback function

## -description

The PFND3DKMT_SETSTEREOENABLED callback function sets stereo enabled.

## -prototype

```
//Declaration

PFND3DKMT_SETSTEREOENABLED Pfnd3dkmtSetstereoenabled; 

// Definition

NTSTATUS Pfnd3dkmtSetstereoenabled 
(
	BOOL Arg1
)
{...}

```

## -parameters

### -param Arg1: 



## -returns

Returns NTSTATUS.


## -remarks




## -see-also