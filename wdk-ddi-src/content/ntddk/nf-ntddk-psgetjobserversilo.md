---
UID: NF:ntddk.PsGetJobServerSilo
title: PsGetJobServerSilo function (ntddk.h)
description: This routine returns the effective ServerSilo for the job. The returned pointer is valid as long as the supplied Job object remains referenced.
tech.root: kernel
ms.date: 12/07/2022
keywords: ["PsGetJobServerSilo function"]
ms.keywords: PsGetJobServerSilo, PsGetJobServerSilo routine [Kernel-Mode Driver Architecture], kernel.psgetjobserversilo, ntddk/PsGetJobServerSilo
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
 - PsGetJobServerSilo
 - ntddk/PsGetJobServerSilo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsGetJobServerSilo
---

## -description

This routine returns the effective *ServerSilo* for the job. The returned pointer is valid as long as the supplied *Job* object remains referenced.

This returns a *ServerSilo* or a value indicating the host silo. Unlike [PsGetJobSilo](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetjobsilo), it will not return an app silo, even if one is present.

## -parameters

### -param Job [in, optional]

A job object.

### -param ServerSilo [out]

 A pointer that receives the server silo for the job.

## -returns

The following NT status codes are returned.

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER** | The *Job* parameter is **NULL**. |
| **STATUS_SUCCESS** | A PESILO is returned successfully. |

## -remarks

**STATUS_SUCCESS** is returned even if a server silo is not in effect for the job. In that case, it will return the default host silo.
