---
UID: NF:wdm.PsQueryProcessAvailableCpusCount
tech.root: kernel
title: PsQueryProcessAvailableCpusCount
ms.date: 08/05/2025
targetos: Windows
description: The PsQueryProcessAvailableCpusCount function queries the count of CPUs that are available for a given process to run on.
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
 - PsQueryProcessAvailableCpusCount
f1_keywords:
 - PsQueryProcessAvailableCpusCount
 - wdm/PsQueryProcessAvailableCpusCount
dev_langs:
 - c++
helpviewer_keywords:
 - PsQueryProcessAvailableCpusCount
---

## -description

The **PsQueryProcessAvailableCpusCount** function queries the count of CPUs that are available for a given process to run on.

## -parameters

### -param Process [in]

Pointer to a process (PEPROCESS).

### -param AvailableCpuCount [out]

Pointer to a buffer that will receive the count of available CPUs to the given process.

### -param SequenceNumber [out]

Pointer to a buffer that will receive the current sequence number for the available CPUs to the given process.

## -returns

**PsQueryProcessAvailableCpusCount** returns an NTSTATUS value. Possible return values include:

| Return code | Description |
|-------------|-------------|
| **STATUS_SUCCESS** | The query was completed successfully. |
| **STATUS_INVALID_PARAMETER** | Any of the required parameters is NULL. |

## -remarks

This routine can be called at IRQL from PASSIVE_LEVEL to DISPATCH_LEVEL.

This function provides a simpler alternative to [**PsQueryProcessAvailableCpus**](nf-wdm-psqueryprocessavailablecpus.md) when only the count of available CPUs is needed, rather than the detailed affinity information.

The sequence number allows callers to track changes in CPU availability and can be used with [**PsQueryProcessAvailableCpus**](nf-wdm-psqueryprocessavailablecpus.md) for optimized queries.

## -see-also

[**PsQueryProcessAvailableCpus**](nf-wdm-psqueryprocessavailablecpus.md)

[**PsQuerySystemAvailableCpusCount**](nf-wdm-psquerysystemavailablecpuscount.md)
