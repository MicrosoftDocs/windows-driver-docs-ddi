---
UID: NF:ntddk.PsGetProcessExitStatus
tech.root: kernel
title: PsGetProcessExitStatus
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
req.irql: APC_LEVEL
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
 - PsGetProcessExitStatus
f1_keywords:
 - PsGetProcessExitStatus
 - ntddk/PsGetProcessExitStatus
dev_langs:
 - c++
helpviewer_keywords:
 - PsGetProcessExitStatus
---

## -description

This routine retrieves the exit status of a process.

## -parameters

### -param Process [in]

A pointer to the EPROCESS structure that represents the process. Drivers can use the [**PsGetCurrentProcess**](../wdm/nf-wdm-iogetcurrentprocess.md) and [**ObReferenceObjectByHandle**](../wdm/nf-wdm-obreferenceobjectbyhandle.md) routines to obtain a pointer to the EPROCESS structure for a process.

## -returns

Returns the exit status of the supplied EPROCESS.

## -remarks

A driver might call PsGetProcessExitStatus in the following scenarios: monitoring process termination to obtain information about whether a process terminated normally or due to an error, resource cleanup to determine when and how to clean up resources allocated on behalf of a process, and error reporting and logging to provide more detailed information about process terminations.

## -see-also

