---
UID: NF:ks.KsAcquireControl
title: KsAcquireControl function (ks.h)
description: The KsAcquireControl function acquires the filter control mutex for Object.
old-location: stream\ksacquirecontrol.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsAcquireControl function"]
ms.keywords: KsAcquireControl, KsAcquireControl function [Streaming Media Devices], avfunc_a3c1eb2c-db95-463f-98f5-a158dd1e14f5.xml, ks/KsAcquireControl, stream.ksacquirecontrol
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
 - KsAcquireControl
 - ks/KsAcquireControl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsAcquireControl
---

# KsAcquireControl function


## -description

The <b>KsAcquireControl</b> function acquires the filter control mutex for <i>Object</i>.

## -parameters

### -param Object [in]


A pointer to the object for which to acquire the filter control mutex. This should be a pointer to either a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> or a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>, cast to PVOID.

## -remarks

Minidrivers typically do not call this function directly, but instead call either <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilteracquirecontrol">KsFilterAcquireControl</a> or <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinacquirecontrol">KsPinAcquireControl</a>. These functions provide the necessary typecasting to PVOID automatically.

For more information, see <a href="/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilteracquirecontrol">KsFilterAcquireControl</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinacquirecontrol">KsPinAcquireControl</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksreleasecontrol">KsReleaseControl</a>
