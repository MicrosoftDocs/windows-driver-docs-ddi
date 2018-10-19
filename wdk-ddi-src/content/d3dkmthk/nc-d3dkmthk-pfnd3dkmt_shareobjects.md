---
UID: NC:d3dkmthk.PFND3DKMT_SHAREOBJECTS
title: PFND3DKMT_SHAREOBJECTS
author: windows-driver-content
description: The PFND3DKMT_SHAREOBJECTS callback function shares resource objects that were created with the D3DKMTCreateAllocation, D3DKMTCreateKeyedMutex2, and D3DKMTCreateSynchronizationObject2 functions.
ms.assetid: 735eae78-aded-49b2-9c8e-7404ce15a143
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
-	PFND3DKMT_SHAREOBJECTS
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_SHAREOBJECTS callback function

## -description

The PFND3DKMT_SHAREOBJECTS callback function shares resource objects that were created with the D3DKMTCreateAllocation, D3DKMTCreateKeyedMutex2, and D3DKMTCreateSynchronizationObject2 functions.

## -prototype

```cpp
//Declaration

PFND3DKMT_SHAREOBJECTS Pfnd3dkmtShareobjects; 

// Definition

NTSTATUS Pfnd3dkmtShareobjects 
(
	UINT cObjects
	 const D3DKMT_HANDLE *hObjects
	POBJECT_ATTRIBUTES pObjectAttributes
	DWORD dwDesiredAccess
	HANDLE *phSharedNtHandle
)
{...}

```

## -parameters

### -param cObjects: 
### -param *hObjects: 
### -param pObjectAttributes: 
### -param dwDesiredAccess: 
### -param *phSharedNtHandle: 



## -returns

Returns NTSTATUS.


## -remarks




## -see-also
