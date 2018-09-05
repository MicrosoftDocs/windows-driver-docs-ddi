---
UID: NC:d3dkmthk.PFND3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE
title: PFND3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE
author: windows-driver-content
description:
ms.assetid: d446a771-1b71-458a-9dbb-f36f8838ba19
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
-	PFND3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE callback function

## -description

Implemented by the client driver to query protected session info from NT handle.

## -prototype

```
//Declaration

PFND3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE Pfnd3dkmtQueryprotectedsessioninfofromnthandle;

// Definition

NTSTATUS Pfnd3dkmtQueryprotectedsessioninfofromnthandle
(
	D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE *
)
{...}

PFND3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE


```

## -parameters

### -param D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE *

Pointer to a [D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE](ns-d3dkmthk-_d3dkmt_queryprotectedsessioninfofromnthandle.md) structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE](ns-d3dkmthk-_d3dkmt_queryprotectedsessioninfofromnthandle.md) and then calling Pfnd3dkmtQueryProtectedSessionInfoFromNtHandle.

