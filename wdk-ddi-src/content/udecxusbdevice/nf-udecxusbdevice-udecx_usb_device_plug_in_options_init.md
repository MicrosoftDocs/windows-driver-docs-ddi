---
UID: NF:udecxusbdevice.UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT
title: UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT function
author: windows-driver-content
description: Initializes a UDECX_USB_DEVICE_PLUG_IN_OPTIONS structure.
old-location: buses\udecx_usb_device_plug_in_options_init.htm
tech.root: usbref
ms.assetid: 3188E2EE-E011-476D-9DDC-1DF61ECF9413
ms.date: 5/7/2018
ms.keywords: UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT, UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT function [Buses], buses.udecx_usb_device_plug_in_options_init, udecxusbdevice/UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT function


## -description


Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt627998">UDECX_USB_DEVICE_PLUG_IN_OPTIONS</a> structure.


## -parameters




### -param Options [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt627998">UDECX_USB_DEVICE_PLUG_IN_OPTIONS</a> structure to initialize.


## -returns



This function does not return a value.




## -remarks



The method initializes <b>Usb20PortNumber</b> and <b>Usb30PortNumber</b>  to 0. This indicates a request for  automatic port number selection.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt627975">UdecxUsbDevicePlugIn</a>
 

 

