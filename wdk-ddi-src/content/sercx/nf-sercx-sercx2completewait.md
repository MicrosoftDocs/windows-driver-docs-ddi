---
UID: NF:sercx.SerCx2CompleteWait
title: SerCx2CompleteWait function (sercx.h)
description: The SerCx2CompleteWait method notifies version 2 of the serial framework extension (SerCx2) that an event in the current wait mask has occurred.
old-location: serports\sercx2completewait.htm
tech.root: serports
ms.assetid: 7A3DC90E-628C-4FFC-807D-8F23BDC97742
ms.date: 04/23/2018
ms.keywords: 2/SerCx2CompleteWait, SerCx2CompleteWait, SerCx2CompleteWait method [Serial Ports], serports.sercx2completewait
ms.topic: function
f1_keywords:
 - "sercx/SerCx2CompleteWait"
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- 2.0\Sercx.h
api_name:
- SerCx2CompleteWait
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCx2CompleteWait function


## -description


The <b>SerCx2CompleteWait</b> method notifies version 2 of the serial framework extension (SerCx2) that an event in the current wait mask has occurred.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>.


### -param Event [in]

The type of event that is ending the current wait operation. This parameter is a wait mask value. Each event type corresponds to a particular bit in the wait mask. This bit is set to indicate that the corresponding event has occurred. For more information about the types of events that can be specified by a wait mask, see <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>.


## -returns



None.




## -remarks



When SerCx2 receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a> request from a client, the request handler in SerCx2 calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_set_wait_mask">EvtSerCx2SetWaitMask</a> callback function to notify the serial controller driver that the wait mask has changed.

When an event in the new wait mask occurs, the driver calls <b>SerCx2CompleteWait</b> to notify SerCx2 of the event. If a previously sent <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_wait_on_mask">IOCTL_SERIAL_WAIT_ON_MASK</a> request is pending in SerCx2 at the time of the <b>SerCx2CompleteWait</b> call, SerCx2 completes this request with an output wait mask that indicates which event occurred. Otherwise, SerCx2 stores the event in its internal event history in anticipation of a future <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_waitmask">EvtSerCxWaitmask</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_wait_on_mask">IOCTL_SERIAL_WAIT_ON_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>
 

 

