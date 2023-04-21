---
UID: NF:ntddk.IoSetActivityIdIrp
title: IoSetActivityIdIrp function (ntddk.h)
description: The IoSetActivityIdIrp routine associates an activity ID with an IRP.
tech.root: kernel
ms.date: 04/20/2023
keywords: ["IoSetActivityIdIrp function"]
ms.keywords: IoSetActivityIdIrp, IoSetActivityIdIrp routine [Kernel-Mode Driver Architecture], kernel.iosetactivityidirp, ntddk/IoSetActivityIdIrp
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
req.irql: Any level if a GUID is passed in, otherwise PASSIVE_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - IoSetActivityIdIrp
 - ntddk/IoSetActivityIdIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoSetActivityIdIrp
---

## -description

The IoSetActivityIdIrp routine associates an activity ID with an IRP.

## -parameters

### -param Irp [in]

The IRP to associate the activity ID with.

### -param Guid [in, optional]

A pointer to the GUID that represents the ID to store in the IRP.  If NULL, IoSetActivityIdIrp attempts to retrieve the activity ID from the current thread if it was the thread that originally issued the request.

## -returns

IoSetActivityIdIrp returns STATUS_SUCCESS if the call is successful. Possible error return values include the following.

| Return code | Description |
|--|--|
| **STATUS_NOT_SUPPORTED** | No GUID was provided and the ETW activity ID was unavailable. |
| **STATUS_UNSUCCESSFUL** | The I/O tracing provider has not been enabled on the IRP. |

## -remarks

Drivers should use IoSetActivityIdIrp only on IRPs that have been allocated using [IoAllocateIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp) (and freed using [IoFreeIrp](/windows-hardware/drivers/devtest/storport-iofreeirp)). Otherwise, memory leakage may result.
