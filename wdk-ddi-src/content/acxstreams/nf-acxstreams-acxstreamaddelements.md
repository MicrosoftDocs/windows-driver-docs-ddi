---
UID: NF:acxstreams.AcxStreamAddElements
tech.root: audio
title: AcxStreamAddElements
ms.date: 07/09/2021
targetos: Windows
description: AcxStreamAddElements is used to add stream elements.
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
 - AcxStreamAddElements
f1_keywords:
 - AcxStreamAddElements
 - acxstreams/AcxStreamAddElements
dev_langs:
 - c++
---

## -description

AcxStreamAddElements is used to add stream elements.

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An [ACXSTREAM Object]() (DocsTeam - need link to ACX Object Summary topic) that represents an audio stream created by a circuit. ACX objects are WDF object-like, i.e., the ACX driver interacts with them in the same way as WDF when creating, deleting, and interacting with them. For more information, see [WDF Architecture](/windows-hardware/drivers/wdf/kernel-mode-driver-framework-architecture) and [Framework Object Life Cycle](/windows-hardware/drivers/wdf/framework-object-life-cycle).

The ACXSTREAM Object is the driver component that’s created to represent an audio stream, created by a circuit. The Stream is composed of a list of Elements created based on the parent Circuit’s Elements.   An AcxStream aggregates zero or n AcxElements-like objects. By default, AcxElements are connected in the same order of assembly. An AcxStream is associated with only one ACX circuit. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RT stream objects used by streaming circuits.

### -param Elements

A pointer to a location that receives a handle to the new [ACXELEMENT Object]() (DocsTeam - need link to ACX Object Summary topic).

### -param ElementsCount

The count of elements TBD. This is a 0/1 TBD based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp

    elementCtx = GetElementContext(elements[0]);
 
    ACX_ELEMENT_CONFIG_INIT(&elementCfg);
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, ELEMENT_CONTEXT);
 
    attributes.ParentObject = stream;
    status = AcxElementCreate(stream, &attributes, &elementCfg, &elements[1]);
    elementCtx = GetElementContext(elements[1]);
    //
    // Add stream elements
    //
    status = AcxStreamAddElements(stream, elements, SIZEOF_ARRAY(elements));
```

## -see-also

[acxstreams.h header](index.md)

