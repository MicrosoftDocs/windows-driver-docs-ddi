---
UID: NC:d3dkmthk.PFND3DKMT_CREATEOUTPUTDUPL
title: PFND3DKMT_CREATEOUTPUTDUPL (d3dkmthk.h)
description: Reserved for system use. Do not use in your driver.
ms.assetid: 62080c15-3c27-48cd-a497-83afea9f95a3
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CREATEOUTPUTDUPL callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_CREATEOUTPUTDUPL"
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
- PFND3DKMT_CREATEOUTPUTDUPL
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_CREATEOUTPUTDUPL callback function

## -description

Reserved for system use. Do not use in your driver.

## -prototype

```cpp
//Declaration

PFND3DKMT_CREATEOUTPUTDUPL Pfnd3dkmtCreateoutputdupl; 

// Definition

NTSTATUS Pfnd3dkmtCreateoutputdupl 
(
	const D3DKMT_CREATE_OUTPUTDUPL *
)
{...}

```

## -parameters

### -param *

Pointer to a D3DKMT_CREATE_OUTPUTDUPL structure.

## -returns

Returns NTSTATUS.
