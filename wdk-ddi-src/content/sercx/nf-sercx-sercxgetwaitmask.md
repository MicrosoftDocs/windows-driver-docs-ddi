---
UID: NF:sercx.SerCxGetWaitMask
title: SerCxGetWaitMask function
author: windows-driver-content
description: The SerCxGetWaitMask method returns the event wait mask for the wait operation that is currently pending.
old-location: serports\sercxgetwaitmask.htm
old-project: serports
ms.assetid: 57A8E522-D787-4663-B2E3-46E8430388B7
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1/SerCxGetWaitMask, SerCxGetWaitMask, SerCxGetWaitMask method [Serial Ports], serports.sercxgetwaitmask
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	1.0\Sercx.h
api_name:
-	SerCxGetWaitMask
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCxGetWaitMask function


## -description


The <b>SerCxGetWaitMask</b> method returns the event wait mask for the wait operation that is currently pending.


## -syntax


````
ULONG SerCxGetWaitMask(
  [in] WDFDEVICE Device
);
````


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


## -returns



<b>SerCxGetWaitMask</b> returns a wait mask that specifies the events that a client (application or peripheral driver)  selected to trigger completion of the wait operation that is currently pending. If no wait operation is pending, this method returns the null wait mask, 0x0000. For more information, see the following Remarks section.




## -remarks



The serial controller driver calls <b>SerCxGetWaitMask</b> to obtain the wait mask to use for a pending wait operation. Typically, the controller driver calls this method from the <a href="..\sercx\nc-sercx-evt_sercx_waitmask.md">EvtSerCxWaitmask</a> callback function.

The wait mask indicates the types of events that can trigger completion of a wait operation. Each bit in the wait mask represents a particular type of event. A bit is set in the wait mask if the corresponding event will trigger completion of a wait operation. For more information about the meaning of the bits in the wait mask, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>



<a href="..\ntddser\ni-ntddser-ioctl_serial_wait_on_mask.md">IOCTL_SERIAL_WAIT_ON_MASK</a>



<a href="..\sercx\nc-sercx-evt_sercx_waitmask.md">EvtSerCxWaitmask</a>



 

 


