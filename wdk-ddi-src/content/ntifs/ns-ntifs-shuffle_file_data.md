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

Cluster-aligned byte offset of the base of the contiguous region from which to add or remove data in the file passed with the FS control code.

### -field Length

Cluster-aligned length in bytes of the data to be added or removed. **Length** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| Greater than 0 | Add the allocation to the file. |
| Less than 0    | Remove the allocation from the file. |
| 0              | Do nothing. |

### -field Flags

Bitwise OR of flags for the shuffle operation. **Flags** be the following value.

| Value | Meaning |
| ----- | ------- |
| SHUFFLE_FILE_FLAG_SKIP_INITIALIZING_NEW_CLUSTERS (0x001) | Valid only when adding allocation. When set, free clusters are allocated and added but have arbitrary initial contents (they are not zero-initialized). |

## -see-also

[**FSCTL_SHUFFLE_FILE**](ni-ntifs-fsctl_shuffle_file.md)
