---
UID: NF:ks.KsGateCaptureThreshold
title: KsGateCaptureThreshold function (ks.h)
description: The KsGateCaptureThreshold function is used to capture an ON input of an AND gate specified by Gate.
old-location: stream\ksgatecapturethreshold.htm
tech.root: stream
ms.assetid: 24a7745d-28f8-4f5a-9f51-37ad2d0ffa0b
ms.date: 04/23/2018
keywords: ["KsGateCaptureThreshold function"]
ms.keywords: KsGateCaptureThreshold, KsGateCaptureThreshold function [Streaming Media Devices], avfunc_9fd4ddfc-f715-45da-936e-9527b8ec4a25.xml, ks/KsGateCaptureThreshold, stream.ksgatecapturethreshold
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: 
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - KsGateCaptureThreshold
 - ks/KsGateCaptureThreshold
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsGateCaptureThreshold
---

# KsGateCaptureThreshold function


## -description

The<b> KsGateCaptureThreshold</b> function is used to capture an ON input of an AND gate specified by <i>Gate</i>.

## -parameters

### -param Gate 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a> structure representing the AND gate for which to capture an ON input synchronously.

## -returns

<b>KsGateCaptureThreshold</b> returns <b>TRUE</b> if the AND gate was originally open. Note that returning <b>TRUE</b> implies that the gate was closed so that no other thread could simultaneously capture the gate and commence processing.

## -remarks

<b>KsGateCaptureThreshold</b> checks the state of the given AND gate. If the gate is open, it turns off an input to the gate, thereby transitioning the gate to a closed state. If the gate is closed, the function does nothing. Unlike <b>KsGateGetStateUnsafe</b>, this call is done synchronously with respect to other gate state changes. It is the primary synchronization mechanism for processing based on gate control.

Despite its name, this function is only a valid call for AND gates, not gates in general. AVStream, however, does not verify whether <i>Gate</i> is an AND gate or an OR gate. It is the caller's responsibility to ensure that the call is only made on AND gates.

The call is made using interlocked functions and is thus synchronous with respect to any of the other gate state change functions; it is also a very efficient method of process control.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoffinputtoand">KsGateAddOffInputToAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoffinputtoor">KsGateAddOffInputToOr</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoninputtoand">KsGateAddOnInputToAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoninputtoor">KsGateAddOnInputToOr</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgategetstateunsafe">KsGateGetStateUnsafe</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateinitializeand">KsGateInitializeAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateinitializeor">KsGateInitializeOr</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoffinputfromand">KsGateRemoveOffInputFromAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoffinputfromor">KsGateRemoveOffInputFromOr</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoninputfromand">KsGateRemoveOnInputFromAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoninputfromor">KsGateRemoveOnInputFromOr</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputoff">KsGateTurnInputOff</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputon">KsGateTurnInputOn</a>