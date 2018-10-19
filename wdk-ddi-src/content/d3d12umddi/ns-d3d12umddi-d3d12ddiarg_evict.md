---
UID: NS:d3d12umddi.D3D12DDIARG_EVICT
title: D3D12DDIARG_EVICT
author: windows-driver-content
description: Arguments used in the PFND3D12DDI_EVICT2 callback function to instruct the OS to decrement the residency reference count.
ms.assetid: 5cd700e6-bd18-4899-ba83-892f87d1ea18
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDIARG_EVICT, D3D12DDIARG_EVICT, 
req.header: d3d12umddi.h
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
req.typenames: D3D12DDIARG_EVICT
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDIARG_EVICT
product:
- Windows
targetos: Windows
---

# D3D12DDIARG_EVICT structure

## -description

Arguments used in the [PFND3D12DDI_EVICT2](nc-d3d12umddi-pfnd3d12ddi_evict2.md) callback function to instruct the OS to decrement the residency reference count. 

## -struct-fields

### -field NumObjects

The number of objects to evict.

### -field pObjects

Pointer to an array of objects.

### -field Flags
 
Flags.

## -remarks

## -see-also
