---
UID: NF:bdasup.BdaPropertyNodeProperties
title: BdaPropertyNodeProperties function (bdasup.h)
description: The BdaPropertyNodeProperties function retrieves a list of properties that a node supports.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaPropertyNodeProperties function"]
ms.keywords: BdaPropertyNodeProperties, BdaPropertyNodeProperties function [Streaming Media Devices], bdaref_fc328c79-7b0b-4646-91cd-3e4957b30b2a.xml, bdasup/BdaPropertyNodeProperties, stream.bdapropertynodeproperties
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
 - BdaPropertyNodeProperties
 - bdasup/BdaPropertyNodeProperties
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaPropertyNodeProperties
---

## -description

The **BdaPropertyNodeProperties** function retrieves a list of properties that a node supports.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to retrieve the list of properties for a node. The BDA minidriver receives this IRP with the [KSPROPERTY_BDA_NODE_PROPERTIES](/windows-hardware/drivers/stream/ksproperty-bda-node-properties) request.

### -param pKSProperty [in]

Points to a [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property and request type of the property request.

### -param pguidProperty [out, optional]

Points to an array that receives the list of GUIDs for the properties supported by a node.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaPropertyNodeProperties** function to retrieve the list of properties for a node after the minidriver receives a [KSPROPERTY_BDA_NODE_PROPERTIES](/windows-hardware/drivers/stream/ksproperty-bda-node-properties) request of the [KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology) property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the **BdaPropertyNodeProperties** function directly, without intercepting this request using an internal get-handler ([KStrGetPropertyHandler](/previous-versions/ff567177(v=vs.85))). See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Determining BDA Device Topology](/windows-hardware/drivers/stream/determining-bda-device-topology) for more information.

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_BDA_NODE_PROPERTIES](/windows-hardware/drivers/stream/ksproperty-bda-node-properties)

[KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology)
