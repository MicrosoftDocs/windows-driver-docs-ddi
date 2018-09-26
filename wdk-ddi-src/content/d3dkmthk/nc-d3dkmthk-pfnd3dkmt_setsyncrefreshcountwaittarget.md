---
UID: NC:d3dkmthk.PFND3DKMT_SETSYNCREFRESHCOUNTWAITTARGET
title: PFND3DKMT_SETSYNCREFRESHCOUNTWAITTARGET
author: windows-driver-content
description: The PFND3DKMT_SETSYNCREFRESHCOUNTWAITTARGET callback function sets sync refresh count for wait target.
ms.assetid: 012ee806-e75f-49c3-aedf-395298324cbc
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
-	PFND3DKMT_SETSYNCREFRESHCOUNTWAITTARGET
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_SETSYNCREFRESHCOUNTWAITTARGET callback function

## -description

The PFND3DKMT_SETSYNCREFRESHCOUNTWAITTARGET callback function sets sync refresh count for wait target.

## -prototype

```
//Declaration

PFND3DKMT_SETSYNCREFRESHCOUNTWAITTARGET Pfnd3dkmtSetsyncrefreshcountwaittarget; 

// Definition

NTSTATUS Pfnd3dkmtSetsyncrefreshcountwaittarget 
(
	const D3DKMT_SETSYNCREFRESHCOUNTWAITTARGET *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_SETSYNCREFRESHCOUNTWAITTARGET](ns-d3dkmthk-_d3dkmt_setsyncrefreshcountwaittarget.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also