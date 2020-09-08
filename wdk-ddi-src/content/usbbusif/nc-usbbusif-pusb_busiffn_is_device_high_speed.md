---
UID: NC:usbbusif.PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED
title: PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED (usbbusif.h)
description: The USB_BUSIFFN_IS_DEVICE_HIGH_SPEED routine returns TRUE if the device is operating at high speed.
old-location: buses\isdevicehighspeed.htm
tech.root: usbref
ms.assetid: 36e0041d-700f-44db-84b6-3745026cb6f7
ms.date: 05/07/2018
keywords: ["PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED callback function"]
ms.keywords: IsDeviceHighSpeed, IsDeviceHighSpeed callback function [Buses], PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED, USB_BUSIFFN_IS_DEVICE_HIGH_SPEED, USB_BUSIFFN_IS_DEVICE_HIGH_SPEED callback, buses.isdevicehighspeed, usbbusif/IsDeviceHighSpeed, usbinterKR_eaf122ed-eee1-4924-a186-b0474b8c9816.xml
req.header: usbbusif.h
req.include-header: Usbbusif.h
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
req.irql: < = DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED
 - usbbusif/PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbbusif.h
api_name:
 - IsDeviceHighSpeed
---

# PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED callback function


## -description

The USB_BUSIFFN_IS_DEVICE_HIGH_SPEED routine returns <b>TRUE</b> if the device  is operating at high speed.

## -parameters

#### - BusContext [in, optional]

Handle returned in the <b>BusContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbbusif/ns-usbbusif-_usb_bus_interface_usbdi_v1">USB_BUS_INTERFACE_USBDI_V1</a> structure by an IRP_MN_QUERY_INTERFACE request.

## -returns

            USB_BUSIFFN_IS_DEVICE_HIGH_SPEED implementation returns <b>TRUE</b> if the USB device is operating at high speed USB 2.0 compliant device; <b>FALSE</b> otherwise.

## -remarks

The function definition that is provided on this reference page is an example routine whose parameters are just placeholder names. The actual prototype of the function is declared in usbbusif.h as follows:

<pre class="syntax" xml:space="preserve"><code>typedef BOOLEAN
  (USB_BUSIFFN *PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED) (
    IN PVOID
  );</code></pre>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbbusif/ns-usbbusif-_usb_bus_interface_usbdi_v1">USB_BUS_INTERFACE_USBDI_V1</a>

