---
UID: NF:ntddk.PsGetJobSilo
title: PsGetJobSilo function (ntddk.h)
description: This routine returns the first job in the hierarchy that is a Silo. The returned pointer is valid as long as the supplied Job object remains referenced.
tech.root: kernel
ms.date: 12/07/2022
keywords: ["PsGetJobSilo function"]
ms.keywords: PsGetJobSilo, PsGetJobSilo routine [Kernel-Mode Driver Architecture], kernel.psgetjobsilo, ntddk/PsGetJobSilo
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
 - PsGetJobSilo
 - ntddk/PsGetJobSilo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsGetJobSilo
---

## -description

This routine returns the first job in the hierarchy that is a *Silo*.  The returned pointer is valid as long as the supplied *Job* object remains referenced.

This returns both app silos and server silos, whichever is first.

## -parameters

### -param Job [in]

A job object.

### -param Silo [out]

 A pointer that receives the silo for the job.

## -returns

The following NT status codes are returned:

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER** | The *Job* parameter is **NULL**. |
| **STATUS_JOB_NO_CONTAINER** | No silo is present. |
| **STATUS_SUCCESS** | A PESILO is returned successfully. |
