---
UID: NF:d3dkmthk.D3DKMTGetTrackedWorkloadStatistics
title: D3DKMTGetTrackedWorkloadStatistics function (d3dkmthk.h)
description: Retrieves the rolling statistics for the tracked workload.
ms.assetid: a29b19fb-1a03-42a1-9523-059f91939ecd
ms.date: 10/19/2018
keywords: ["D3DKMTGetTrackedWorkloadStatistics function"]
f1_keywords:
 - "d3dkmthk/D3DKMTGetTrackedWorkloadStatistics"
ms.keywords: D3DKMTGetTrackedWorkloadStatistics
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: DXGKDDI_INTERFACE_VERSION_WDDM2_5
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
- DllExport
api_location: 
- Gdi32.dll
api_name: 
- D3DKMTGetTrackedWorkloadStatistics
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3DKMTGetTrackedWorkloadStatistics function


## -description

Retrieves the rolling statistics for the tracked workload.

Note that this function returns only stats for work that is currently completed.

## -parameters

### -param Arg1

[in/out] Pointer to a [D3DKMT_GETTRACKEDWORKLOADSTATISTICS](ns-d3dkmthk-_d3dkmt_gettrackedworkloadstatistics.md) structure to get the tracked workload statistics.

## -returns


This function returns NTSTATUS.


## -remarks

## -see-also
