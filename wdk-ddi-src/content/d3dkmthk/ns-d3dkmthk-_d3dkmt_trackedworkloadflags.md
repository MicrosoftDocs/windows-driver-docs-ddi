---
UID: NS:d3dkmthk._D3DKMT_TRACKEDWORKLOADFLAGS
title: _D3DKMT_TRACKEDWORKLOADFLAGS
description: A workload may be periodic, have similar load, or both.
ms.assetid: 31f01df5-7df0-4671-9bb9-92b68b3c501c
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DKMT_TRACKEDWORKLOADFLAGS, D3DKMT_TRACKEDWORKLOADFLAGS, 
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_TRACKEDWORKLOADFLAGS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmthk.h
api_name: 
-	_D3DKMT_TRACKEDWORKLOADFLAGS
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# _D3DKMT_TRACKEDWORKLOADFLAGS structure

## -description

A workload may be periodic, have similar load, or both. These flags will be used to derive heuristics for how we are going to adjust the hints we sent to the driver.

## -struct-fields

### -field Periodic

The tracked workload occurs at a periodic rate. 

### -field SimilarLoad

The tracked workload loads instances are similar in load, that is, a similar amount of work will be submitted every time. For instance, decoding video P-frames could be considered similar.

### -field Reserved

Reserved for internal use.

### -field Value
 
The value used to operate over the other members.

## -remarks

## -see-also
