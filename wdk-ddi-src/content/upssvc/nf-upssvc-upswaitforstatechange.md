---
UID: NF:upssvc.UPSWaitForStateChange
title: UPSWaitForStateChange function
author: windows-driver-content
description: The UPSWaitForStateChange function waits until a specified UPS state changes, or until a time-out interval elapses.
old-location: battery\upswaitforstatechange.htm
old-project: battery
ms.assetid: ac78dda4-6d14-441b-8e79-3245f7253875
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: UPSWaitForStateChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: upssvc.h
req.include-header: Upssvc.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UPSWaitForStateChange
req.alt-loc: upssvc.h
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
req.typenames: UMDETW_ALLOCATION_USAGE
req.product: Windows 10 or later.
---

# UPSWaitForStateChange function



## -description
The <b>UPSWaitForStateChange</b> function waits until a specified UPS state changes, or until a time-out interval elapses.



## -syntax

````
void UPSWaitForStateChange(
  _In_ DWORD aCurrentState,
  _In_ DWORD anInterval
);
````


## -parameters

### -param aCurrentState [in]

Specifies the UPS state on which to wait. When the state of the UPS system changes from the specified state to any other state, the function returns. The specified value can be one of the following:




### -param UPS_ONLINE 

Utility-supplied power is normal.


### -param UPS_ONBATTERY

Utility-supplied power is inadequate, and the UPS batteries are discharging.


### -param UPS_LOWBATTERY

Utility-supplied power is inadequate, and the UPS batteries are critically low.


### -param UPS_NOCOMM

Communication with the UPS is not currently established.

</dd>
</dl>

### -param anInterval [in]

Specifies a time-out interval, in milliseconds, for the function. If the UPS state has not changed from the specified state when the interval elapses, the function returns. A value of INFINITE means the interval never elapses.


## -returns
None


## -remarks
The <b>UPSWaitForStateChange</b> function must wait until either the state of the UPS changes from the value specified by <i>aCurrentState</i>, or until the time specified by <i>anInterval</i> has elapsed, whichever occurs first. 

A call to <a href="..\upssvc\nf-upssvc-upscancelwait.md">UPSCancelWait</a> interrupts <b>UPSWaitForStateChange</b> and causes it to return. 


## -see-also
<dl>
<dt>
<a href="..\upssvc\nf-upssvc-upscancelwait.md">UPSCancelWait</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [battery\battery]:%20UPSWaitForStateChange function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

