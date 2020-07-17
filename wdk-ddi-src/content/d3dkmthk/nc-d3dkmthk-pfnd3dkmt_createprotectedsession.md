---
UID: NC:d3dkmthk.PFND3DKMT_CREATEPROTECTEDSESSION
title: PFND3DKMT_CREATEPROTECTEDSESSION (d3dkmthk.h)
description: Implemented by the client driver to create a protected session.
ms.assetid: 000fb6fc-0d6e-4c2a-ac7c-05759d7e0d28
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CREATEPROTECTEDSESSION callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_CREATEPROTECTEDSESSION"
 - "PFND3DKMT_CREATEPROTECTEDSESSION"
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
- PFND3DKMT_CREATEPROTECTEDSESSION
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_CREATEPROTECTEDSESSION callback function

## -description

Implemented by the client driver to create a protected session.

## -prototype

```cpp
//Declaration

PFND3DKMT_CREATEPROTECTEDSESSION Pfnd3dkmtCreateprotectedsession;

// Definition

NTSTATUS Pfnd3dkmtCreateprotectedsession
(
	D3DKMT_CREATEPROTECTEDSESSION *
)
{...}

PFND3DKMT_CREATEPROTECTEDSESSION


```

## -parameters

### -param D3DKMT_CREATEPROTECTEDSESSION *

Pointer to a [D3DKMT_CREATEPROTECTEDSESSION](ns-d3dkmthk-_d3dkmt_createprotectedsession.md) structure that contains the information needed to create a protected session.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_CREATEPROTECTEDSESSION](ns-d3dkmthk-_d3dkmt_createprotectedsession.md) and then calling Pfnd3DkmtCreateProtectedSession.

