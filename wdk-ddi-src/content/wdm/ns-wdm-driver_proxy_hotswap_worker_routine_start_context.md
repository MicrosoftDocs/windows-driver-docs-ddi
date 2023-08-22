---
UID: NS:wdm._DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
tech.root: kernel
title: DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
ms.date: 08/21/2023
targetos: Windows
description: This topic describes the DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT, *PDRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - PDRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
f1_keywords:
 - _DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - wdm/_DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - PDRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - wdm/PDRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - wdm/DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
dev_langs:
 - c++
helpviewer_keywords:
 - _DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
---

## -description

This topic describes the **DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT** structure.

## -struct-fields

### -field WorkerRoutine

Defines the **PDRIVER_PROXY_HOTSWAP_WORKER_ROUTINE** member **WorkerRoutine**.

### -field Context

Defines the **PVOID** member **Context**.

### -field WaitType

Defines the **WAIT_TYPE** member **WaitType**.

### -field WaitReason

Defines the **KWAIT_REASON** member **WaitReason**.

### -field WaitMode

Defines the **KPROCESSOR_MODE** member **WaitMode**.

### -field Altertable

Defines the **BOOLEAN** member **Altertable**.

### -field HasTimeout

Defines the **BOOLEAN** member **HasTimeout**.

### -field Timeout

Defines the **LARGE_INTEGER** member **Timeout**.

### -field EventCount

Defines the **ULONG** member **EventCount**.

### -field Events[ANYSIZE_ARRAY]

Defines the **PKEVENT** member **Events**.

## -remarks

## -see-also
