---
UID: NF:bdasup.BdaPropertyNodeDescriptors
title: BdaPropertyNodeDescriptors function (bdasup.h)
description: The BdaPropertyNodeDescriptors function retrieves a list of nodes in a template topology.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaPropertyNodeDescriptors function"]
ms.keywords: BdaPropertyNodeDescriptors, BdaPropertyNodeDescriptors function [Streaming Media Devices], bdaref_67976a51-5f21-4369-be96-ab6a2b758e85.xml, bdasup/BdaPropertyNodeDescriptors, stream.bdapropertynodedescriptors
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
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
 - BdaPropertyNodeDescriptors
 - bdasup/BdaPropertyNodeDescriptors
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaPropertyNodeDescriptors
---

## -description

The **BdaPropertyNodeDescriptors** function retrieves a list of nodes in a template topology.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to retrieve the list of nodes. The BDA minidriver receives this IRP with the [KSPROPERTY_BDA_NODE_DESCRIPTORS](/windows-hardware/drivers/stream/ksproperty-bda-node-descriptors) request.

### -param pKSProperty [in]

Points to a [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property and request type of the property request.

### -param pNodeDescriptorProperty [out, optional]

Points to an array that receives the list of GUIDs for the nodes in a template topology.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaPropertyNodeDescriptors** function to retrieve the list of nodes after the minidriver receives a [KSPROPERTY_BDA_NODE_DESCRIPTORS](/windows-hardware/drivers/stream/ksproperty-bda-node-descriptors) request of the [KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology) property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the **BdaPropertyNodeDescriptors** function directly, without intercepting this request using an internal get-handler ([KStrGetPropertyHandler](/previous-versions/ff567177(v=vs.85))). See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Determining BDA Device Topology](/windows-hardware/drivers/stream/determining-bda-device-topology) for more information.

For a list of BDA nodes that are available to create in a template topology, see [BDA Node Category GUIDs](/windows-hardware/drivers/stream/bda-node-category-guids).

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_BDA_NODE_DESCRIPTORS](/windows-hardware/drivers/stream/ksproperty-bda-node-descriptors)

[KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology)
