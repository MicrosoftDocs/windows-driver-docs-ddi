---
UID: NC:udecxwdfdevice.EVT_UDECX_WDF_DEVICE_RESET
title: EVT_UDECX_WDF_DEVICE_RESET
author: windows-driver-content
description: The UDE client driver's implementation to reset the emulated host controller or the devices attached to it.
old-location: buses\evt_udecx_wdf_device_reset.htm
old-project: usbref
ms.assetid: 394343A5-10E4-4F64-AD3C-1D2114422B39
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.evt_udecx_wdf_device_reset, EvtUdecxWdfDeviceReset callback function [Buses], EvtUdecxWdfDeviceReset, EVT_UDECX_WDF_DEVICE_RESET, EVT_UDECX_WDF_DEVICE_RESET, udecxwdfdevice/EvtUdecxWdfDeviceReset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: udecxwdfdevice.h
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
-	UdecxWdfDevice.h
apiname:
-	EvtUdecxWdfDeviceReset
product: Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_CALLBACKS, *PUDECX_USB_ENDPOINT_CALLBACKS
req.product: Windows 10 or later.
---

# EVT_UDECX_WDF_DEVICE_RESET callback


## -description


The UDE client driver's implementation to reset the emulated host controller or the devices attached to it.


## -prototype


````
EVT_UDECX_WDF_DEVICE_RESET EvtUdecxWdfDeviceReset;

void EvtUdecxWdfDeviceReset(
  _In_ WDFDEVICE UdecxWdfDevice
)
{ ... }
````


## -parameters




### -param UdecxWdfDevice [in]

A handle to a framework device object that represents the controller. The client driver initialized this object in the previous call to <a href="..\udecxwdfdevice\nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation.md">UdecxWdfDeviceAddUsbDeviceEmulation</a>.


## -returns



This callback function does not return a value.




## -remarks



The USB device emulation  class extension (UdeCx) invokes this callback function to notify the client driver that it must handle a reset request including resetting all downstream devices attached to the emulated host controller.
This call is asynchronous. The client driver signals completion with status information by calling <a href="..\udecxwdfdevice\nf-udecxwdfdevice-udecxwdfdeviceresetcomplete.md">UdecxWdfDeviceResetComplete</a>.
If the client specified <b>UdeWdfDeviceResetActionResetEachUsbDevice</b> in <a href="..\udecxwdfdevice\ns-udecxwdfdevice-_udecx_wdf_device_config.md">UDECX_WDF_DEVICE_CONFIG</a> (during the <a href="..\udecxwdfdevice\nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation.md">UdecxWdfDeviceAddUsbDeviceEmulation</a> call), this callback is never used. Instead, each connected attached device receives an <i>EVT_UDECX_WDF_DEVICE_RESET</i> callback.





## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UDECX_WDF_DEVICE_RESET callback function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

