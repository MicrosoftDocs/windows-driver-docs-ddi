---
UID: NF:acxstreams.AcxStreamStopIoActual
tech.root: audio
title: AcxStreamStopIoActual
ms.date: 07/22/2022
targetos: Windows
description: The AcxStreamStopIoActual function is used to temporarily stop the IO for a stream.
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
 - AcxStreamStopIoActual
f1_keywords:
 - AcxStreamStopIoActual
 - acxstreams/AcxStreamStopIoActual
dev_langs:
 - c++
---

## -description

The **AcxStreamStopIoActual** function is used to to signal to the operating system to temporarily stop stream IO. This allows the driver a short period of time to run time sensitive tasks, and then resume IO after the execution of time sensitive code is complete.

## -parameters

### -param Stream

An existing ACXSTREAM Object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Flags

Set to AcxStopIoNoFlags.

### -param ObjectTag

An optional Tag that is a driver-defined value that the framework includes with diagnostic tracing.

### -param Line

The Line number in the driver code that can be displayed for diagnostic purposes.

### -param File

The file name in the driver code that can be displayed for diagnostic purposes.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

It is not recommended to use this version of the stop IO call, but rather [AcxStreamStopIoWithTag](nf-acxstreams-acxstreamstopiowithtag.md).


### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

[acxstreams.h header](index.md)
[AcxStreamStopIoWithTag](nf-acxstreams-acxstreamstopiowithtag.md)

