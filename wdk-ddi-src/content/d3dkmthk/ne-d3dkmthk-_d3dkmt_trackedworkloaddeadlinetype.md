---
UID: NE:d3dkmthk._D3DKMT_TRACKEDWORKLOADDEADLINETYPE
title: _D3DKMT_TRACKEDWORKLOADDEADLINETYPE (d3dkmthk.h)
description: Specifies the tracked workload deadline type.
ms.assetid: 7bf49b7e-0658-46c2-bc35-e5dcddb4f507
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/_D3DKMT_TRACKEDWORKLOADDEADLINETYPE"
ms.keywords: _D3DKMT_TRACKEDWORKLOADDEADLINETYPE, D3DKMT_TRACKEDWORKLOADDEADLINETYPE, 
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3DKMT_TRACKEDWORKLOADDEADLINETYPE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_TRACKEDWORKLOADDEADLINETYPE
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# _D3DKMT_TRACKEDWORKLOADDEADLINETYPE enumeration

## -description

Specifies the tracked workload deadline type.

## -enum-fields

### -field D3DKMT_TRACKEDWORKLOADDEADLINETYPE_ABSOLUTE

The deadline is absolute, given in QPC (query performance counter).

### -field D3DKMT_TRACKEDWORKLOADDEADLINETYPE_VBLANK 

The deadline is given as an offset to the next VBLANK (vertical blanking interval), in hundreds of nanoseconds. 

Note that there’s currently no way to skip a VBLANK.

## -remarks

## -see-also
