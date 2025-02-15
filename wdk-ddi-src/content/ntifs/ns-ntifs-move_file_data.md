---
UID: NS:ntifs.MOVE_FILE_DATA
tech.root: ifsk
title: MOVE_FILE_DATA
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the MOVE_FILE_DATA structure.
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
req.typenames: MOVE_FILE_DATA, *PMOVE_FILE_DATA
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
 - MOVE_FILE_DATA
 - PMOVE_FILE_DATA
f1_keywords:
 - MOVE_FILE_DATA
 - ntifs/MOVE_FILE_DATA
 - PMOVE_FILE_DATA
 - ntifs/PMOVE_FILE_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - MOVE_FILE_DATA
---

## -description

The **MOVE_FILE_DATA** structure contains input data for the [**FSCTL_MOVE_FILE**](ni-ntifs-fsctl_move_file.md) control code.

## -struct-fields

### -field FileHandle

Handle to the file to be moved.

### -field StartingVcn

A VCN (cluster number relative to the beginning of a file) of the first cluster to be moved.

### -field StartingLcn

An LCN (cluster number on a volume) to which the VCN is to be moved.

### -field ClusterCount

The count of clusters to be moved.

## -see-also

[**FSCTL_MOVE_FILE**](ni-ntifs-fsctl_move_file.md)
