---
UID: NF:ks.KsPinReleaseProcessingMutex
title: KsPinReleaseProcessingMutex function (ks.h)
description: The KsPinReleaseProcessingMutex function releases the processing mutex for the AVStream pin specified by Pin.
old-location: stream\kspinreleaseprocessingmutex.htm
tech.root: stream
ms.assetid: 9a117c5b-26a4-4fdb-b51e-933b8f105a81
ms.date: 04/23/2018
keywords: ["KsPinReleaseProcessingMutex function"]
ms.keywords: KsPinReleaseProcessingMutex, KsPinReleaseProcessingMutex function [Streaming Media Devices], avfunc_22421ea0-8973-4921-a0cb-f1d824f76357.xml, ks/KsPinReleaseProcessingMutex, stream.kspinreleaseprocessingmutex
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
 - KsPinReleaseProcessingMutex
 - ks/KsPinReleaseProcessingMutex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsPinReleaseProcessingMutex
---

# KsPinReleaseProcessingMutex function


## -description

The<b> KsPinReleaseProcessingMutex </b>function releases the processing mutex for the AVStream pin specified by <i>Pin</i>.

## -parameters

### -param Pin 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure representing the AVStream pin object for which to acquire the processing mutex.

## -remarks

Minidrivers that must suspend processing for a long time should not use this mutex to do so. Instead, directly manipulate the processing control gate using the <b>KSGATE</b><i>Xxx</i> functions. See links to these functions in <a href="/windows-hardware/drivers/stream/flow-control-gates-in-avstream">Flow Control Gates in AVStream</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinacquireprocessingmutex">KsPinAcquireProcessingMutex</a>