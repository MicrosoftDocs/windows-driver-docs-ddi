---
UID: NF:ks.KsPinAttemptProcessing
title: KsPinAttemptProcessing function (ks.h)
description: The KsPinAttemptProcessing function is used to resume processing on a specific pin on a pin-centric filter. It attempts to initiate processing on Pin by sending a processing dispatch call to Pin's processing object.
tech.root: stream
ms.date: 11/16/2022
keywords: ["KsPinAttemptProcessing function"]
ms.keywords: KsPinAttemptProcessing, KsPinAttemptProcessing function [Streaming Media Devices], avfunc_e17d5ad8-b0e3-4b5e-ab4c-a552f1650ed4.xml, ks/KsPinAttemptProcessing, stream.kspinattemptprocessing
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL (See Remarks)
targetos: Windows
req.typenames: 
f1_keywords:
 - KsPinAttemptProcessing
 - ks/KsPinAttemptProcessing
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsPinAttemptProcessing
---

## -description

The KsPinAttemptProcessing function is used to resume processing on a specific pin on a pin-centric filter. It attempts to initiate processing on *Pin* by sending a processing dispatch call to *Pin*'s processing object.

## -parameters

### -param Pin [in]

A pointer to a [KSPIN](./ns-ks-_kspin.md) structure that represents the AVStream pin object on which to attempt processing.

> [!WARNING]
> This parameter is mandatory. If you call KsPinAttemptProcessing with a *Pin* value of **NULL**, system instability may result.

### -param Asynchronous [in]

This parameter indicates the minidriver's preference whether the processing should occur synchronously or asynchronously. If **TRUE**, processing is always asynchronous. However, synchronous processing only happens under certain circumstances. For more information, see the Remarks section below.

## -remarks

A minidriver may need to call KsPinAttemptProcessing to resume processing in various situations. For example, if the client has shut off the processing control gate with [KsGateTurnInputOff](./nf-ks-ksgateturninputoff.md), call this function when ready to attempt processing. Note that this only causes a processing dispatch if the process control gate is in the open state. Another situation involves the minidriver having previously returning STATUS_PENDING to a processing dispatch. For more details, see [Restarting Processing in AVStream](/windows-hardware/drivers/stream/restarting-processing-in-avstream) and [Flow Control Gates in AVStream](/windows-hardware/drivers/stream/flow-control-gates-in-avstream).

The processing dispatch occurs either synchronously or asynchronously, and *only* if the processing control gate is open. The *Asynchronous* flag specifies the minidriver's preference. If the minidriver requests an asynchronous process dispatch, the dispatch is always asynchronous. However, even if the caller sets *Asynchronous* to **FALSE**, a synchronous dispatch only occurs if the system is currently running at an IRQL less than the maximum processing IRQL. In other words, if the minidriver does not specify dispatch level processing and the call is made at IRQL = DISPATCH_LEVEL, then the call occurs in an asynchronous work item at PASSIVE_LEVEL regardless of the value of *Asynchronous*. For more information, see [Filter-Centric Processing](/windows-hardware/drivers/stream/filter-centric-processing) and [Pin-Centric Processing](/windows-hardware/drivers/stream/pin-centric-processing).

## -see-also

[**KSFILTER_DISPATCH**](./ns-ks-_ksfilter_dispatch.md)

[KsFilterAttemptProcessing](./nf-ks-ksfilterattemptprocessing.md)

[KsGateCaptureThreshold](./nf-ks-ksgatecapturethreshold.md)