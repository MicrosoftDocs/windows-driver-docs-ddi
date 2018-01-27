---
UID: NF:udecxusbdevice.UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT
title: UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT function
author: windows-driver-content
description: Initializes a UDECX_USB_DEVICE_PLUG_IN_OPTIONS structure.
old-location: buses\udecx_usb_device_plug_in_options_init.htm
old-project: usbref
ms.assetid: 3188E2EE-E011-476D-9DDC-1DF61ECF9413
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT, buses.udecx_usb_device_plug_in_options_init, UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT function [Buses], udecxusbdevice/UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Udecxstub.lib
-	Udecxstub.dll
apiname: 
-	UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---

# UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT function


## -description


Initializes a <a href="..\udecxusbdevice\ns-udecxusbdevice-_udecx_usb_device_plug_in_options.md">UDECX_USB_DEVICE_PLUG_IN_OPTIONS</a> structure.


## -syntax


````
FORCEINLINE void UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT(
  _Out_ PUDECX_USB_DEVICE_PLUG_IN_OPTIONS Options
);
````


## -parameters




### -param Options [out]

A pointer to a <a href="..\udecxusbdevice\ns-udecxusbdevice-_udecx_usb_device_plug_in_options.md">UDECX_USB_DEVICE_PLUG_IN_OPTIONS</a> structure to initialize.


## -returns


This function does not return a value.



## -remarks


The method initializes <b>Usb20PortNumber</b> and <b>Usb30PortNumber</b>  to 0. This indicates a request for  automatic port number selection.



## -see-also

<a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceplugin.md">UdecxUsbDevicePlugIn</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

