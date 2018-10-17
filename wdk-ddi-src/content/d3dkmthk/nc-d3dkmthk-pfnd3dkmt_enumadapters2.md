---
UID: NC:d3dkmthk.PFND3DKMT_ENUMADAPTERS2
title: PFND3DKMT_ENUMADAPTERS2
author: windows-driver-content
description: The PFND3DKMT_ENUMADAPTERS2 callback function enumerates all graphics adapters on the system.
ms.assetid: 06879518-8a38-4b70-ae9c-25fb4ed35c70
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
-	PFND3DKMT_ENUMADAPTERS2
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_ENUMADAPTERS2 callback function

## -description

The PFND3DKMT_ENUMADAPTERS2 callback function enumerates all graphics adapters on the system.

## -prototype

```
//Declaration

PFND3DKMT_ENUMADAPTERS2 Pfnd3dkmtEnumadapters2; 

// Definition

NTSTATUS Pfnd3dkmtEnumadapters2 
(
	const D3DKMT_ENUMADAPTERS2 *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_ENUMADAPTERS2](ns-d3dkmthk-_d3dkmt_enumadapters2.md) structure.

## -returns

Returns NTSTATUS.
