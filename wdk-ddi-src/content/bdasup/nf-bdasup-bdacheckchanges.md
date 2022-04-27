---
UID: NF:bdasup.BdaCheckChanges
title: BdaCheckChanges function (bdasup.h)
description: The BdaCheckChanges function verifies a new set of BDA topology changes before they are committed.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaCheckChanges function"]
ms.keywords: BdaCheckChanges, BdaCheckChanges function [Streaming Media Devices], bdaref_d60c7f03-8188-4be5-807c-e21384429341.xml, bdasup/BdaCheckChanges, stream.bdacheckchanges
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
 - BdaCheckChanges
 - bdasup/BdaCheckChanges
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaCheckChanges
---

## -description

The **BdaCheckChanges** function verifies a new set of BDA topology changes before they are committed.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to verify changes. The BDA minidriver receives this IRP with the [KSMETHOD_BDA_CHECK_CHANGES](/windows-hardware/drivers/stream/ksmethod-bda-check-changes) request.

## -returns

Returns STATUS_SUCCESS or an appropriate error code. Returns the result that the **BdaCommitChanges** function would have returned.

## -remarks

A BDA minidriver calls the **BdaCheckChanges** function to verify a group of BDA topology changes after the minidriver receives a [KSMETHOD_BDA_CHECK_CHANGES](/windows-hardware/drivers/stream/ksmethod-bda-check-changes) request of the [KSMETHODSETID_BdaChangeSync](/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync) method set from the network provider. BDA minidrivers define dispatch and filter-automation tables so that those minidrivers either dispatch the **BdaCheckChanges** function directly or intercept this request using an internal method ([KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)), which then calls the **BdaCheckChanges** function. For example, BDA minidrivers that intercept this request can obtain a pointer to the BDA filter from the passed IRP so that they can validate the new list of resources for the filter. See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Changing BDA Filter Properties](/windows-hardware/drivers/stream/changing-bda-filter-properties) for more information.

## -see-also

[BdaCommitChanges](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacommitchanges)

[KSMETHODSETID_BdaChangeSync](/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync)

[KSMETHOD_BDA_CHECK_CHANGES](/windows-hardware/drivers/stream/ksmethod-bda-check-changes)

[KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)
