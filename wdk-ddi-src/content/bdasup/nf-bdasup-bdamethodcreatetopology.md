---
UID: NF:bdasup.BdaMethodCreateTopology
title: BdaMethodCreateTopology function (bdasup.h)
description: The BdaMethodCreateTopology function creates a template topology between two pins of a filter.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaMethodCreateTopology function"]
ms.keywords: BdaMethodCreateTopology, BdaMethodCreateTopology function [Streaming Media Devices], bdaref_3e082bad-4178-430a-aca0-3af6324a0aa2.xml, bdasup/BdaMethodCreateTopology, stream.bdamethodcreatetopology
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
 - BdaMethodCreateTopology
 - bdasup/BdaMethodCreateTopology
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaMethodCreateTopology
---

## -description

The **BdaMethodCreateTopology** function creates a template topology between two pins of a filter.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to create topology. The BDA minidriver receives this IRP with the [KSMETHOD_BDA_CREATE_TOPOLOGY](/windows-hardware/drivers/stream/ksmethod-bda-create-topology) request.

### -param pKSMethod [in]

Points to a [KSMETHOD](/windows-hardware/drivers/stream/ksmethod-structure) structure that describes the method and request type of a method request.

### -param pvIgnored [optional]

Points to a buffer that is ignored.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaMethodCreateTopology** function to create the template topology between two filter pins after the minidriver receives a [KSMETHOD_BDA_CREATE_TOPOLOGY](/windows-hardware/drivers/stream/ksmethod-bda-create-topology) request of the [KSMETHODSETID_BdaDeviceConfiguration](/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration) method set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the **BdaMethodCreateTopology** function directly. Some BDA minidrivers must intercept this request, using an internal method ([KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)), rather than dispatch it directly. These mindrivers must obtain a pointer to the BDA filter from the passed IRP before calling **BdaMethodCreateTopology** so that they can use the filter to keep track of associated pins. These mindrivers can then send instructions to the hardware when connecting particular pin types. See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Configuring a BDA Filter](/windows-hardware/drivers/stream/configuring-a-bda-filter) for more information.

If a BDA minidriver must create the template topology between two filter pins without relying on the network provider, the BDA minidriver should call the [BdaCreateTopology](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatetopology) function.

## -see-also

[BdaCreateTopology](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacreatetopology)

[KSMETHOD](/windows-hardware/drivers/stream/ksmethod-structure)

[KSMETHODSETID_BdaDeviceConfiguration](/windows-hardware/drivers/stream/ksmethodsetid-bdadeviceconfiguration)

[KSMETHOD_BDA_CREATE_TOPOLOGY](/windows-hardware/drivers/stream/ksmethod-bda-create-topology)

[KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)
