---
UID: NF:ntddk.PsGetThreadExitStatus
tech.root: kernel
title: PsGetThreadExitStatus
ms.date: 02/12/2024
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.idl: 
req.include-header: 
req.irql: <= APC_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsGetThreadExitStatus
f1_keywords:
 - PsGetThreadExitStatus
 - ntddk/PsGetThreadExitStatus
dev_langs:
 - c++
helpviewer_keywords:
 - PsGetThreadExitStatus
---

## -description

This routine returns the exit status for a given thread.

## -parameters

### -param Thread [in]

A pointer to an executive thread object structure (ETHREAD).

## -returns

If the thread is being or has been deleted, this routine returns the exit status of the thread. This can be any valid NTSTATUS code depending on how the thread was terminated, including STATUS_SUCCESS if the call is successful or an appropriate error status code if the thread was terminated due to an error.

If the thread is still active and not being deleted, this routine returns STATUS_PENDING.

## -remarks

## -see-also

