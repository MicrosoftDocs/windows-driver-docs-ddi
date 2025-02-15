---
UID: NS:ntifs.STARTING_LCN_INPUT_BUFFER
tech.root: ifsk
title: STARTING_LCN_INPUT_BUFFER
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the STARTING_LCN_INPUT_BUFFER structure.
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
req.typenames: STARTING_LCN_INPUT_BUFFER, *PSTARTING_LCN_INPUT_BUFFER
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
 - STARTING_LCN_INPUT_BUFFER
 - PSTARTING_LCN_INPUT_BUFFER
f1_keywords:
 - STARTING_LCN_INPUT_BUFFER
 - ntifs/STARTING_LCN_INPUT_BUFFER
 - PSTARTING_LCN_INPUT_BUFFER
 - ntifs/PSTARTING_LCN_INPUT_BUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - STARTING_LCN_INPUT_BUFFER
---

## -description

The **STARTING_LCN_INPUT_BUFFER** structure contains the starting logical cluster number (LCN) for the [**FSCTL_GET_VOLUME_BITMAP**](ni-ntifs-fsctl_get_volume_bitmap.md).
 control code.

## -struct-fields

### -field StartingLcn

The LCN from which the operation should start when describing a bitmap. This member will be rounded down to a file-system-dependent rounding boundary, and that value will be returned. Its value should be an integral multiple of eight.

## -see-also

[**FSCTL_GET_VOLUME_BITMAP**](ni-ntifs-fsctl_get_volume_bitmap.md)
