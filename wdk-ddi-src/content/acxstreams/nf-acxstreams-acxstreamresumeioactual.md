---
UID: NF:acxstreams.AcxStreamResumeIoActual
tech.root: audio
title: AcxStreamResumeIoActual
ms.date: 07/14/2021
targetos: Windows
description: The AcxStreamResumeIoActual function is used to resume actual IO for a stream TBD.
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
 - AcxStreamResumeIoActual
f1_keywords:
 - AcxStreamResumeIoActual
 - acxstreams/AcxStreamResumeIoActual
dev_langs:
 - c++
---

## -description

The AcxStreamResumeIoActual function is used to resume actual IO for a stream TBD. It is different from the [AcxStreamResumeIo](nf-acxstreams-acxstreamresumeio.md) function, in that it TBD.

## -parameters

### -param Stream

A pointer to an existing ACXSTREAM Object. An ACXSTREAM Object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ObjectTag

An optional ObjectTag that is used to TBD. (can be displayed for diagnostic information??? TBD)

### -param Line

The Line number in the TBD that is used to TBD. (can be displayed for diagnostic information??? TBD)

### -param File

The File that is used to TBD. (can be displayed for diagnostic information??? TBD)

## -returns

Void


## -remarks

### Example

Example usage is shown below.

TBD No example code found

```cpp

```



## -see-also

[acxstreams.h header](index.md)

