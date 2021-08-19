---
UID: NF:acxstreams.AcxStreamGetElementById
tech.root: audio
title: AcxStreamGetElementById
ms.date: 07/12/2021
targetos: Windows
description: The AcxStreamGetElementById function returns ACXELEMENT Object for the requested element ID.
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
 - AcxStreamGetElementById
f1_keywords:
 - AcxStreamGetElementById
 - acxstreams/AcxStreamGetElementById
dev_langs:
 - c++
---

## -description

The AcxStreamGetElementById function returns  [ACXELEMENT Object]() (DocsTeam - need link to ACX Object Summary topic) for the requested element ID.

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An [ACXSTREAM Object]() (DocsTeam - need link to ACX Object Summary topic) that represents an audio stream created by a circuit. ACX objects are WDF object-like, i.e., the ACX driver interacts with them in the same way as WDF when creating, deleting, and interacting with them. For more information, see [WDF Architecture](/windows-hardware/drivers/wdf/kernel-mode-driver-framework-architecture) and [Framework Object Life Cycle](/windows-hardware/drivers/wdf/framework-object-life-cycle).

The ACXSTREAM Object is the driver component that’s created to represent an audio stream, created by a circuit. The Stream is composed of a list of Elements created based on the parent Circuit’s Elements.   An AcxStream aggregates zero or n AcxElements-like objects. By default, AcxElements are connected in the same order of assembly. An AcxStream is associated with only one ACX circuit. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RT stream objects used by streaming circuits.

### -param ElementId

A 0/1 (TBD?) based count of the requested element number. 

## -returns

A pointer to a location that receives a handle to the new [ACXELEMENT Object]() (DocsTeam - need link to ACX Object Summary topic).

## -remarks

### Example

Example usage is shown below.

```cpp
    ULONGLONG               index       = GetMessageContext(Event); // Context is an index.
    ACXELEMENT              element     = nullptr;
    //
    // Get the ACX element.
    //
    element = AcxStreamGetElementById(Stream, (ULONG)index);
```


## -see-also

[acxstreams.h header](index.md)

