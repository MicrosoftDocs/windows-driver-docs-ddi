---
UID: NS:d3dumddi._D3DDDICB_QUERYADAPTERINFO2
title: _D3DDDICB_QUERYADAPTERINFO2
author: windows-driver-content
description: Contains information that describes the graphics adapter.
ms.assetid: ee97cc0b-2486-4fae-9950-af4422d9acb0
ms.date:
ms.topic: struct
ms.keywords: _D3DDDICB_QUERYADAPTERINFO2, D3DDDICB_QUERYADAPTERINFO2,
req.header: d3dumddi.h
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
req.typenames: D3DDDICB_QUERYADAPTERINFO2
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	_D3DDDICB_QUERYADAPTERINFO2
product: 
- Windows
targetos: Windows
tech.root: display
---

# _D3DDDICB_QUERYADAPTERINFO2 structure

## -description

Contains information that describes the graphics adapter.

## -struct-fields

### -field QueryType

The type of query.

### -field pPrivateDriverData

[out] A pointer to a buffer that the display miniport driver can fill with information about the graphics adapter.

### -field PrivateDriverDataSize

[in/out] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.

