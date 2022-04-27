---
UID: NF:bdasup.BdaGetChangeState
title: BdaGetChangeState function (bdasup.h)
description: The BdaGetChangeState function returns the current change state of BDA topology.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaGetChangeState function"]
ms.keywords: BdaGetChangeState, BdaGetChangeState function [Streaming Media Devices], bdaref_52b39183-4a62-47b2-91d1-41fb76b31606.xml, bdasup/BdaGetChangeState, stream.bdagetchangestate
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
 - BdaGetChangeState
 - bdasup/BdaGetChangeState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaGetChangeState
---

## -description

The **BdaGetChangeState** function returns the current change state of BDA topology.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to get the current change state. The BDA minidriver receives this IRP with the [KSMETHOD_BDA_GET_CHANGE_STATE](/windows-hardware/drivers/stream/ksmethod-bda-get-change-state) request.

### -param pChangeState [out, optional]

Points to a variable that receives the current change state of BDA topology. The BDA change state can be one of the following values from the [BDA_CHANGE_STATE](/previous-versions/windows/hardware/drivers/ff556518(v=vs.85)) enumerated type:

| Value | Description |
|--|--|
| BDA_CHANGES_COMPLETE | BDA topology changes are complete. |
| BDA_CHANGES_PENDING | BDA topology changes are pending. |

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaGetChangeState** function to retrieve the current change state of BDA topology after the minidriver receives a [KSMETHOD_BDA_GET_CHANGE_STATE](/windows-hardware/drivers/stream/ksmethod-bda-get-change-state) request of the [KSMETHODSETID_BdaChangeSync](/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync) method set from the network provider. BDA minidrivers define dispatch and filter-automation tables so that those minidrivers either dispatch the **BdaGetChangeState** function directly or intercept this request using an internal method ([KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)), which then calls the **BdaGetChangeState** function. For example, BDA minidrivers that intercept this request can obtain a pointer to the BDA filter from the passed IRP so that they can:

- Not only check for pending topology changes but also for pending changes on the filter.

- Return the current change state for both BDA topology and the BDA filter.

See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Changing BDA Filter Properties](/windows-hardware/drivers/stream/changing-bda-filter-properties) for more information.

## -see-also

[BDA_CHANGE_STATE](/previous-versions/windows/hardware/drivers/ff556518(v=vs.85))

[KSMETHODSETID_BdaChangeSync](/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync)

[KSMETHOD_BDA_GET_CHANGE_STATE](/windows-hardware/drivers/stream/ksmethod-bda-get-change-state)

[KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)
