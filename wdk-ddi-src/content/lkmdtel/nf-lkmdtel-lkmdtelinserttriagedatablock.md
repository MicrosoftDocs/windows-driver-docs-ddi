---
UID: NF:lkmdtel.LkmdTelInsertTriageDataBlock
tech.root: kernel
title: LkmdTelInsertTriageDataBlock
ms.date: 12/11/2024
targetos: Windows
description: The LkmdTelInsertTriageDataBlock function adds a region of kernel memory to the kernel minidump.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: lkmdtel.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: lkmdtel.lib, \werkernelapi.lib 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
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
 - lkmdtel.h
api_name:
 - LkmdTelInsertTriageDataBlock
f1_keywords:
 - LkmdTelInsertTriageDataBlock
 - lkmdtel/LkmdTelInsertTriageDataBlock
dev_langs:
 - c++
helpviewer_keywords:
 - LkmdTelInsertTriageDataBlock
---

## -description

This function adds a region of kernel memory to the kernel minidump.  

## -parameters

### -param TelemetryHandle

Supplies a Telemetry Report handle created by [LkmdTelCreateReport](./nf-lkmdtel-lkmdtelcreatereport.md). 

### -param TriageData

Supplies the location of the triage data to be added.

### -param TriageDataSize

Supplies the number of bytes of triage data to add. 

## -returns

STATUS_SUCCESS if successful. 
 
STATUS_INVALID_PARAMETER if there is not already at least one triage data block present or an existing triage data block does not start on an 8 byte boundary. 
 
STATUS_BUFFER_TOO_SMALL if there is insufficient space in the triage dump buffer to contain the new triage block. 


## -remarks

- The buffers passed to this function must remain valid until the function returns.  The function will copy the memory to new buffers. 
- The maximum amount of memory that can be added via calls to `LkmdTelInsertTriageDataBlock` is dependent on the OS architecture. On a 64-bit OS, the maximum is approximately 180 KB. On a 32-bit OS, it is approximately 90 KB.


## -see-also

[LkmdTelCreateReport](./nf-lkmdtel-lkmdtelcreatereport.md)

