---
UID: NS:prminterface._PRM_INTERFACE
tech.root: kernel
title: PRM_INTERFACE
ms.date: 02/05/2024
targetos: Windows
description: "Provides a set of pointers to functions that control the operation of a PRM interface."
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: prminterface.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: PRM_INTERFACE, *PPRM_INTERFACE
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - prminterface.h
api_name:
 - _PRM_INTERFACE
 - PPRM_INTERFACE
 - PRM_INTERFACE
f1_keywords:
 - _PRM_INTERFACE
 - prminterface/_PRM_INTERFACE
 - PPRM_INTERFACE
 - prminterface/PPRM_INTERFACE
 - PRM_INTERFACE
 - prminterface/PRM_INTERFACE
dev_langs:
 - c++
helpviewer_keywords:
 - _PRM_INTERFACE
---

# PRM_INTERFACE structure (prminterface.h)

## -description

The PRM_INTERFACE structure provides a set of pointers to functions that control the operation of a PRM interface.

## -struct-fields

### -field Version

Specifies the version of this structure.

### -field UnlockModule

A pointer to a system-defined routine to unlock a PRM module. For more information, see [PRM_UNLOCK_MODULE](./nc-prminterface-prm_unlock_module.md).

### -field LockModule

A pointer to a system-defined routine to lock a PRM module. For more information, see [PRM_LOCK_MODULE](./nc-prminterface-prm_lock_module.md).

### -field InvokeHandler

A pointer to a system-defined routine to invoke a specific PRM handler. For more information, see [PRM_INVOKE_HANDLER](./nc-prminterface-prm_invoke_handler.md).

### -field QueryHandler

A pointer to a system-defined routine to query for the presence of a specific PRM handler. For more information, see [PRM_QUERY_HANDLER](./nc-prminterface-prm_query_handler.md).

## -remarks

All members of this structure, with the exception of Version, are pointers to functions that drivers use to perform PRM operations. Drivers obtain these pointers by calling the [**ExGetPrmInterface**](./nf-prminterface-exgetprminterface.md) routine.

## -see-also

[Windows Kernel-Mode PRM Library](/windows-hardware/drivers/kernel/windows-kernel-mode-prm-library)