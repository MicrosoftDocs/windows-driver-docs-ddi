---
UID: NC:wdm.BOUND_CALLBACK
title: BOUND_CALLBACK (wdm.h)
description: The BoundCallback routine is executed whenever the system issues a bounds exception for a user-mode thread.
old-location: kernel\boundcallback.htm
tech.root: kernel
ms.assetid: D9047BB2-2FCD-41DE-B1E1-DE89AAA40ED7
ms.date: 04/30/2018
ms.keywords: BOUND_CALLBACK, BoundCallback, BoundCallback routine [Kernel-Mode Driver Architecture], kernel.boundcallback, wdm/BoundCallback
ms.topic: callback
f1_keywords:
 - "wdm/BoundCallback"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- BoundCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# BOUND_CALLBACK callback function


## -description


The <i>BoundCallback</i> routine is executed whenever the system issues a bounds exception for a user-mode thread.


## -returns



A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_bound_callback_status">BOUND_CALLBACK_STATUS</a> value that indicates how the bounds exception was processed by the callback function. 




## -remarks



Drivers can supply a <i>BoundCallback</i> that is called when the system issues a bounds exception.

Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterboundcallback">KeRegisterBoundCallback</a> to register a <i>BoundCallback</i> routine. A driver can subsequently remove the callback by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kederegisterboundcallback">KeDeregisterBoundCallback</a> routine. If the driver can be unloaded, it must remove any registered callbacks in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a> routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kederegisterboundcallback">KeDeregisterBoundCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterboundcallback">KeRegisterBoundCallback</a>
 

 

