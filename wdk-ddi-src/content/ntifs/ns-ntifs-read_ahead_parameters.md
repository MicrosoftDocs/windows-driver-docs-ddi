---
UID: NS:ntifs._READ_AHEAD_PARAMETERS
tech.root: ifsk
title: READ_AHEAD_PARAMETERS
ms.date: 03/13/2023
targetos: Windows
description: Learn more about the READ_AHEAD_PARAMETERS structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: READ_AHEAD_PARAMETERS, *PREAD_AHEAD_PARAMETERS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _READ_AHEAD_PARAMETERS
 - PREAD_AHEAD_PARAMETERS
 - READ_AHEAD_PARAMETERS
f1_keywords:
 - _READ_AHEAD_PARAMETERS
 - ntifs/_READ_AHEAD_PARAMETERS
 - PREAD_AHEAD_PARAMETERS
 - ntifs/PREAD_AHEAD_PARAMETERS
 - READ_AHEAD_PARAMETERS
 - ntifs/READ_AHEAD_PARAMETERS
dev_langs:
 - c++
helpviewer_keywords:
 - _READ_AHEAD_PARAMETERS
---

## -description

The **READ_AHEAD_PARAMETERS** structure contains read-ahead parameters.

## -struct-fields

### -field NodeByteSize

Size of the node, in bytes.

### -field Granularity

Granularity of read-aheads. This value must be an even power of 2 and greater than, or equal to PAGE_SIZE.

### -field PipelinedRequestSize

The request size to be used when performing pipelined read-aheads, in bytes. Each read-ahead request that is pipelined is broken into smaller **PipelinedRequestSize**-sized requests. This is typically used to increase the throughput by parallelizing multiple requests instead of one single big one.

For backward compatibility, the Cache Manager will break every read-ahead request into two if this value is zero.

### -field ReadAheadGrowthPercentage

The growth of read ahead as a percentage of the data that has already been ready by the application so far.

## -see-also

[**CcReadAhead**](/previous-versions/ff539191(v=vs.85))

[**CcScheduleReadAhead**](nf-ntifs-ccschedulereadahead.md)
