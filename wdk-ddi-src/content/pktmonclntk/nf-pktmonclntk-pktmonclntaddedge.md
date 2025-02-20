---
UID: NF:pktmonclntk.PktMonClntAddEdge
tech.root: netvista
title: PktMonClntAddEdge
ms.date: 02/13/2025
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntk.h
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
 - pktmonclntk.h
api_name:
 - PktMonClntAddEdge
f1_keywords:
 - PktMonClntAddEdge
 - pktmonclntk/PktMonClntAddEdge
dev_langs:
 - c++
helpviewer_keywords:
 - PktMonClntAddEdge
---

## -description

The **PktMonClntAddEdge** function adds an edge to a Packet Monitor component. An edge represents a pair of entry/exit points for a component. It can be referred to as a boundary for a component. Each component registers its lower or/and upper edge.

## -parameters

### -param CompContext

Pointer to the **[PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)** structure that holds the context for the component.

### -param Name

The name of the edge being added.

### -param PacketType

Packet type to be handled by this edge. Must be a valid value defined in **[PKTMON_PACKET_TYPE](../pktmonnpik/ne-pktmonnpik-pktmon_packet_type.md)**.

### -param EdgeContext

Pointer to a **[PKTMON_EDGE_CONTEXT](ns-pktmonclntk-pktmon_edge_context.md)** which will store the context information for this edge.

## -returns

If the function succeeds, it returns `STATUS_SUCCESS`. Otherwise, it returns a `NTSTATUS` error code.

## -remarks

An edge represents a pair of entry and exit points for a component. It can be referred to as a boundary for a component. Each component registers its lower and/or upper edge. A component can have multiple edges. One call to **PktMonClntAddEdge** should be made for each of these edges.

The *ListLink* member of **[PKTMON_EDGE_CONTEXT](ns-pktmonclntk-pktmon_edge_context.md)** is used to track all the edge contexts belonging to a component. *ListLink* can be used to access these edge contexts.

## -see-also

- **[PKTMON_PACKET_TYPE](../pktmonnpik/ne-pktmonnpik-pktmon_packet_type.md)**
- **[PKTMON_EDGE_CONTEXT](../pktmonclntk//ns-pktmonclntk-pktmon_edge_context.md)**

### Example

```cpp
PKTMON_EDGE_CONTEXT EdgeContext = { 0 };

NTSTATUS
NTAPI
PktMonApiTstAddEdge()
{
    NTSTATUS status = STATUS_SUCCESS;

    DECLARE_CONST_UNICODE_STRING(EdgeName, L"LowerEdge");

    status = PktMonClntAddEdge(
        &PktMonComp,
        &EdgeName,
        PktMonPayload_IP,
        &EdgeContext
    );
    if (STATUS_SUCCESS != status)
    {
        return status;
    }

    return status;
}
```
