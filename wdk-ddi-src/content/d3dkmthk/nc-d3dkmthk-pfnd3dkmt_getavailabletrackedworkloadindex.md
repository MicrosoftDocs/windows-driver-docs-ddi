---
UID: NC:d3dkmthk.PFND3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX
title: PFND3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX
author: windows-driver-content
description: Gets the available tracked workload index.
ms.assetid: aa4a954a-abac-4adb-859e-e7f7c46c58cf
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
-	PFND3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX
product:
-	Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX callback function

## -description

Gets the available tracked workload index.

## -prototype

```
//Declaration

PFND3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX Pfnd3dkmtGetavailabletrackedworkloadindex; 

// Definition

NTSTATUS Pfnd3dkmtGetavailabletrackedworkloadindex 
(
	D3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_GETAVAILABLETRACKEDWORKLOADINDEX](ns-d3dkmthk-_d3dkmt_getavailabletrackedworkloadindex.md) structure to get the available tracked workload index.

## -returns

Returns NTSTATUS that.

## -remarks



## -see-also
