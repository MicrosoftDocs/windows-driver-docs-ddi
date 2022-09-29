---
UID: NF:bdasup.BdaValidateNodeProperty
title: BdaValidateNodeProperty function (bdasup.h)
description: The BdaValidateNodeProperty function validates that a node property request is associated with a specific pin.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaValidateNodeProperty function"]
ms.keywords: BdaValidateNodeProperty, BdaValidateNodeProperty function [Streaming Media Devices], bdaref_a6f1ec2f-9e23-4cbb-a3dc-fab0d2c5ca1c.xml, bdasup/BdaValidateNodeProperty, stream.bdavalidatenodeproperty
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
 - BdaValidateNodeProperty
 - bdasup/BdaValidateNodeProperty
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaValidateNodeProperty
---

## -description

The **BdaValidateNodeProperty** function validates that a node property request is associated with a specific pin.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to validate that the current pin controls the node property at *pProperty*. The BDA minidriver can receive this IRP with the [KSPROPERTY_BDA_RF_TUNER_FREQUENCY](/windows-hardware/drivers/stream/ksproperty-bda-rf-tuner-frequency) or [KSPROPERTY_BDA_AUTODEMODULATE_START](/windows-hardware/drivers/stream/ksproperty-bda-autodemodulate-start) request.

### -param pProperty [in]

Points to a [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property and request type of the property request.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A pin method in a BDA minidriver calls the **BdaValidateNodeProperty** function to validate that the pin controls a specific node property after the minidriver receives the node property request from the network provider. This node property request can be, for example, a [KSPROPERTY_BDA_RF_TUNER_FREQUENCY](/windows-hardware/drivers/stream/ksproperty-bda-rf-tuner-frequency) request of the [KSPROPSETID_BdaFrequencyFilter](/windows-hardware/drivers/stream/kspropsetid-bdafrequencyfilter) property set or a [KSPROPERTY_BDA_AUTODEMODULATE_START](/windows-hardware/drivers/stream/ksproperty-bda-autodemodulate-start) request of the [KSPROPSETID_BdaAutodemodulate](/windows-hardware/drivers/stream/kspropsetid-bdaautodemodulate) property set. These property sets manipulate tuner and demodulator nodes. After successfully calling **BdaValidateNodeProperty**, the minidriver obtains a pointer to the BDA filter from the passed IRP so that the minidriver can perform an operation on the particular node.

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_BDA_AUTODEMODULATE_START](/windows-hardware/drivers/stream/ksproperty-bda-autodemodulate-start)

[KSPROPERTY_BDA_RF_TUNER_FREQUENCY](/windows-hardware/drivers/stream/ksproperty-bda-rf-tuner-frequency)

[KSPROPSETID_BdaAutodemodulate](/windows-hardware/drivers/stream/kspropsetid-bdaautodemodulate)

[KSPROPSETID_BdaFrequencyFilter](/windows-hardware/drivers/stream/kspropsetid-bdafrequencyfilter)
