---
UID: NF:acxstreams.AcxStreamStopIoWithTag
tech.root: audio
title: AcxStreamStopIoWithTag
ms.date: 02/04/2022
targetos: Windows
description: The AcxStreamStopIo function is used to temporarily stop the IO for a stream.
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
 - AcxStreamStopIoWithTag
f1_keywords:
 - AcxStreamStopIoWithTag
 - acxstreams/AcxStreamStopIoWithTag
dev_langs:
 - c++
---

## -description

The **AcxStreamStopIoWithTag** function is used used to signal to the operating system to temporarily stop stream IO. This allows the driver a short period of time to run time sensitive tasks, and then resume IO after the execution of time sensitive code is complete.

## -parameters

### -param Stream

An existing ACXSTREAM Object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Flags

Set to AcxStopIoNoFlags.

### -param Tag

An optional Tag that is a driver-defined value that the framework includes with diagnostic tracing.

## -remarks

Do not call AcxStreamStopIoWithTag from an I/O dispatched thread. This will cause a deadlock.

### Example

Example usage is shown below.

```cpp

    //
    // Temporarily disable this stream's I/Os. This thread cannot be an I/O dispatched thread else we deadlock.
    //
    status = AcxStreamStopIoWithTag(stream, AcxStopIoNoFlags, (PVOID)this);

```


## -see-also

- [acxstreams.h header](index.md)

READY2GO
