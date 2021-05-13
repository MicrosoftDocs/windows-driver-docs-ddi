---
UID: NS:dxva._DXVA_Tile_AV1
tech.root: display
title: DXVA_Tile_AV1
ms.date: 05/13/2021
targetos: Windows
description: The DXVA_Tile_AV1 structure is sent by the host software decoder to the accelerator to convey tile data locations.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dxva.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: DXVA_Tile_AV1, *LPDXVA_Tile_AV1
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - _DXVA_Tile_AV1
 - LPDXVA_Tile_AV1
 - DXVA_Tile_AV1
f1_keywords:
 - _DXVA_Tile_AV1
 - dxva/_DXVA_Tile_AV1
 - LPDXVA_Tile_AV1
 - dxva/LPDXVA_Tile_AV1
 - DXVA_Tile_AV1
 - dxva/DXVA_Tile_AV1
dev_langs:
 - c++
---

## -description

The **DXVA_Tile_AV1** structure is sent by the host software decoder to the accelerator to convey tile data locations.

## -struct-fields

### -field DataOffset

Locates the compressed bitstream data for the current tile. Specifically, **DataOffset** is the byte offset from the start of the bitstream buffer of either tile_list_obu, codec_tile_data or tile_group_obu, init_symbol(tileSize) from the AV1 specification.

### -field DataSize

Number of bytes in the bitstream data buffer that are associated with this tile or list of tiles starting at the byte given by **DataOffset**.

### -field row

The row that this tile belongs to. When part of a Tile List Open Bitstream Unit (OBU), this specifies the anchor_tile_row from the AV1 specification.

### -field column

The column that this tile belongs to. When part of a Tile List OBU, this specifies the anchor_tile_column from the AV1 specification.

### -field Reserved16Bits

Reserved; set to 0. The accelerator ignores this field.

### -field anchor_frame

Specifies an associated anchor_frame for the tile list OBU. This is to be translated to the the source frame buffer/surface index for the reference tile picture, from the anchor_frame_idx value in the specification. If this tile is not part of a Tile List OBU then this frame will have the standard invalid frame index of 255.

### -field Reserved8Bits

Reserved; set to 0. The accelerator ignores this field.

## -remarks

See the [Direct X Video Acceleration Specification for AV1 Video Coding](https://www.microsoft.com/download/details.aspx?id=101577) for detailed information, including how to use this structure.
