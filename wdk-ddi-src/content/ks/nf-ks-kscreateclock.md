---
UID: NF:ks.KsCreateClock
title: KsCreateClock function (ks.h)
description: The KsCreateClock function creates a handle to a clock instance.
old-location: stream\kscreateclock.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsCreateClock function"]
ms.keywords: KsCreateClock, KsCreateClock function [Streaming Media Devices], ks/KsCreateClock, ksfunc_ba840ce8-a1c9-4ede-8d2e-6e2829ad9b11.xml, stream.kscreateclock
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsCreateClock
 - ks/KsCreateClock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ks.lib
 - ks.dll
api_name:
 - KsCreateClock
---

# KsCreateClock function


## -description

The <b>KsCreateClock</b> function creates a handle to a clock instance.

## -parameters

### -param ConnectionHandle [in]


Specifies the handle to the connection on which to create the clock.

### -param ClockCreate [in]


Specifies clock create parameters. This currently consists of a flag that must be set to zero.

### -param ClockHandle [out]


Specifies the new clock handle.

## -returns

The <b>KsCreateClock</b> function returns STATUS_SUCCESS if successful, or it returns an error on clock creation failure.

