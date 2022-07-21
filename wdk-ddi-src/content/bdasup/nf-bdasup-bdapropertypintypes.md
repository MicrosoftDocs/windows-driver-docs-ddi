---
UID: NF:bdasup.BdaPropertyPinTypes
title: BdaPropertyPinTypes function (bdasup.h)
description: The BdaPropertyPinTypes function retrieves a list of pin types in a template topology.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaPropertyPinTypes function"]
ms.keywords: BdaPropertyPinTypes, BdaPropertyPinTypes function [Streaming Media Devices], bdaref_38003a0c-ac8f-4249-b7b1-a4979f05b7ab.xml, bdasup/BdaPropertyPinTypes, stream.bdapropertypintypes
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
 - BdaPropertyPinTypes
 - bdasup/BdaPropertyPinTypes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaPropertyPinTypes
---

## -description

The **BdaPropertyPinTypes** function retrieves a list of pin types in a template topology.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to retrieve list of pin types. The BDA minidriver receives this IRP with the [KSPROPERTY_BDA_PIN_TYPES](/windows-hardware/drivers/stream/ksproperty-bda-pin-types) request.

### -param pKSProperty [in]

Points to a [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property and request type of the property request.

### -param pulProperty [out]

Points to an array that receives the list of pin types.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaPropertyPinTypes** function to retrieve the list of pin types after the minidriver receives a [KSPROPERTY_BDA_PIN_TYPES](/windows-hardware/drivers/stream/ksproperty-bda-pin-types) request of the [KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology) property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the **BdaPropertyPinTypes** function directly, without intercepting this request using an internal get-handler ([KStrGetPropertyHandler](/previous-versions/ff567177(v=vs.85))). See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Determining BDA Device Topology](/windows-hardware/drivers/stream/determining-bda-device-topology) for more information.

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_BDA_PIN_TYPES](/windows-hardware/drivers/stream/ksproperty-bda-pin-types)

[KSPROPSETID_BdaTopology](/windows-hardware/drivers/stream/kspropsetid-bdatopology)
