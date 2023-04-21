---
UID: NF:ntddk.ExUuidCreate
title: ExUuidCreate function (ntddk.h)
description: The ExUuidCreate routine initializes a UUID (GUID) structure to a newly generated value.
tech.root: kernel
ms.date: 04/20/2023
keywords: ["ExUuidCreate function"]
ms.keywords: ExUuidCreate, ExUuidCreate routine [Kernel-Mode Driver Architecture], k102_e7d2044b-4f90-41bd-bac4-819c721e80c8.xml, kernel.exuuidcreate, ntddk/ExUuidCreate
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExPassive, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExUuidCreate
 - ntddk/ExUuidCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExUuidCreate
---

# ExUuidCreate function

## -description

The **ExUuidCreate** routine initializes a UUID (GUID) structure to a newly generated value.

## -parameters

### -param Uuid [out]

A pointer to a caller-allocated UUID (GUID) structure that is set to a new UUID value.

## -returns

Possible return values include the following status codes.

| return code | description |
|--|--|
| **status_success** | the routine successfully generated a uuid that is universally unique. |
| **rpc_nt_uuid_local_only** | the routine generated a uuid that is unique only to this computer. this can occur when the mac address is not an ieee universally-administered address or when no nics are present. |
| **status_retry** | the system is not ready to generate a new uuid. |

## -remarks

A UUID and a GUID are the same data type.

The caller can iteratively attempt to obtain a new UUID value.
