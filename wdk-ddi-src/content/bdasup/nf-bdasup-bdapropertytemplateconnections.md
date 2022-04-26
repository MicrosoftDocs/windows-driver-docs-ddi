---
UID: NF:bdasup.BdaPropertyTemplateConnections
title: BdaPropertyTemplateConnections function (bdasup.h)
description: The BdaPropertyTemplateConnections function retrieves a list of connections that describe how pin types and node types are connected in a template topology.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaPropertyTemplateConnections function"]
ms.keywords: BdaPropertyTemplateConnections, BdaPropertyTemplateConnections function [Streaming Media Devices], bdaref_919b0c2d-5bb9-4e17-8028-79f669ab7b8c.xml, bdasup/BdaPropertyTemplateConnections, stream.bdapropertytemplateconnections
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
 - BdaPropertyTemplateConnections
 - bdasup/BdaPropertyTemplateConnections
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaPropertyTemplateConnections
---

## -description

The **BdaPropertyTemplateConnections** function retrieves a list of connections that describe how pin types and node types are connected in a template topology.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to retrieve the list of connections. The BDA minidriver receives this IRP with the [KSPROPERTY_BDA_TEMPLATE_CONNECTIONS](/windows-hardware/drivers/stream/ksproperty-bda-template-connections) request.

### -param pKSProperty [in]

Points to a [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property and request type of the property request.

### -param pConnectionProperty [out, optional]

Points to an array that receives the list of [KSTOPOLOGY_CONNECTION](/windows-hardware/drivers/ddi/ks/ns-ks-kstopology_connection) structures that describe the connections in a template topology.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaPropertyTemplateConnections** function to retrieve the list of template connections after the minidriver receives a [KSPROPERTY_BDA_TEMPLATE_CONNECTIONS](/windows-hardware/drivers/stream/ksproperty-bda-template-connections) request of the [KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology) property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the **BdaPropertyTemplateConnections** function directly, without intercepting this request using an internal get-handler ([KStrGetPropertyHandler](/previous-versions/ff567177(v=vs.85))). See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Determining BDA Device Topology](/windows-hardware/drivers/stream/determining-bda-device-topology) for more information.

The BDA minidriver provided a list of connections to the BDA support library in an array of [KSTOPOLOGY_CONNECTION](/windows-hardware/drivers/ddi/ks/ns-ks-kstopology_connection) structures when the BDA minidriver passed the BDA filter template ([BDA_FILTER_TEMPLATE](/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_filter_template)) in [BdaCreateFilterFactory](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatefilterfactory) and [BdaInitFilter](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdainitfilter) function calls. This array is a representation of all the possible connections between node and pin types that can be made within the filter or between the filter and adjoining filters. The **BdaPropertyTemplateConnections** function returns this array.

## -see-also

[BDA_FILTER_TEMPLATE](/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_filter_template)

[BdaCreateFilterFactory](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatefilterfactory)

[BdaInitFilter](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdainitfilter)

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_BDA_TEMPLATE_CONNECTIONS](/windows-hardware/drivers/stream/ksproperty-bda-template-connections)

[KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology)

[KSTOPOLOGY_CONNECTION](/windows-hardware/drivers/ddi/ks/ns-ks-kstopology_connection)
