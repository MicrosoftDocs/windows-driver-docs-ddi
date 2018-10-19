---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYPROTECTEDSESSION
title: PFND3DKMT_DESTROYPROTECTEDSESSION
author: windows-driver-content
description: Implemented by the client driver to destroy a protected session.
ms.assetid: a5e0bcd2-aa9e-450a-9f72-038c90dafc36
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
-	apiref
api_type:
-	UserDefined
api_location:
-	d3dkmthk.h
api_name:
-	PFND3DKMT_DESTROYPROTECTEDSESSION
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_DESTROYPROTECTEDSESSION callback function

## -description

Implemented by the client driver to destroy a protected session.

## -prototype

```cpp
//Declaration

PFND3DKMT_DESTROYPROTECTEDSESSION Pfnd3dkmtDestroyprotectedsession;

// Definition

NTSTATUS Pfnd3dkmtDestroyprotectedsession
(
	D3DKMT_DESTROYPROTECTEDSESSION *
)
{...}

PFND3DKMT_DESTROYPROTECTEDSESSION


```

## -parameters

### -param D3DKMT_DESTROYPROTECTEDSESSION *

Pointer to a [D3DKMT_DESTROYPROTECTEDSESSION](ns-d3dkmthk-_d3dkmt_destroyprotectedsession.md) structure that contains the information needed to destroy a protected session.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_DESTROYPROTECTEDSESSION](ns-d3dkmthk-_d3dkmt_destroyprotectedsession.md) and then calling <!-- REPLACE ME -->.

