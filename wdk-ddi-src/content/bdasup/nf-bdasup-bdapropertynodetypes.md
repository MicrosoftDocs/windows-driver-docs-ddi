---
UID: NF:bdasup.BdaPropertyNodeTypes
title: BdaPropertyNodeTypes function (bdasup.h)
description: The BdaPropertyNodeTypes function retrieves a list of node types in a template topology.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaPropertyNodeTypes function"]
ms.keywords: BdaPropertyNodeTypes, BdaPropertyNodeTypes function [Streaming Media Devices], bdaref_cec37979-eb0c-4914-86fe-6dc613c61ae8.xml, bdasup/BdaPropertyNodeTypes, stream.bdapropertynodetypes
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - BdaPropertyNodeTypes
 - bdasup/BdaPropertyNodeTypes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaPropertyNodeTypes
---

## -description

The **BdaPropertyNodeTypes** function retrieves a list of node types in a template topology.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to retrieve the list of node types. The BDA minidriver receives this IRP with the [KSPROPERTY_BDA_NODE_TYPES](/windows-hardware/drivers/stream/ksproperty-bda-node-types) request.

### -param pKSProperty [in]

Points to a [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property and request type of the property request.

### -param pulProperty [out]

Points to an array that receives the list of node types.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaPropertyNodeTypes** function to retrieve the list of node types after the minidriver receives a [KSPROPERTY_BDA_NODE_TYPES](/windows-hardware/drivers/stream/ksproperty-bda-node-types) request of the [KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology) property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the **BdaPropertyNodeTypes** function directly, without intercepting this request using an internal get-handler ([KStrGetPropertyHandler](/previous-versions/ff567177(v=vs.85))). See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Determining BDA Device Topology](/windows-hardware/drivers/stream/determining-bda-device-topology) for more information.

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_BDA_NODE_TYPES](/windows-hardware/drivers/stream/ksproperty-bda-node-types)

[KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology)
