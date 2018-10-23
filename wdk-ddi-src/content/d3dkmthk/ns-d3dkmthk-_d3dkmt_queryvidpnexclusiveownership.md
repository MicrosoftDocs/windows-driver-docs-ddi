---
UID: NS:d3dkmthk._D3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP
title: _D3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP
author: windows-driver-content
description: Used to query for VidPn exclusive ownership.
ms.assetid: cefe498a-79be-46c7-8cf8-4517d15a85bf
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP, D3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP, 
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
req.typenames: D3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmthk.h
api_name: 
-	_D3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP
product:
-	Windows
targetos: Windows
---

# _D3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP structure

## -description

Used to query for VidPn exclusive ownership.

## -struct-fields

### -field hProcess

[in] A handle to the process.

### -field hWindow

[in] A handle to the window.

### -field VidPnSourceId

[out] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field AdapterLuid

[out] The adapter LUID (locally unique identifier).

### -field OwnerType
 
[out] The owner type.

## -remarks

## -see-also
