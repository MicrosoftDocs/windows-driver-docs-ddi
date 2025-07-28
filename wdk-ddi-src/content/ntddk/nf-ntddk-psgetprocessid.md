---
UID: NF:ntddk.PsGetProcessId
title: PsGetProcessId function (ntddk.h)
description: The PsGetProcessId routine returns the process identifier (process ID) that is associated with a specified process.
tech.root: kernel
ms.date: 07/28/2025
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - PsGetProcessId
 - ntddk/PsGetProcessId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsGetProcessId
---

# PsGetProcessId function

## -description

The **PsGetProcessId** routine returns the process identifier (process ID) that is associated with a specified process.

## -parameters

### -param Process [in]

A pointer to a process object structure.

## -returns

**PsGetProcessId** returns the process ID of the process that the **Process** parameter specifies.

## -remarks

The EPROCESS-typed process object structure is an opaque data structure that the operating system uses internally. To obtain a pointer to the EPROCESS structure for the current process, a driver can call [**PsGetCurrentProcess**](../wdm/nf-wdm-iogetcurrentprocess.md). To obtain a pointer to the EPROCESS structure for a different process, the driver can call [**ObReferenceObjectByHandle**](../wdm/nf-wdm-obreferenceobjectbyhandle.md).

## -see-also

[**ObReferenceObjectByHandle**](../wdm/nf-wdm-obreferenceobjectbyhandle.md)

[**PsGetCurrentProcess**](../wdm/nf-wdm-iogetcurrentprocess.md)
