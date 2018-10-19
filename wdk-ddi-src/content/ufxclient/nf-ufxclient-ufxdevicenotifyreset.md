---
UID: NF:ufxclient.UfxDeviceNotifyReset
title: UfxDeviceNotifyReset function
author: windows-driver-content
description: Notifies UFX about a USB bus reset event.
old-location: buses\ufxdevicenotifyreset.htm
tech.root: usbref
ms.assetid: FD88E645-7CBB-4998-BEBA-5BBE2FF167FC
ms.date: 05/07/2018
ms.keywords: UfxDeviceNotifyReset, UfxDeviceNotifyReset method [Buses], buses.ufxdevicenotifyreset, ufxclient/UfxDeviceNotifyReset
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.lib: ufxstub.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ufxclient.h
api_name:
-	UfxDeviceNotifyReset
product:
- Windows
targetos: Windows
req.typenames: 
---

# UfxDeviceNotifyReset function


## -description


Notifies UFX about a USB bus reset event.


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


### -param DeviceSpeed [in]

Contains a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff539294">USB_DEVICE_SPEED</a> that indicates the speed of the device.


## -returns



This method does not return a value.




## -remarks



The client driver calls <b>UfxDeviceNotifyReset</b> when it receives a bus reset event. All non-default endpoints should be disabled and the default endpoint should be reset.  The device moves to the default state.

The client driver typically calls <b>UfxDeviceNotifyReset</b> from its <a href="https://msdn.microsoft.com/d2d505e0-aeac-4871-8c60-d026b2833043">EvtInterruptDpc</a> callback function.  The following example shows how to handle a reset event.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
VOID
HandleUsbConnect (
    WDFDEVICE WdfDevice
    )
/*++

Routine Description:

    Handles a connect event from the controller.

Arguments:

    WDfDevice - WDFDEVICE object representing the controller.

--*/
{
    PCONTROLLER_CONTEXT ControllerContext;
    USB_DEVICE_SPEED DeviceSpeed;

    TraceEntry();

    ControllerContext = DeviceGetControllerContext(WdfDevice);

    //
    // Read the device speed.
    //

    //
    // #### TODO: Add code to read device speed from the controller ####
    //
    
    // Sample will assume SuperSpeed operation for illustration purposes
    DeviceSpeed = UsbSuperSpeed;
    
    //
    // #### TODO: Add any code needed to configure the controller after connect has occurred ####
    //


    ControllerContext-&gt;Speed = DeviceSpeed;
    TraceInformation("Connected Speed is %d!", DeviceSpeed);

    //
    // Notify UFX about reset, which will take care of updating 
    // Max Packet Size for EP0 by calling descriptor update.
    //
    UfxDeviceNotifyReset(ControllerContext-&gt;UfxDevice, DeviceSpeed);

    ControllerContext-&gt;Connect = TRUE;

    TraceExit();
}</pre>
</td>
</tr>
</table></span></div>


