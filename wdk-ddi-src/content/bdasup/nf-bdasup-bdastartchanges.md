---
UID: NF:bdasup.BdaStartChanges
title: BdaStartChanges function (bdasup.h)
description: The BdaStartChanges function initiates the setting of new BDA topology changes.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaStartChanges function"]
ms.keywords: BdaStartChanges, BdaStartChanges function [Streaming Media Devices], bdaref_16498957-566e-405d-b573-3a2eb75a6bcb.xml, bdasup/BdaStartChanges, stream.bdastartchanges
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
 - BdaStartChanges
 - bdasup/BdaStartChanges
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaStartChanges
---

## -description

The **BdaStartChanges** function initiates the setting of new BDA topology changes.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to initiate changes. The BDA minidriver receives this IRP with the [KSMETHOD_BDA_START_CHANGES](/windows-hardware/drivers/stream/ksmethod-bda-start-changes) request.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaStartChanges** function to initiate the setting of new BDA topology changes after the minidriver receives a [KSMETHOD_BDA_START_CHANGES](/windows-hardware/drivers/stream/ksmethod-bda-start-changes) request of the [KSMETHODSETID_BdaChangeSync](/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync) method set from the network provider. BDA minidrivers define dispatch and filter-automation tables so that those minidrivers either dispatch the **BdaStartChanges** function directly or intercept this request using an internal method ([KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)), which then calls the **BdaStartChanges** function. For example, BDA minidrivers that intercept this request can obtain a pointer to the BDA filter from the passed IRP so that they can subsequently reset pending filter resources to the new requirements and set the change state of the filter to BDA_CHANGES_COMPLETE. See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Changing BDA Filter Properties](/windows-hardware/drivers/stream/changing-bda-filter-properties) for more information.

Calling the **BdaStartChanges** function causes any previously requested topology changes that have not yet been committed to be ignored.

## -see-also

[BDA_CHANGE_STATE](/previous-versions/windows/hardware/drivers/ff556518(v=vs.85))

[BdaCommitChanges](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacommitchanges)

[KSMETHODSETID_BdaChangeSync](/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync)

[KSMETHOD_BDA_START_CHANGES](/windows-hardware/drivers/stream/ksmethod-bda-start-changes)

[KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)
