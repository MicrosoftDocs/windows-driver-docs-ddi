---
UID: NF:ks.KsGetDevice
title: KsGetDevice function (ks.h)
description: The KsGetDevice function returns the AVStream device structure to which Object belongs.
old-location: stream\ksgetdevice.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsGetDevice function"]
ms.keywords: KsGetDevice, KsGetDevice function [Streaming Media Devices], avfunc_8459c499-365e-4cd4-927c-b359792937b0.xml, ks/KsGetDevice, stream.ksgetdevice
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
 - KsGetDevice
 - ks/KsGetDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsGetDevice
---

# KsGetDevice function


## -description

The<b> KsGetDevice</b> function returns the AVStream device structure to which <i>Object </i>belongs.

## -parameters

### -param Object [in]


The object to query for the device to which it belongs.

## -returns

<b>KsGetDevice</b> returns a pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> structure that is the AVStream device to which <i>Object</i> belongs.

## -remarks

<i>Object</i> should be one of: PKSPIN, PKSFILTER, or PKSFILTERFACTORY. Callers must perform appropriate typecasting to PVOID.

Minidrivers typically do not call this function directly. There are a number of functions that perform inline calls to <b>KsGetDevice</b> and that perform typecasting automatically: <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetdevice">KsFilterFactoryGetDevice</a>, <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetdevice">KsFilterGetDevice</a>, and <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspingetdevice">KsPinGetDevice</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetdevice">KsFilterFactoryGetDevice</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetdevice">KsFilterGetDevice</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspingetdevice">KsPinGetDevice</a>
