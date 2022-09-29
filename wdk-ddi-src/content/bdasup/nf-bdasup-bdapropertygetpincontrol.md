---
UID: NF:bdasup.BdaPropertyGetPinControl
title: BdaPropertyGetPinControl function (bdasup.h)
description: The BdaPropertyGetPinControl function retrieves either the identifier or type of a pin.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaPropertyGetPinControl function"]
ms.keywords: BdaPropertyGetPinControl, BdaPropertyGetPinControl function [Streaming Media Devices], bdaref_f2db3de1-bfa0-4ad9-a537-6cc46f972984.xml, bdasup/BdaPropertyGetPinControl, stream.bdapropertygetpincontrol
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
 - BdaPropertyGetPinControl
 - bdasup/BdaPropertyGetPinControl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaPropertyGetPinControl
---

## -description

The **BdaPropertyGetPinControl** function retrieves either the identifier or type of a pin.

## -parameters

### -param Irp [in]

Points to the IRP for the request to retrieve pin information. The BDA minidriver receives this IRP with either the [KSPROPERTY_BDA_PIN_ID](/windows-hardware/drivers/stream/ksproperty-bda-pin-id) or [KSPROPERTY_BDA_PIN_TYPE](/windows-hardware/drivers/stream/ksproperty-bda-pin-type) request.

### -param Property [in]

Points to a [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property and request type of the property request.

### -param pulProperty [out, optional]

Points to a variable that receives either the identifier or type of a pin.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaPropertyGetPinControl** function to retrieve either the identifier or type of a pin after the minidriver receives either a [KSPROPERTY_BDA_PIN_ID](/windows-hardware/drivers/stream/ksproperty-bda-pin-id) or [KSPROPERTY_BDA_PIN_TYPE](/windows-hardware/drivers/stream/ksproperty-bda-pin-type) request of the [KSPROPSETID_BdaPinControl](/windows-hardware/drivers/stream/kspropsetid-bdapincontrol) property set. Most BDA minidrivers can define pin-automation tables so that those minidrivers dispatch the **BdaPropertyGetPinControl** function directly, without intercepting this request using an internal get-handler ([KStrGetPropertyHandler](/previous-versions/ff567177(v=vs.85))).

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_BDA_PIN_ID](/windows-hardware/drivers/stream/ksproperty-bda-pin-id)

[KSPROPERTY_BDA_PIN_TYPE](/windows-hardware/drivers/stream/ksproperty-bda-pin-type)

[KSPROPSETID_BdaPinControl](/windows-hardware/drivers/stream/kspropsetid-bdapincontrol)
