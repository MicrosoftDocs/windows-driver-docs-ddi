---
UID: NF:acxstreams.AcxStreamResumeIoWithTag
tech.root: audio
title: AcxStreamResumeIoWithTag
ms.date: 07/22/2022
targetos: Windows
description: The AcxStreamResumeIoWithTag function is used to resume IO for a stream. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: 
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
 - acxstreams.h
api_name:
 - AcxStreamResumeIoWithTag
f1_keywords:
 - AcxStreamResumeIoWithTag
 - acxstreams/AcxStreamResumeIoWithTag
dev_langs:
 - c++
---

## -description

The **AcxStreamResumeIoWithTag** function is used to resume IO for a stream after stream IO has been stopped. It is similar to [AcxStreamResumeIo](nf-acxstreams-acxstreamresumeio.md) function, but provides the ability to use a Tag that provides additional diagnostic information.

## -parameters

### -param Stream

An existing ACXSTREAM Object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Tag

An optional Tag that is a driver-defined value that the framework includes with diagnostic tracing.

## -returns

Void

## -remarks

### Example

Example usage is shown below.

```cpp

    //
    // Resume stream IO after it was stopped with AcxStreamStopIoWithTag.
    //
    status = AcxStreamResumeIoWithTag(stream, (PVOID)this);

```

## -see-also

- [acxstreams.h header](index.md)

READY2GO

EDITCOMPLETE
