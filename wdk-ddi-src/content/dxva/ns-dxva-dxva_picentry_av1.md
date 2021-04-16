---
UID: NS:dxva._DXVA_PicEntry_AV1
tech.root: display
title: DXVA_PicEntry_AV1
ms.date: 05/13/2021
targetos: Windows
description: The DXVA_PicEntry_AV1 structure specifies a reference to an uncompressed surface, with the additional metadata necessary for referencing that surface.
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
req.typenames: DXVA_PicEntry_AV1, *LPDXVA_PicEntry_AV1
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - _DXVA_PicEntry_AV1
 - LPDXVA_PicEntry_AV1
 - DXVA_PicEntry_AV1
f1_keywords:
 - _DXVA_PicEntry_AV1
 - dxva/_DXVA_PicEntry_AV1
 - LPDXVA_PicEntry_AV1
 - dxva/LPDXVA_PicEntry_AV1
 - DXVA_PicEntry_AV1
 - dxva/DXVA_PicEntry_AV1
dev_langs:
 - c++
---

## -description

The **DXVA_PicEntry_AV1** structure specifies a reference to an uncompressed surface, with the additional metadata necessary for referencing that surface.

## -struct-fields

### -field width

Specifies the coded width of the referred frame. This field corresponds to the frame_width_minus_1 syntax element. See Remarks.

### -field height

Specifies the coded height of the referred frame. This field corresponds to the frame_height_minus_1 syntax element. See Remarks.

### -field wmmat

The affine transformation matrix that applies globally to motion vectors referring to this frame.  

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.wminvalid

Specifies whether the given global motion parameters are valid. If 0 then the parameters should be assumed to be invalid and not read.

### -field DUMMYUNIONNAME.wmtype

Specifies the global motion type of this referred frame. This value matches the reference software’s TransformationType enum:

``` cpp
typedef enum {
  IDENTITY = 0,
  TRANSLATION = 1,
  ROTZOOM = 2,
  AFFINE = 3,
  TRANS_TYPES,
} TransformationType;
```

This attribute is informational, to help validate the contents of **wmmat**.

### -field DUMMYUNIONNAME.Reserved

Reserved; do not use.

### -field DUMMYUNIONNAME.GlobalMotionFlags

Global motion parameters.

### -field Index

Identifies the index into **ref_frame_map_texture_index[]** to identify the frame used as a reference for this picture. When **Index** does not contain an index to a valid reference, the value shall be set to 255, to indicate that the index is invalid.

### -field Reserved16Bits

Reserved; do not use.

## -remarks

If **width** and **height** are derived for the frame (for example via the frame_size_override_flag), the host decoder will derive the appropriate values and store the result in these fields. Each AV1 frame may be coded at a different resolution than the previous frame(s).

See the [Direct X Video Acceleration Specification for AV1 Video Coding](https://www.microsoft.com/download/details.aspx?id=101577) for detailed information, including how to use this structure.
