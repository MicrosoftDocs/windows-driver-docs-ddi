---
UID: NF:ks.KsGetDefaultClockTime
title: KsGetDefaultClockTime function (ks.h)
description: The KsGetDefaultClockTime function gets the current time of the clock.The function can be called at DISPATCH_LEVEL.
old-location: stream\ksgetdefaultclocktime.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsGetDefaultClockTime function"]
ms.keywords: KsGetDefaultClockTime, KsGetDefaultClockTime function [Streaming Media Devices], ks/KsGetDefaultClockTime, ksfunc_16bfafe4-e317-48e9-841f-f642eb1fb8d3.xml, stream.ksgetdefaultclocktime
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsGetDefaultClockTime
 - ks/KsGetDefaultClockTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsGetDefaultClockTime
---

# KsGetDefaultClockTime function


## -description

The <b>KsGetDefaultClockTime</b> function gets the current time of the clock.

The function can be called at DISPATCH_LEVEL.

## -parameters

### -param DefaultClock 

[in]
Specifies an initialize default clock structure that is shared among any instance of the default clock for the parent.

## -returns

The <b>KsGetDefaultClockTime</b> function returns the current clock time.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kssetdefaultclocktime">KsSetDefaultClockTime</a>
