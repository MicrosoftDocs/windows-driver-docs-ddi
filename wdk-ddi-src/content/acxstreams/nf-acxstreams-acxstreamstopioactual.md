---
UID: NF:acxstreams.AcxStreamStopIoActual
tech.root: audio
title: AcxStreamStopIoActual
ms.date: 02/04/2022
targetos: Windows
description: The AcxStreamStopIoActual function is used to stop the IO for a stream. 
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

A pointer to an existing ACXSTREAM Object. An ACXSTREAM Object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Flags

TBD - The following flags are defined to TBD TBD.

TBD - Set to null as no flags are defined.

### -param ObjectTag

An optional ObjectTag that is a driver-defined value that the framework stores as an identification tag for the ACX driver.

### -param Line

The Line number in the driver code that can be displayed for diagnostic purposes.

### -param File

The file name in the driver code that can be displayed for diagnostic purposes.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

It is not recommended to use this version of the stop IO call, but rather [AcxStreamStopIoWithTag](nf-acxstreams-acxstreamstopiowithtag.md).


## -see-also

[acxstreams.h header](index.md)

