---
UID: NF:udecxusbdevice.UDECX_USB_DEVICE_CALLBACKS_INIT
title: UDECX_USB_DEVICE_CALLBACKS_INIT function
author: windows-driver-content
description: Initializes a UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS structure before a UdecxUsbDeviceCreate call.
old-location: buses\udecx_usb_device_callbacks_init.htm
old-project: usbref
ms.assetid: ACBF5E07-9F36-4DF9-B72B-1BF159CE27A7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UDECX_USB_DEVICE_CALLBACKS_INIT, UDECX_USB_DEVICE_CALLBACKS_INIT method [Buses], buses.udecx_usb_device_callbacks_init, udecxusbdevice/UDECX_USB_DEVICE_CALLBACKS_INIT
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UDECX_USB_DEVICE_CALLBACKS_INIT
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---

# UDECX_USB_DEVICE_CALLBACKS_INIT function


## -description


Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt628003">UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS</a> structure before a <a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a> call.


## -parameters




### -param Callbacks [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt628003">UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS</a> structure to initialize.


## -returns



This method does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a>
 

 

