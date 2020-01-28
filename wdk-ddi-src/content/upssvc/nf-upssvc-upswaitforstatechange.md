---
UID: NF:upssvc.UPSWaitForStateChange
title: UPSWaitForStateChange function (upssvc.h)
description: The UPSWaitForStateChange function waits until a specified UPS state changes, or until a time-out interval elapses.
old-location: battery\upswaitforstatechange.htm
tech.root: battery
ms.assetid: ac78dda4-6d14-441b-8e79-3245f7253875
ms.date: 02/15/2018
ms.keywords: UPSWaitForStateChange, UPSWaitForStateChange function [Battery Devices], UPS_fns_8921d5d9-c4d0-496f-b531-a697ac06da93.xml, battery.upswaitforstatechange, upssvc/UPSWaitForStateChange
f1_keywords:
 - "upssvc/UPSWaitForStateChange"
req.header: upssvc.h
req.include-header: Upssvc.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- upssvc.h
api_name:
- UPSWaitForStateChange
product:
- Windows
targetos: Windows
req.typenames: 
---

# UPSWaitForStateChange function


## -description


The <b>UPSWaitForStateChange</b> function waits until a specified UPS state changes, or until a time-out interval elapses.


## -parameters




### -param aCurrentState [in]

Specifies the UPS state on which to wait. When the state of the UPS system changes from the specified state to any other state, the function returns. The specified value can be one of the following:





#### UPS_ONLINE

Utility-supplied power is normal.



#### UPS_ONBATTERY

Utility-supplied power is inadequate, and the UPS batteries are discharging.



#### UPS_LOWBATTERY

Utility-supplied power is inadequate, and the UPS batteries are critically low.



#### UPS_NOCOMM

Communication with the UPS is not currently established.


### -param anInterval [in]

Specifies a time-out interval, in milliseconds, for the function. If the UPS state has not changed from the specified state when the interval elapses, the function returns. A value of INFINITE means the interval never elapses.


## -remarks



The <b>UPSWaitForStateChange</b> function must wait until either the state of the UPS changes from the value specified by <i>aCurrentState</i>, or until the time specified by <i>anInterval</i> has elapsed, whichever occurs first. 

A call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/upssvc/nf-upssvc-upscancelwait">UPSCancelWait</a> interrupts <b>UPSWaitForStateChange</b> and causes it to return. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/upssvc/nf-upssvc-upscancelwait">UPSCancelWait</a>
 

 

