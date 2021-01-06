---
UID: NF:ks.KsReleaseControl
title: KsReleaseControl function (ks.h)
description: The KsReleaseControl function releases the control mutex for Object.
old-location: stream\ksreleasecontrol.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsReleaseControl function"]
ms.keywords: KsReleaseControl, KsReleaseControl function [Streaming Media Devices], avfunc_b568770e-1fe0-47d5-8fd4-ac210cd4be30.xml, ks/KsReleaseControl, stream.ksreleasecontrol
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsReleaseControl
 - ks/KsReleaseControl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsReleaseControl
---

# KsReleaseControl function


## -description

The<b> KsReleaseControl </b>function releases the control mutex for <i>Object</i>.

## -parameters

### -param Object 

[in]
The object for which to release the control mutex.

## -remarks

<i>Object</i> should be either a filter or a pin cast to PVOID.

Minidrivers typically do not call <b>KsReleaseControl</b> directly, but instead call <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterreleasecontrol">KsFilterReleaseControl</a> or <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinreleasecontrol">KsPinReleaseControl</a>. These versions automatically provide the necessary typecasting to PVOID.

For more information, see <a href="/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksacquirecontrol">KsAcquireControl</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilteracquirecontrol">KsFilterAcquireControl</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterreleasecontrol">KsFilterReleaseControl</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinacquirecontrol">KsPinAcquireControl</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinreleasecontrol">KsPinReleaseControl</a>
