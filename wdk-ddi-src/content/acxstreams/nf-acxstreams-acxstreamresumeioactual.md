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

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An [ACXSTREAM Object]() (DocsTeam - need link to ACX Object Summary topic) that represents an audio stream created by a circuit. ACX objects are WDF object-like, i.e., the ACX driver interacts with them in the same way as WDF when creating, deleting, and interacting with them. For more information, see [WDF Architecture](/windows-hardware/drivers/wdf/kernel-mode-driver-framework-architecture) and [Framework Object Life Cycle](/windows-hardware/drivers/wdf/framework-object-life-cycle).

The ACXSTREAM Object is the driver component that’s created to represent an audio stream, created by a circuit. The Stream is composed of a list of Elements created based on the parent Circuit’s Elements.   An AcxStream aggregates zero or n AcxElements-like objects. By default, AcxElements are connected in the same order of assembly. An AcxStream is associated with only one ACX circuit. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RT stream objects used by streaming circuits.

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

