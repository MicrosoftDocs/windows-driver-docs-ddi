---
UID: NS:ntifs.STARTING_LCN_INPUT_BUFFER_EX
tech.root: ifsk
title: STARTING_LCN_INPUT_BUFFER_EX
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the STARTING_LCN_INPUT_BUFFER_EX structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.typenames: STARTING_LCN_INPUT_BUFFER_EX, *PSTARTING_LCN_INPUT_BUFFER_EX
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - STARTING_LCN_INPUT_BUFFER_EX
 - PSTARTING_LCN_INPUT_BUFFER_EX
f1_keywords:
 - STARTING_LCN_INPUT_BUFFER_EX
 - ntifs/STARTING_LCN_INPUT_BUFFER_EX
 - PSTARTING_LCN_INPUT_BUFFER_EX
 - ntifs/PSTARTING_LCN_INPUT_BUFFER_EX
dev_langs:
 - c++
helpviewer_keywords:
 - STARTING_LCN_INPUT_BUFFER_EX
---

## -description

The **STARTING_LCN_INPUT_BUFFER_EX** structure contains the starting logical cluster number (LCN) for the [**FSCTL_GET_VOLUME_BITMAP**](ni-ntifs-fsctl_get_volume_bitmap.md) control code.

## -struct-fields

### -field StartingLcn

The LCN from which the operation should start when describing a bitmap. This member will be rounded down to a file-system-dependent rounding boundary, and that value will be returned. Its value should be an integral multiple of eight.

### -field Flags

Set of flags that modify the behavior of the bitmap retrieval operation. The following flag is defined.

| Flag | Description |
|------|-------------|
| GET_VOLUME_BITMAP_FLAG_MASK_METADATA (0x00000001) | When set, indicates that the operation should include metadata in the volume bitmap. |

## -see-also

[**FSCTL_GET_VOLUME_BITMAP**](ni-ntifs-fsctl_get_volume_bitmap.md)
