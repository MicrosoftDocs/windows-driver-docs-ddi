---
UID: NF:bdasup.BdaMethodDeletePin
title: BdaMethodDeletePin function (bdasup.h)
description: The BdaMethodDeletePin function deletes a pin factory.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaMethodDeletePin function"]
ms.keywords: BdaMethodDeletePin, BdaMethodDeletePin function [Streaming Media Devices], bdaref_6d81ac60-26e8-4cdb-ba9c-05f73cea187d.xml, bdasup/BdaMethodDeletePin, stream.bdamethoddeletepin
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
 - BdaMethodDeletePin
 - bdasup/BdaMethodDeletePin
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaMethodDeletePin
---

## -description

The **BdaMethodDeletePin** function deletes a pin factory.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to delete a pin factory. The BDA minidriver receives this IRP with the [KSMETHOD_BDA_DELETE_PIN_FACTORY](/windows-hardware/drivers/stream/ksmethod-bda-delete-pin-factory) request.

### -param pKSMethod [in]

Points to a [KSMETHOD](/windows-hardware/drivers/stream/ksmethod-structure) structure that describes the method and request type of a method request.

### -param pvIgnored

Points to a buffer that is ignored.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaMethodDeletePin** function to delete a pin factory after the minidriver receives a [KSMETHOD_BDA_DELETE_PIN_FACTORY](/windows-hardware/drivers/stream/ksmethod-bda-delete-pin-factory) request of the [KSMETHODSETID_BdaDeviceConfiguration](/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration) method set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the **BdaMethodDeletePin** function directly, without intercepting this request using an internal method ([KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)). See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Configuring a BDA Filter](/windows-hardware/drivers/stream/configuring-a-bda-filter) for more information.

If a BDA minidriver must delete a pin without relying on the network provider, the BDA minidriver should call the [BdaDeletePin](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdadeletepin) function.

## -see-also

[BdaDeletePin](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdadeletepin)

[BdaMethodCreatePin](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdamethodcreatepin)

[KSMETHOD](/windows-hardware/drivers/stream/ksmethod-structure)

[KSMETHODSETID_BdaDeviceConfiguration](/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration)

[KSMETHOD_BDA_DELETE_PIN_FACTORY](/windows-hardware/drivers/stream/ksmethod-bda-delete-pin-factory)

[KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)
