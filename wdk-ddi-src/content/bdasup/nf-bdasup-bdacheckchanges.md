---
UID: NF:bdasup.BdaCheckChanges
title: BdaCheckChanges function (bdasup.h)
description: The BdaCheckChanges function verifies a new set of BDA topology changes before they are committed.
old-location: stream\bdacheckchanges.htm
tech.root: stream
ms.assetid: 4831e13b-19e7-458c-a392-a135d43fc989
ms.date: 04/23/2018
keywords: ["BdaCheckChanges function"]
ms.keywords: BdaCheckChanges, BdaCheckChanges function [Streaming Media Devices], bdaref_d60c7f03-8188-4be5-807c-e21384429341.xml, bdasup/BdaCheckChanges, stream.bdacheckchanges
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

# BdaCheckChanges function


## -description

The <b>BdaCheckChanges</b> function verifies a new set of BDA topology changes before they are committed.

## -parameters

### -param pIrp

#### - Irp [in]

Points to the IRP for the request to verify changes. The BDA minidriver receives this IRP with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-check-changes">KSMETHOD_BDA_CHECK_CHANGES</a> request.

## -returns

Returns STATUS_SUCCESS or an appropriate error code. Returns the result that the <b>BdaCommitChanges</b> function would have returned.

## -remarks

A BDA minidriver calls the <b>BdaCheckChanges</b> function to verify a group of BDA topology changes after the minidriver receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-check-changes">KSMETHOD_BDA_CHECK_CHANGES</a> request of the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync">KSMETHODSETID_BdaChangeSync</a> method set from the network provider. BDA minidrivers define dispatch and filter-automation tables so that those minidrivers either dispatch the <b>BdaCheckChanges</b> function directly or intercept this request using an internal method (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler">KStrMethodHandler</a>), which then calls the <b>BdaCheckChanges</b> function. For example, BDA minidrivers that intercept this request can obtain a pointer to the BDA filter from the passed IRP so that they can validate the new list of resources for the filter. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/defining-automation-tables">Defining Automation Tables</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/changing-bda-filter-properties">Changing BDA Filter Properties</a> for more information.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacommitchanges">BdaCommitChanges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync">KSMETHODSETID_BdaChangeSync</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-check-changes">KSMETHOD_BDA_CHECK_CHANGES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler">KStrMethodHandler</a>

