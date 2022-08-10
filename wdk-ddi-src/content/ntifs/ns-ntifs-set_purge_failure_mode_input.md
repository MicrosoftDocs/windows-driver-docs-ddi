---
UID: NS:ntifs._SET_PURGE_FAILURE_MODE_INPUT
tech.root: ifsk
title: SET_PURGE_FAILURE_MODE_INPUT
ms.date: 08/10/2022
targetos: Windows
description: Learn more about the SET_PURGE_FAILURE_MODE_INPUT structure.
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
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: SET_PURGE_FAILURE_MODE_INPUT, *PSET_PURGE_FAILURE_MODE_INPUT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _SET_PURGE_FAILURE_MODE_INPUT
 - PSET_PURGE_FAILURE_MODE_INPUT
 - SET_PURGE_FAILURE_MODE_INPUT
f1_keywords:
 - _SET_PURGE_FAILURE_MODE_INPUT
 - ntifs/_SET_PURGE_FAILURE_MODE_INPUT
 - PSET_PURGE_FAILURE_MODE_INPUT
 - ntifs/PSET_PURGE_FAILURE_MODE_INPUT
 - SET_PURGE_FAILURE_MODE_INPUT
 - ntifs/SET_PURGE_FAILURE_MODE_INPUT
dev_langs:
 - c++
helpviewer_keywords:
 - _SET_PURGE_FAILURE_MODE_INPUT
---

## -description

A **SET_PURGE_FAILURE_MODE_INPUT** structure is the input parameter for an [**FSCTL_SET_PURGE_FAILURE_MODE**](ni-ntifs-fsctl_set_purge_failure_mode.md) operation.

## -struct-fields

### -field Flags

Flags for the operation. Can be one of the following values:

| Value | Meaning |
| ----- | ------- |
| SET_PURGE_FAILURE_MODE_ENABLED  | Enables purge failure mode  |
| SET_PURGE_FAILURE_MODE_DISABLED | Disables purge failure mode |

## -see-also

[**FSCTL_SET_PURGE_FAILURE_MODE**](ni-ntifs-fsctl_set_purge_failure_mode.md)
