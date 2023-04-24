---
UID: NF:ntddk.PsCreateSiloContext
title: PsCreateSiloContext function (ntddk.h)
description: This routine creates an object that will be inserted in a Silo.
tech.root: kernel
ms.date: 04/20/2023
keywords: ["PsCreateSiloContext function"]
ms.keywords: PsCreateSiloContext, PsCreateSiloContext routine [Kernel-Mode Driver Architecture], kernel.pscreatesilocontext, ntddk/PsCreateSiloContext
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PsCreateSiloContext
 - ntddk/PsCreateSiloContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsCreateSiloContext
---

# PsCreateSiloContext function

## -description

This routine  creates an object that will be inserted in a *Silo*.

## -parameters

### -param Silo [in]

A pointer to a silo.  This parameter is required and it cannot be **NULL**.

### -param Size [in]

The size, in bytes, of the portion of the object defined by the caller.

### -param PoolType [in]

The type of pool to allocate from. This parameter is required and must be one of the following: **NonPagedPoolNx** or **PagedPool**.

### -param ContextCleanupCallback [in, optional]

A pointer to a [SILO_CONTEXT_CLEANUP_CALLBACK](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-silo_context_cleanup_callback) callback function. The function will be called when the returned object has zero references to it. This parameter is optional and can be **NULL**.

### -param ReturnedSiloContext

A pointer to a caller-allocated variable that receives the address of the newly created object.

## -returns

The following NT status codes are returned.

| Return code | Description |
|--|--|
| **STATUS_INSUFFICIENT_RESOURCES** | The routine encountered a pool allocation failure. This is an error code. |
| **STATUS_INVALID_PARAMETER** | The pool type is not valid. This is an error code. |
| **STATUS_SUCCESS** | The operation completed successfully. |
