---
UID: NF:acxstreams.AcxStreamGetCircuit
tech.root: audio
title: AcxStreamGetCircuit
ms.date: 07/12/2021
targetos: Windows
description: The AcxStreamGetCircuit function returns the ACXCIRCUIT Object associated with the stream.
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
 - AcxStreamGetCircuit
f1_keywords:
 - AcxStreamGetCircuit
 - acxstreams/AcxStreamGetCircuit
dev_langs:
 - c++
---

## -description

The AcxStreamGetCircuit function returns the [ACXCIRCUIT Object]() (DocsTeam - need link to ACX Object Summary topic) associated with the stream.

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An [ACXSTREAM Object]() (DocsTeam - need link to ACX Object Summary topic) that represents an audio stream created by a circuit. ACX objects are WDF object-like, i.e., the ACX driver interacts with them in the same way as WDF when creating, deleting, and interacting with them. For more information, see [WDF Architecture](/windows-hardware/drivers/wdf/kernel-mode-driver-framework-architecture) and [Framework Object Life Cycle](/windows-hardware/drivers/wdf/framework-object-life-cycle).

The ACXSTREAM Object is the driver component that’s created to represent an audio stream, created by a circuit. The Stream is composed of a list of Elements created based on the parent Circuit’s Elements.   An AcxStream aggregates zero or n AcxElements-like objects. By default, AcxElements are connected in the same order of assembly. An AcxStream is associated with only one ACX circuit. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RT stream objects used by streaming circuits.

## -returns

A pointer to a location that receives a handle to the [ACXCIRCUIT Object]() (DocsTeam - need link to ACX Object Summary topic) associated with the stream.

## -remarks

### Example

Example usage is shown below.

```cpp
    streamCtx = GetMyStreamContext(stream);
    streamCtx->StreamEngine = (PVOID)streamEngine;
    streamEngine = NULL;
    ACXCIRCUIT testCircuit = AcxStreamGetCircuit(stream);
```

## -see-also

[acxstreams.h header](index.md)

