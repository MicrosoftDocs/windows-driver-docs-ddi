---
UID: NF:ks.KsFreeDefaultClock
title: KsFreeDefaultClock function (ks.h)
description: The KsFreeDefaultClock function frees a default clock structure previously allocated with KsAllocateDefaultClock, taking into account any currently running timer DPCs.
old-location: stream\ksfreedefaultclock.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsFreeDefaultClock function"]
ms.keywords: KsFreeDefaultClock, KsFreeDefaultClock function [Streaming Media Devices], ks/KsFreeDefaultClock, ksfunc_30a51e64-775e-4412-9a8c-b186e6caf932.xml, stream.ksfreedefaultclock
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
 - KsFreeDefaultClock
 - ks/KsFreeDefaultClock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsFreeDefaultClock
---

# KsFreeDefaultClock function


## -description

The <b>KsFreeDefaultClock</b> function frees a default clock structure previously allocated with <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksallocatedefaultclock">KsAllocateDefaultClock</a>, taking into account any currently running timer DPCs. This assumes that all instances of the clock have been closed. This may actually just decrement the internal reference counter and allow a pending DPC to free the structure asynchronously.

This may only be called at PASSIVE_LEVEL.

## -parameters

### -param DefaultClock 

[in]
Specifies the previously allocated structure to free.

## -returns

None
