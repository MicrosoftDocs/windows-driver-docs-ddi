---
UID: NS:d3dkmddi._DXGK_CREATEALLOCATIONFLAGS
title: DXGK_CREATEALLOCATIONFLAGS (d3dkmddi.h)
description: Learn more about the DXGK_CREATEALLOCATIONFLAGS structure.
ms.date: 11/08/2024
keywords: ["DXGK_CREATEALLOCATIONFLAGS structure"]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: DXGK_CREATEALLOCATIONFLAGS
f1_keywords:
 - _DXGK_CREATEALLOCATIONFLAGS
 - d3dkmddi/_DXGK_CREATEALLOCATIONFLAGS
 - DXGK_CREATEALLOCATIONFLAGS
 - d3dkmddi/DXGK_CREATEALLOCATIONFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_CREATEALLOCATIONFLAGS
 - DXGK_CREATEALLOCATIONFLAGS
---

# DXGK_CREATEALLOCATIONFLAGS structure

## -description

The **DXGK_CREATEALLOCATIONFLAGS** structure identifies how to create allocations.

## -struct-fields

### -field Resource

A UINT value that specifies whether allocations belong to a resource.

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

An alternative way to access the structure.

## -see-also

[**DXGKARG_CREATEALLOCATION**](ns-d3dkmddi-_dxgkarg_createallocation.md)
