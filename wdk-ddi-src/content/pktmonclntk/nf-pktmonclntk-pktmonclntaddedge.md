---
UID: NF:pktmonclntk.PktMonClntAddEdge
tech.root: 
title: PktMonClntAddEdge
ms.date: 02/10/2025
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

This function is used to add an edge to a Packet Monitor component. An edge represents a pair of entry/exit points for a component. It can be referred to as a boundary for a component. Each component registers its lower or/and upper edge.

## -parameters

### -param CompContext

Pointer to PKTMON_COMPONENT_CONTEXT which holds the context for the component.

### -param Name

Name to be used to represent the edge being added.

### -param PacketType

Packet type to be handled by this edge. Must be a valid value defined in PKTMON_PACKET_TYPE.

### -param EdgeContext

Pointer to a PKTMON_EDGE_CONTEXT which will store the context information for this edge.

## -returns

If the function succeeds, it returns STATUS_SUCCESS. Otherwise, it returns a NTSTATUS error code.

## -remarks

A component can have multiple edges. One call to PktMonClntAddEdge should be made for each of these edges.

## -see-also

- [PktMonClntInitialize]()
- [PktMonClntUninitialize]()
- [PktMonClntComponentRegister]()
- [PktMonClntComponentUnregister]()
- [PktMonClntSetComponentProperty]()
- [PktMonClntNblLog]()
- [PktMonClntNblDrop]()
- [PktMonClntHeaderInfoLog]()
- [PktMonClntHeaderInfoDrop]()
