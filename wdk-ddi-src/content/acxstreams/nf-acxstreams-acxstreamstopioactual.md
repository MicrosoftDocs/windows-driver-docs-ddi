---
UID: NF:acxstreams.AcxStreamStopIoActual
tech.root: audio
title: AcxStreamStopIoActual
ms.date: 07/14/2021
targetos: Windows
description: The AcxStreamStopIoActual function is used to stop the IO for a stream TBD. 
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

The AcxStreamStopIoActual function is used to stop the IO for a stream TBD. It is different from the [AcxStreamStopIo](nf-acxstreams-acxstreamstopio.md) function, in that it TBD.

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Flags

TBD
TBD - The following flags are defined to TBD TBD.
TBD
TBD - Set to null as no flags are defined.

### -param ObjectTag

An optional ObjectTag that is used to TBD. (can be displayed for diagnostic information??? TBD)

### -param Line

The Line number in the TBD that is used to TBD. (can be displayed for diagnostic information??? TBD)

### -param File

The File that is used to TBD. (can be displayed for diagnostic information??? TBD)

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.


TBD No example code found

```cpp

```



## -see-also

[acxstreams.h header](index.md)

