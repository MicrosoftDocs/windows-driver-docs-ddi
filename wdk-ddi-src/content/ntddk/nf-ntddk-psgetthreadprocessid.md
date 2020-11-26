---
UID: NF:ntddk.PsGetThreadProcessId
title: PsGetThreadProcessId function (ntddk.h)
description: The PsGetThreadProcessId routine returns the process identifier that is associated with a specified thread's process.
ms.assetid: 4986e5ad-796e-4649-8ca6-118b191f4fd7
ms.date: 06/25/2018
tech.root: kernel
keywords: ["PsGetThreadProcessId function"]
ms.keywords: PsGetThreadProcessId
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - PsGetThreadProcessId
 - ntddk/PsGetThreadProcessId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsGetThreadProcessId
---

# PsGetThreadProcessId function


## -description

The **PsGetThreadProcessId** routine returns the process identifier (process ID) that is associated with a specified thread's process.

## -parameters

### -param Thread

A pointer to an executive thread object structure.

## -returns

The supplied thread's process's process ID.

## -remarks

## -see-also

[**PsGetProcessId**](nf-ntddk-psgetprocessid.md)

