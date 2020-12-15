---
UID: NC:d3dkmthk.PFND3DKMT_CREATEOUTPUTDUPL
title: PFND3DKMT_CREATEOUTPUTDUPL (d3dkmthk.h)
description: Reserved for system use. Do not use in your driver.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CREATEOUTPUTDUPL callback function"]
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
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3DKMT_CREATEOUTPUTDUPL
 - d3dkmthk/PFND3DKMT_CREATEOUTPUTDUPL
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_CREATEOUTPUTDUPL
dev_langs:
 - c++
---

# PFND3DKMT_CREATEOUTPUTDUPL callback function


## -description

Reserved for system use. Do not use in your driver.

## -parameters

### -param Arg1

Pointer to a D3DKMT_CREATE_OUTPUTDUPL structure.

## -returns

Returns NTSTATUS.

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

