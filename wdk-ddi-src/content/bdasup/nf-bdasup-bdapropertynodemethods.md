---
UID: NF:bdasup.BdaPropertyNodeMethods
title: BdaPropertyNodeMethods function (bdasup.h)
description: The BdaPropertyNodeMethods function retrieves a list of methods that a node supports.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaPropertyNodeMethods function"]
ms.keywords: BdaPropertyNodeMethods, BdaPropertyNodeMethods function [Streaming Media Devices], bdaref_15a0d157-4e7d-43ae-9f1f-6ffb70bd4f9b.xml, bdasup/BdaPropertyNodeMethods, stream.bdapropertynodemethods
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
 - BdaPropertyNodeMethods
 - bdasup/BdaPropertyNodeMethods
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaPropertyNodeMethods
---

## -description

The **BdaPropertyNodeMethods** function retrieves a list of methods that a node supports.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to retrieve the list of methods for a node. The BDA minidriver receives this IRP with the [KSPROPERTY_BDA_NODE_METHODS](/windows-hardware/drivers/stream/ksproperty-bda-node-methods) request.

### -param pKSProperty [in]

Points to a [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property and request type of the property request.

### -param pguidProperty [out, optional]

Points to an array that receives the list of GUIDs for the methods supported by a node.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaPropertyNodeMethods** function to retrieve the list of methods for a node after the minidriver receives a [KSPROPERTY_BDA_NODE_METHODS](/windows-hardware/drivers/stream/ksproperty-bda-node-methods) request of the [KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology) property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the **BdaPropertyNodeMethods** function directly, without intercepting this request using an internal get-handler ([KStrGetPropertyHandler](/previous-versions/ff567177(v=vs.85))). See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Determining BDA Device Topology](/windows-hardware/drivers/stream/determining-bda-device-topology) for more information.

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_BDA_NODE_METHODS](/windows-hardware/drivers/stream/ksproperty-bda-node-methods)

[KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology)
