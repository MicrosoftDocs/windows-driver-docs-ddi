---
UID: NF:ks.KsFilterGetAndGate
title: KsFilterGetAndGate function (ks.h)
description: The KsFilterGetAndGate function returns Filter's AND gate.
old-location: stream\ksfiltergetandgate.htm
tech.root: stream
ms.assetid: b5f7c4ed-0596-4e88-b987-fd454e4b4971
ms.date: 04/23/2018
keywords: ["KsFilterGetAndGate function"]
ms.keywords: KsFilterGetAndGate, KsFilterGetAndGate function [Streaming Media Devices], avfunc_58886874-f3f3-4e2d-a69c-e85260dcc702.xml, ks/KsFilterGetAndGate, stream.ksfiltergetandgate
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsFilterGetAndGate
 - ks/KsFilterGetAndGate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsFilterGetAndGate
---

# KsFilterGetAndGate function


## -description

The<b> KsFilterGetAndGate </b>function returns <i>Filter</i>'s AND gate.

## -parameters

### -param Filter 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure for which to acquire the corresponding AND gate.

## -returns

<b>KsFilterGetAndGate</b> returns <i>Filter</i>'s AND gate as a pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a> structure.

## -remarks

A minidriver can use AND gates on a filter as a processing control mechanism for that filter.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgatecapturethreshold">KsGateCaptureThreshold</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputoff">KsGateTurnInputOff</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputon">KsGateTurnInputOn</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinattachandgate">KsPinAttachAndGate</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspingetandgate">KsPinGetAndGate</a>