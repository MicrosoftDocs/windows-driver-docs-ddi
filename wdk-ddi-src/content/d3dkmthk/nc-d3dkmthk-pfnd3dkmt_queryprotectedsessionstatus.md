---
UID: NC:d3dkmthk.PFND3DKMT_QUERYPROTECTEDSESSIONSTATUS
title: PFND3DKMT_QUERYPROTECTEDSESSIONSTATUS
author: windows-driver-content
description:
ms.assetid: 2b5d646e-45c8-4f15-91e5-70c9bc25ea6b
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
topictype:
-	apiref
apitype:
-	UserDefined
apilocation:
-	d3dkmthk.h
apiname:
-	PFND3DKMT_QUERYPROTECTEDSESSIONSTATUS
product: 
- Windows
targetos: Windows
---

# PFND3DKMT_QUERYPROTECTEDSESSIONSTATUS callback function

## -description

Implemented by the client driver to query a protected session.

## -prototype

```
//Declaration

PFND3DKMT_QUERYPROTECTEDSESSIONSTATUS Pfnd3dkmtQueryprotectedsessionstatus;

// Definition

NTSTATUS Pfnd3dkmtQueryprotectedsessionstatus
(
	D3DKMT_QUERYPROTECTEDSESSIONSTATUS *
)
{...}

PFND3DKMT_QUERYPROTECTEDSESSIONSTATUS


```

## -parameters

### -param D3DKMT_QUERYPROTECTEDSESSIONSTATUS *

Pointer to a [D3DKMT_QUERYPROTECTEDSESSIONSTATUS](ns-d3dkmthk-_d3dkmt_queryprotectedsessionstatus.md) structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_QUERYPROTECTEDSESSIONSTATUS](ns-d3dkmthk-_d3dkmt_queryprotectedsessionstatus.md) and then calling Pfnd3dkmtQueryProtectedSessionStatus.

