---
UID: NS:d3dkmthk._D3DKMT_HYBRID_LIST
title: _D3DKMT_HYBRID_LIST (d3dkmthk.h)
description: Describes the Direct 3D kernel mode hybrid list.
ms.date: 10/19/2018
keywords: ["D3DKMT_HYBRID_LIST structure"]
ms.keywords: _D3DKMT_HYBRID_LIST, D3DKMT_HYBRID_LIST,
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
req.typenames: D3DKMT_HYBRID_LIST
targetos: Windows
ms.custom: RS5, 19H1
tech.root: display
f1_keywords:
 - _D3DKMT_HYBRID_LIST
 - d3dkmthk/_D3DKMT_HYBRID_LIST
 - D3DKMT_HYBRID_LIST
 - d3dkmthk/D3DKMT_HYBRID_LIST
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_HYBRID_LIST
dev_langs:
 - c++
---

# _D3DKMT_HYBRID_LIST structure


## -description

Describes the Direct 3D kernel mode hybrid list.

## -struct-fields

### -field State

The GPU preference query state.

### -field AdapterLuid

[in,opt] Adapter LUID to per-adapter DList state. Optional, if *bUserPreferenceQuery* is true. 

For more info about DList, see *Setting up the dList DLL* in [Hybrid system DDI](/windows-hardware/drivers/display/hybrid-system-ddi).

### -field bUserPreferenceQuery

 
Indicates whether the structure is referring to user GPU preference, or per-adapter DList query.

### -field QueryType

## -remarks

## -see-also
