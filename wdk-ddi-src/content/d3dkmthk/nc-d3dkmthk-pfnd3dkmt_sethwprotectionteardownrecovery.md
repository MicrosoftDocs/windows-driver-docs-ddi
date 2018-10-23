---
UID: NC:d3dkmthk.PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY
title: PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY
author: windows-driver-content
description: The PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY callback function sets the hardware protection tear down recovery.
ms.assetid: 7beb2a30-1171-4ad3-8ae3-8358e55921a0
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
-	PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY callback function

## -description

The PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY callback function sets the hardware protection tear down recovery.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY Pfnd3dkmtSethwprotectionteardownrecovery; 

// Definition

NTSTATUS Pfnd3dkmtSethwprotectionteardownrecovery 
(
	D3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY](ns-d3dkmthk-_d3dkmt_sethwprotectionteardownrecovery.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
