---
UID: NE:d3dkmthk._D3DKMT_GPU_PREFERENCE_QUERY_STATE
title: D3DKMT_GPU_PREFERENCE_QUERY_STATE (d3dkmthk.h)
description: Learn more about the D3DKMT_GPU_PREFERENCE_QUERY_STATE enumeration.
ms.date: 04/10/2024
keywords: ["D3DKMT_GPU_PREFERENCE_QUERY_STATE enumeration"]
ms.keywords: _D3DKMT_GPU_PREFERENCE_QUERY_STATE, D3DKMT_GPU_PREFERENCE_QUERY_STATE,
req.header: d3dkmthk.h
req.construct-type: enumeration
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3DKMT_GPU_PREFERENCE_QUERY_STATE
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - _D3DKMT_GPU_PREFERENCE_QUERY_STATE
 - d3dkmthk/_D3DKMT_GPU_PREFERENCE_QUERY_STATE
 - D3DKMT_GPU_PREFERENCE_QUERY_STATE
 - d3dkmthk/D3DKMT_GPU_PREFERENCE_QUERY_STATE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_GPU_PREFERENCE_QUERY_STATE
 - D3DKMT_GPU_PREFERENCE_QUERY_STATE
dev_langs:
 - c++
---

# D3DKMT_GPU_PREFERENCE_QUERY_STATE enumeration (d3dkmthk.h)



## -description

A **D3DKMT_GPU_PREFERENCE_QUERY_STATE** value specifies the GPU preference for a query.

## -enum-fields

### -field D3DKMT_GPU_PREFERENCE_STATE_UNINITIALIZED

The GPU preference isn't initialized.

### -field D3DKMT_GPU_PREFERENCE_STATE_HIGH_PERFORMANCE

The highest performing GPU is preferred.

### -field D3DKMT_GPU_PREFERENCE_STATE_MINIMUM_POWER

The minimum-powered GPU is preferred.

### -field D3DKMT_GPU_PREFERENCE_STATE_UNSPECIFIED

A GPU preference isn't specified.

### -field D3DKMT_GPU_PREFERENCE_STATE_NOT_FOUND

The GPU preference isn't found.

### -field D3DKMT_GPU_PREFERENCE_USER_SPECIFIED_GPU

The GPU preference is specified by the user.

## -remarks

The user preference should be one of the following three options:

* D3DKMT_GPU_PREFERENCE_STATE_HIGH_PERFORMANCE
* D3DKMT_GPU_PREFERENCE_STATE_MINIMUM_POWER
* D3DKMT_GPU_PREFERENCE_STATE_UNSPECIFIED
