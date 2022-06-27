---
UID: NF:bdasup.BdaPropertyGetControllingPinId
title: BdaPropertyGetControllingPinId function (bdasup.h)
description: The BdaPropertyGetControllingPinId function retrieves the identifier of a pin on which to control the properties, methods, and events of a specific node.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaPropertyGetControllingPinId function"]
ms.keywords: BdaPropertyGetControllingPinId, BdaPropertyGetControllingPinId function [Streaming Media Devices], bdaref_7f3a3695-4599-4b16-8a90-4ac171ab1ec0.xml, bdasup/BdaPropertyGetControllingPinId, stream.bdapropertygetcontrollingpinid
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
 - BdaPropertyGetControllingPinId
 - bdasup/BdaPropertyGetControllingPinId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaPropertyGetControllingPinId
---

## -description

The **BdaPropertyGetControllingPinId** function retrieves the identifier of a pin on which to control the properties, methods, and events of a specific node.

## -parameters

### -param Irp [in]

Points to the IRP for the request to retrieve the controlling pin for a node. The BDA minidriver receives this IRP with the [KSPROPERTY_BDA_CONTROLLING_PIN_ID](/windows-hardware/drivers/stream/ksproperty-bda-controlling-pin-id) request.

### -param Property [in]

Points to a [KSP_BDA_NODE_PIN](/windows-hardware/drivers/ddi/bdamedia/ns-bdamedia-_ksp_bda_node_pin) structure that describes the property and request type of the property request to retrieve the controlling pin for a node.

### -param pulControllingPinId [out, optional]

Points to a variable that receives the identifier of the controlling pin for a node.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaPropertyGetControllingPinId** function to retrieve the identifier of the controlling pin for a node after the minidriver receives a [KSPROPERTY_BDA_CONTROLLING_PIN_ID](/windows-hardware/drivers/stream/ksproperty-bda-controlling-pin-id) request of the [KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology) property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the **BdaPropertyGetControllingPinId** function directly, without intercepting this request using an internal get-handler ([KStrGetPropertyHandler](/previous-versions/ff567177(v=vs.85))). See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Determining BDA Device Topology](/windows-hardware/drivers/stream/determining-bda-device-topology) for more information.

## -see-also

[KSPROPERTY_BDA_CONTROLLING_PIN_ID](/windows-hardware/drivers/stream/ksproperty-bda-controlling-pin-id)

[KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology)

[KSP_BDA_NODE_PIN](/windows-hardware/drivers/ddi/bdamedia/ns-bdamedia-_ksp_bda_node_pin)
