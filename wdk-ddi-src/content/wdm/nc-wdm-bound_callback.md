---
UID: NC:wdm.BOUND_CALLBACK
title: BOUND_CALLBACK (wdm.h)
description: The BoundCallback routine is executed whenever the system issues a bounds exception for a user-mode thread.
old-location: kernel\boundcallback.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["BOUND_CALLBACK callback function"]
ms.keywords: BOUND_CALLBACK, BoundCallback, BoundCallback routine [Kernel-Mode Driver Architecture], kernel.boundcallback, wdm/BoundCallback
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - BOUND_CALLBACK
 - wdm/BOUND_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - BOUND_CALLBACK
---

# BOUND_CALLBACK callback function


## -description

The <i>BoundCallback</i> routine is executed whenever the system issues a bounds exception for a user-mode thread.

## -returns

A <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_bound_callback_status">BOUND_CALLBACK_STATUS</a> value that indicates how the bounds exception was processed by the callback function.

## -remarks

Drivers can supply a <i>BoundCallback</i> that is called when the system issues a bounds exception.

Use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterboundcallback">KeRegisterBoundCallback</a> to register a <i>BoundCallback</i> routine. A driver can subsequently remove the callback by using the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kederegisterboundcallback">KeDeregisterBoundCallback</a> routine. If the driver can be unloaded, it must remove any registered callbacks in its <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a> routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kederegisterboundcallback">KeDeregisterBoundCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterboundcallback">KeRegisterBoundCallback</a>

