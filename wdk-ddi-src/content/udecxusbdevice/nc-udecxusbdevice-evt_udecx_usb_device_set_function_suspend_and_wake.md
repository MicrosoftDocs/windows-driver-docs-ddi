---
UID: NC:udecxusbdevice.EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE
title: EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE
author: windows-driver-content
description: The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to change the function state of the specified interface of the virtual USB 3.0 device.
old-location: buses\evt_udecx_usb_device_set_function_suspend_and_wake.htm
old-project: UsbRef
ms.assetid: 54484E17-AA96-4152-B672-94C29E53F352
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE, EvtUsbDeviceSetFunctionSuspendAndWake, EvtUsbDeviceSetFunctionSuspendAndWake callback function [Buses], buses.evt_udecx_usb_device_set_function_suspend_and_wake, udecxusbdevice/EvtUsbDeviceSetFunctionSuspendAndWake
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	udecxusbdevice.h
apiname:
-	EvtUsbDeviceSetFunctionSuspendAndWake
product: Windows
targetos: Windows
req.typenames: USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH
req.product: Windows 10 or later.
---

# EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE callback


## -description


The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to change the function state of  the specified interface of the virtual USB 3.0 device.


## -prototype


````
EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE EvtUsbDeviceSetFunctionSuspendAndWake;

NTSTATUS EvtUsbDeviceSetFunctionSuspendAndWake(
  _In_ WDFDEVICE                       UdecxWdfDevice,
  _In_ UDECXUSBDEVICE                  UdecxUsbDevice,
  _In_ ULONG                           Interface,
  _In_ UDECX_USB_DEVICE_FUNCTION_POWER FunctionPower
)
{ ... }
````


## -parameters




### -param UdecxWdfDevice [in]

A handle to a framework device object that represents the controller to which the USB device is attached. The client driver initialized this object in a previous call to <a href="..\udecxwdfdevice\nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation.md">UdecxWdfDeviceAddUsbDeviceEmulation</a>.


### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver created this object in a previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>.


### -param Interface [in]

This value is the <b>bInterfaceNumber</b> of the interface that is waking up. 


### -param FunctionPower [in]

A <a href="..\udecxusbdevice\ne-udecxusbdevice-_udecx_usb_device_function_power.md">UDECX_USB_DEVICE_FUNCTION_POWER</a>-type value that indicates whether the interface can suspend and send wake signal to the host controller.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE.




## -remarks



The client driver registered the function in a previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks.md">UdecxUsbDeviceInitSetStateChangeCallbacks</a> by supplying a function pointer to its implementation.

In the callback implementation, the client driver for the USB device is expected to perform steps to enter working state. 

This event callback function applies to USB 3.0+ devices. UdeCx invokes this function to notify the client driver of a request to change the power state of a particular function. It also informs the driver whether or not the  function can wake from the new state.

The power request may be completed asynchronously by returning STATUS_PENDING, and then later completing it by calling <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicesetfunctionsuspendandwakecomplete.md">UdecxUsbDeviceSetFunctionSuspendAndWakeComplete</a> with the actual completion code.





## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

