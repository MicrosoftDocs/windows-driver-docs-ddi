---
UID: NE:d3dkmthk._D3DKMT_GPU_PREFERENCE_QUERY_STATE
title: _D3DKMT_GPU_PREFERENCE_QUERY_STATE
author: windows-driver-content
description: Specifies the GPU preference query state.
ms.assetid: ff9a92ba-1cc6-4814-941d-33c829de7ca2
ms.date: 10/19/2018
ms.topic: enum
ms.keywords: _D3DKMT_GPU_PREFERENCE_QUERY_STATE, D3DKMT_GPU_PREFERENCE_QUERY_STATE, 
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3DKMT_GPU_PREFERENCE_QUERY_STATE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmthk.h
api_name: 
-	_D3DKMT_GPU_PREFERENCE_QUERY_STATE
product:
-	Windows
targetos: Windows
tech.root: display
---

# _D3DKMT_GPU_PREFERENCE_QUERY_STATE enumeration

## -description

Specifies the GPU preference query state.



## -enum-fields

### -field D3DKMT_GPU_PREFERENCE_STATE_UNINITIALIZED

Unitialized.

### -field D3DKMT_GPU_PREFERENCE_STATE_HIGH_PERFORMANCE

High performance.

### -field D3DKMT_GPU_PREFERENCE_STATE_MINIMUM_POWER

Minimum power.

### -field D3DKMT_GPU_PREFERENCE_STATE_UNSPECIFIED

Unspecified.

## -remarks

The user preference should be on of the following three options:

* D3DKMT_GPU_PREFERENCE_STATE_HIGH_PERFORMANCE
* D3DKMT_GPU_PREFERENCE_STATE_MINIMUM_POWER
* D3DKMT_GPU_PREFERENCE_STATE_UNSPECIFIED

## -see-also
