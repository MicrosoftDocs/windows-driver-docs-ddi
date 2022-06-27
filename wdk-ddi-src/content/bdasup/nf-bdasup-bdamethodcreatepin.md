---
UID: NF:bdasup.BdaMethodCreatePin
title: BdaMethodCreatePin function (bdasup.h)
description: The BdaMethodCreatePin function creates a pin factory.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaMethodCreatePin function"]
ms.keywords: BdaMethodCreatePin, BdaMethodCreatePin function [Streaming Media Devices], bdaref_492b1847-e4b7-4dfd-a8b1-c6c17fc6aff8.xml, bdasup/BdaMethodCreatePin, stream.bdamethodcreatepin
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
 - BdaMethodCreatePin
 - bdasup/BdaMethodCreatePin
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaMethodCreatePin
---

## -description

The **BdaMethodCreatePin** function creates a pin factory.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to create a pin factory. The BDA minidriver receives this IRP with the [KSMETHOD_BDA_CREATE_PIN_FACTORY](/windows-hardware/drivers/stream/ksmethod-bda-create-pin-factory) request.

### -param pKSMethod [in]

Points to a [KSMETHOD](/windows-hardware/drivers/stream/ksmethod-structure) structure that describes the method and request type of a method request.

### -param pulPinFactoryID [out, optional]

Points to a variable that receives the identifier of the pin factory.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaMethodCreatePin** function to create a pin factory after the minidriver receives a [KSMETHOD_BDA_CREATE_PIN_FACTORY](/windows-hardware/drivers/stream/ksmethod-bda-create-pin-factory) request of the [KSMETHODSETID_BdaDeviceConfiguration](/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration) method set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the **BdaMethodCreatePin** function directly, without intercepting this request using an internal method ([KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)). See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Configuring a BDA Filter](/windows-hardware/drivers/stream/configuring-a-bda-filter) for more information.

If a BDA minidriver must create a pin without relying on the network provider, the BDA minidriver should call the **BdaCreatePin** function.

## -see-also

[BdaCreatePin](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatepin)

[BdaMethodDeletePin](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdamethoddeletepin)

[KSMETHOD](/windows-hardware/drivers/stream/ksmethod-structure)

[KSMETHODSETID_BdaDeviceConfiguration](/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration)

[KSMETHOD_BDA_CREATE_PIN_FACTORY](/windows-hardware/drivers/stream/ksmethod-bda-create-pin-factory)

[KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)
