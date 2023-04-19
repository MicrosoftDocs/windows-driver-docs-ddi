---
UID: NS:ntifs._SHUFFLE_FILE_DATA
tech.root: ifsk
title: SHUFFLE_FILE_DATA
ms.date: 04/17/2023
targetos: Windows
description: Lear more about the SHUFFLE_FILE_DATA structure.
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
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.target-type: 
req.typenames: SHUFFLE_FILE_DATA, *PSHUFFLE_FILE_DATA
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _SHUFFLE_FILE_DATA
 - PSHUFFLE_FILE_DATA
 - SHUFFLE_FILE_DATA
f1_keywords:
 - _SHUFFLE_FILE_DATA
 - ntifs/_SHUFFLE_FILE_DATA
 - PSHUFFLE_FILE_DATA
 - ntifs/PSHUFFLE_FILE_DATA
 - SHUFFLE_FILE_DATA
 - ntifs/SHUFFLE_FILE_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - _SHUFFLE_FILE_DATA
---

## -description

**SHUFFLE_FILE_DATA** is the input structure for the [**FSCTL_SHUFFLE_FILE**](ni-ntifs-fsctl_shuffle_file.md) control code.

## -struct-fields

### -field StartingOffset

Cluster-aligned byte offset of the base of the contiguous region to shuffle into the file.

### -field Length

Cluster-aligned length in bytes of the data to be shuffled into the file.

### -field Flags

Bitwise OR of flags for the shuffle operation. **Flags** be the following value.

| Value | Meaning |
| ----- | ------- |
| SHUFFLE_FILE_FLAG_SKIP_INITIALIZING_NEW_CLUSTERS (0x001) | Don't zero-initialize any new clusters created as a result of the shuffle. |

## -see-also

[**FSCTL_SHUFFLE_FILE**](ni-ntifs-fsctl_shuffle_file.md)
