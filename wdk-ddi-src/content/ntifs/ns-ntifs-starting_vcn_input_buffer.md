---
UID: NS:ntifs.STARTING_VCN_INPUT_BUFFER
tech.root: ifsk
title: STARTING_VCN_INPUT_BUFFER
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the STARTING_VCN_INPUT_BUFFER structure.
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
req.typenames: STARTING_VCN_INPUT_BUFFER, *PSTARTING_VCN_INPUT_BUFFER
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
 - STARTING_VCN_INPUT_BUFFER
 - PSTARTING_VCN_INPUT_BUFFER
f1_keywords:
 - STARTING_VCN_INPUT_BUFFER
 - ntifs/STARTING_VCN_INPUT_BUFFER
 - PSTARTING_VCN_INPUT_BUFFER
 - ntifs/PSTARTING_VCN_INPUT_BUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - STARTING_VCN_INPUT_BUFFER
---

## -description

The **STARTING_VCN_INPUT_BUFFER** structure contains the starting virtual cluster number (VCN) for the [**FSCTL_GET_RETRIEVAL_POINTERS**](ni-ntifs-fsctl_get_retrieval_pointers.md) control code.

## -struct-fields

### -field StartingVcn

The VCN at which the operation will begin enumerating extents in the file. This value may be rounded down to the first VCN of the extent in which the specified extent is found.

## -see-also

[**FSCTL_GET_RETRIEVAL_POINTERS**](ni-ntifs-fsctl_get_retrieval_pointers.md)
