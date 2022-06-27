---
UID: NF:bdasup.BdaCommitChanges
title: BdaCommitChanges function (bdasup.h)
description: The BdaCommitChanges function commits the changes to BDA topology that have occurred since the last call to the BdaStartChanges function.
tech.root: stream
ms.date: 04/25/2022
keywords: ["BdaCommitChanges function"]
ms.keywords: BdaCommitChanges, BdaCommitChanges function [Streaming Media Devices], bdaref_41fbbc81-4461-47a2-ba7a-725b696329f3.xml, bdasup/BdaCommitChanges, stream.bdacommitchanges
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems.
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
 - BdaCommitChanges
 - bdasup/BdaCommitChanges
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaCommitChanges
---

## -description

The **BdaCommitChanges** function commits the changes to BDA topology that have occurred since the last call to the **BdaStartChanges** function.

## -parameters

### -param pIrp [in]

Points to the IRP for the request to commit changes. The BDA minidriver receives this IRP with the [KSMETHOD_BDA_COMMIT_CHANGES](/windows-hardware/drivers/stream/ksmethod-bda-commit-changes) request.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the **BdaCommitChanges** function to commit a set of BDA topology changes after the minidriver receives a [KSMETHOD_BDA_COMMIT_CHANGES](/windows-hardware/drivers/stream/ksmethod-bda-commit-changes) request of the [KSMETHODSETID_BdaChangeSync](/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync) method set from the network provider. BDA minidrivers define dispatch and filter-automation tables so that those minidrivers either dispatch the **BdaCommitChanges** function directly or intercept this request using an internal method ([KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)), which then calls the **BdaCommitChanges** function. For example, BDA minidrivers that intercept this request can obtain a pointer to the BDA filter from the passed IRP so that they can:

- Set the new list of resources for the filter to the pending list of resources.

- Set the change state of the filter to BDA_CHANGES_COMPLETE.

- Commit the resources on the underlying device.

See [Defining Automation Tables](/windows-hardware/drivers/stream/defining-automation-tables) and [Changing BDA Filter Properties](/windows-hardware/drivers/stream/changing-bda-filter-properties) for more information.

## -see-also

[BDA_CHANGE_STATE](/previous-versions/windows/hardware/drivers/ff556518(v=vs.85))

[BdaCheckChanges](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacheckchanges)

[BdaStartChanges](/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdastartchanges)

[KSMETHODSETID_BdaChangeSync](/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync)

[KSMETHOD_BDA_COMMIT_CHANGES](/windows-hardware/drivers/stream/ksmethod-bda-commit-changes)

[KStrMethodHandler](/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler)
