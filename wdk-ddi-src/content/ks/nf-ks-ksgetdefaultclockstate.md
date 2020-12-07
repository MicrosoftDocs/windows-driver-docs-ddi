---
UID: NF:ks.KsGetDefaultClockState
title: KsGetDefaultClockState function (ks.h)
description: The KsGetDefaultClockState function gets the current state of the clock.The function can be called at DISPATCH_LEVEL.
old-location: stream\ksgetdefaultclockstate.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsGetDefaultClockState function"]
ms.keywords: KsGetDefaultClockState, KsGetDefaultClockState function [Streaming Media Devices], ks/KsGetDefaultClockState, ksfunc_9b1067e9-8d12-42a5-969e-0ec6205f12e2.xml, stream.ksgetdefaultclockstate
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
 - KsGetDefaultClockState
 - ks/KsGetDefaultClockState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsGetDefaultClockState
---

# KsGetDefaultClockState function


## -description

The <b>KsGetDefaultClockState</b> function gets the current state of the clock.

The function can be called at DISPATCH_LEVEL.

## -parameters

### -param DefaultClock 

[in]
Specifies an initialized, default clock structure that is shared among any instance of the default clock for the parent.

## -returns

The <b>KsGetDefaultClockState</b> function returns the current clock state.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kssetdefaultclockstate">KsSetDefaultClockState</a>
