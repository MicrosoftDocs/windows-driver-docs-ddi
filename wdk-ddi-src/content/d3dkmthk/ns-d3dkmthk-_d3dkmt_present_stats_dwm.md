---
UID: NS:d3dkmthk._D3DKMT_PRESENT_STATS_DWM
title: _D3DKMT_PRESENT_STATS_DWM
author: windows-driver-content
description: The present status of the desktop windows manager (DWM).
ms.assetid: 8bd41296-e5b2-440b-a871-a644af659790
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DKMT_PRESENT_STATS_DWM, D3DKMT_PRESENT_STATS_DWM, 
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_PRESENT_STATS_DWM
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmthk.h
api_name: 
-	_D3DKMT_PRESENT_STATS_DWM
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# _D3DKMT_PRESENT_STATS_DWM structure

## -description

The present status of the desktop windows manager (DWM).

## -struct-fields

### -field PresentCount

The number of present operations that can be queued for the device that is specified by *hDevice*.

### -field PresentRefreshCount

The present refresh count.

### -field PresentQPCTime

The present QPC (query performance counter) time.

### -field SyncRefreshCount

The sync refresh count.

### -field SyncQPCTime

The sync QPC time.

### -field CustomPresentDuration
 
The custom present duration.

## -remarks

## -see-also
