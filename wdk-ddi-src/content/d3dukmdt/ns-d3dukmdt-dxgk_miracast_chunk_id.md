---
UID: NS:d3dukmdt.__unnamed_union_16
title: DXGK_MIRACAST_CHUNK_ID (d3dukmdt.h)
description: Stores info that identifies a wireless display (Miracast) encode chunk.
old-location: display\dxgk_miracast_chunk_id.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGK_MIRACAST_CHUNK_ID structure"]
ms.keywords: DXGK_MIRACAST_CHUNK_ID, DXGK_MIRACAST_CHUNK_ID union [Display Devices], d3dukmdt/DXGK_MIRACAST_CHUNK_ID, display.dxgk_miracast_chunk_id
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: DXGK_MIRACAST_CHUNK_ID
f1_keywords:
 - DXGK_MIRACAST_CHUNK_ID
 - d3dukmdt/DXGK_MIRACAST_CHUNK_ID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dukmdt.h
api_name:
 - DXGK_MIRACAST_CHUNK_ID
---

# DXGK_MIRACAST_CHUNK_ID structure


## -description

Stores info that identifies a wireless display (Miracast) encode chunk.

## -struct-fields

### -field FrameNumber

The number of the encoded Wi-Fi frame.

### -field PartNumber

The frame part number.

### -field Value

Holds a 64-bit value that identifies the encode chunk.

