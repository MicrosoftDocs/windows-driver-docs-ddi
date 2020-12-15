---
UID: NS:wdm._FILE_SFIO_RESERVE_INFORMATION
title: FILE_SFIO_RESERVE_INFORMATION
ms.date: 11/20/2020
tech.root: ifsk
ms.topic: language-reference
targetos: Windows
description: FILE_SFIO_RESERVE_INFORMATION is used to query or set a file's reserved bandwidth information for scheduled file I/O (SFIO).
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: FILE_SFIO_RESERVE_INFORMATION, *PFILE_SFIO_RESERVE_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _FILE_SFIO_RESERVE_INFORMATION
 - PFILE_SFIO_RESERVE_INFORMATION
 - FILE_SFIO_RESERVE_INFORMATION
f1_keywords:
 - _FILE_SFIO_RESERVE_INFORMATION
 - wdm/_FILE_SFIO_RESERVE_INFORMATION
 - PFILE_SFIO_RESERVE_INFORMATION
 - wdm/PFILE_SFIO_RESERVE_INFORMATION
 - FILE_SFIO_RESERVE_INFORMATION
 - wdm/FILE_SFIO_RESERVE_INFORMATION
dev_langs:
 - c++
---

## -description

**FILE_SFIO_RESERVE_INFORMATION** is used to query or set a file's reserved bandwidth information for scheduled file I/O (SFIO).

## -struct-fields

### -field RequestsPerPeriod

Number of I/O requests that complete per period of time, as specified by the **Period** field. When setting bandwidth reservation, a value of 0 indicates to the file system that it must free any existing reserved bandwidth.

### -field Period

The period for reservation, which is the time from which the I/O is issued to the kernel until the time the I/O should be completed, specified in milliseconds.

### -field RetryFailures

Boolean value.

### -field Discardable

Boolean value. When TRUE, the I/O should be completed with an error if a driver is unable to satisfy the I/O within the deadline.

### -field RequestSize

Minimum size of any individual I/O request that can be issued by an application using bandwidth reservation.

### -field NumOutstandingRequests

The number of **RequestSize** I/O requests allowed to be outstanding at any time. When setting reservations, this field MUST be ignored by servers and SHOULD be set to 0 by clients.

## -remarks

## -see-also

[**NtQueryInformationFile**](../ntifs/nf-ntifs-ntqueryinformationfile.md)
