---
UID: NF:wdm.PsQuerySystemAvailableCpusCount
tech.root: kernel
title: PsQuerySystemAvailableCpusCount
ms.date: 08/05/2025
targetos: Windows
description: The PsQuerySystemAvailableCpusCount function queries the count of CPUs that are available to the system process.
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
 - PsQuerySystemAvailableCpusCount
f1_keywords:
 - PsQuerySystemAvailableCpusCount
 - wdm/PsQuerySystemAvailableCpusCount
dev_langs:
 - c++
helpviewer_keywords:
 - PsQuerySystemAvailableCpusCount
---

## -description

The **PsQuerySystemAvailableCpusCount** function queries the count of CPUs that are available to the system process.

## -parameters

### -param AvailableCpuCount [out]

Pointer to a buffer that will receive the count of available CPUs to the system process.

### -param SequenceNumber [out]

Pointer to a buffer that will receive the current sequence number for the available CPUs to the system process.

## -returns

**PsQuerySystemAvailableCpusCount** returns an NTSTATUS value. Possible return values include:

| Return code | Description |
|-------------|-------------|
| **STATUS_SUCCESS** | The query was completed successfully. |
| **STATUS_INVALID_PARAMETER** | Any of the required parameters is NULL. |

## -remarks

This routine can be called at IRQL from PASSIVE_LEVEL to DISPATCH_LEVEL.

This function provides a simpler alternative to [**PsQuerySystemAvailableCpus**](nf-wdm-psquerysystemavailablecpus.md) when only the count of available CPUs is needed, rather than the detailed affinity information.

The sequence number allows callers to track changes in CPU availability and can be used with [**PsQuerySystemAvailableCpus**](nf-wdm-psquerysystemavailablecpus.md) for optimized queries.

This function queries CPU availability for the system process, which typically represents all available CPUs in the system.

## -see-also

[**PsQuerySystemAvailableCpus**](nf-wdm-psquerysystemavailablecpus.md)

[**PsQueryProcessAvailableCpusCount**](nf-wdm-psqueryprocessavailablecpuscount.md)
