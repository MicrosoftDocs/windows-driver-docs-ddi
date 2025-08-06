---
UID: NF:wdm.PsQuerySystemAvailableCpus
tech.root: kernel
title: PsQuerySystemAvailableCpus
ms.date: 08/05/2025
targetos: Windows
description: The PsQuerySystemAvailableCpus function queries the set of CPUs that are available to the system process.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL to DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
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
 - wdm.h
api_name:
 - PsQuerySystemAvailableCpus
f1_keywords:
 - PsQuerySystemAvailableCpus
 - wdm/PsQuerySystemAvailableCpus
dev_langs:
 - c++
helpviewer_keywords:
 - PsQuerySystemAvailableCpus
---

## -description

The **PsQuerySystemAvailableCpus** function queries the set of CPUs that are available to the system process.

## -parameters

### -param Affinity [in, out]

Pointer to an extended affinity object (PKAFFINITY_EX) that will receive the set of available CPUs for the system process.

### -param ObservedSequenceNumber [in, optional]

Optional pointer to the most recent sequence number observed by the caller through a previous call to this routine. If this sequence number matches the current sequence number, the routine returns STATUS_NO_WORK_DONE and does not write to the affinity buffer.

### -param SequenceNumber [out]

Pointer to a buffer which will receive the current sequence number for the available CPUs to the system process.

## -returns

**PsQuerySystemAvailableCpus** returns one of the following NTSTATUS values:

| Return code | Description |
|-------------|-------------|
| **STATUS_SUCCESS** | The query was completed successfully. |
| **STATUS_INVALID_PARAMETER** | Any of the required buffers is NULL. |
| **STATUS_NO_WORK_DONE** | The given sequence number matches the current sequence number and no query was performed. |
| **STATUS_BUFFER_TOO_SMALL** | The given affinity buffer is too small. |

## -remarks

This routine can be called at IRQL from PASSIVE_LEVEL to DISPATCH_LEVEL.

The affinity buffer must be large enough to accommodate the active processor group count. Use [**KeQueryActiveGroupCount**](nf-wdm-kequeryactivegroupcount.md) to determine the required size.

The sequence number allows callers to optimize repeated queries by checking if the CPU availability has changed since the last call.

This function queries CPU availability for the system process, which typically represents all available CPUs in the system.

## -see-also

[**PsQuerySystemAvailableCpusCount**](nf-wdm-psquerysystemavailablecpuscount.md)

[**PsQueryProcessAvailableCpus**](nf-wdm-psqueryprocessavailablecpus.md)

[**KeQueryActiveGroupCount**](nf-wdm-kequeryactivegroupcount.md)
