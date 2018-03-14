---
UID: NS:usb._URB_CONTROL_FEATURE_REQUEST
title: "_URB_CONTROL_FEATURE_REQUEST"
author: windows-driver-content
description: The _URB_CONTROL_FEATURE_REQUEST structure is used by USB client drivers to set or clear features on a device, interface, or endpoint.
old-location: buses\_urb_control_feature_request.htm
old-project: usbref
ms.assetid: b32c6a7e-84c2-412a-a13e-959aaddc81ac
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "_URB_CONTROL_FEATURE_REQUEST, _URB_CONTROL_FEATURE_REQUEST structure [Buses], buses._urb_control_feature_request, usb/_URB_CONTROL_FEATURE_REQUEST, usbstrct_0552c436-5e4b-4573-b9ea-1f098de7dedd.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usb.h
api_name:
-	_URB_CONTROL_FEATURE_REQUEST
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# _URB_CONTROL_FEATURE_REQUEST structure


## -description


The <b>_URB_CONTROL_FEATURE_REQUEST</b> structure is used by USB client drivers  to set or clear features on a device, interface, or endpoint.


## -syntax


````
struct _URB_CONTROL_FEATURE_REQUEST {
  struct URB_HEADER  Hdr;
  PVOID               Reserved;
  ULONG               Reserved2;
  ULONG               Reserved3;
  PVOID               Reserved4;
  PMDL                Reserved5;
  struct URB  *UrbLink;
  struct URB_HCD_AREA  hca;
  USHORT              Reserved0;
  USHORT              FeatureSelector;
  USHORT              Index;
  USHORT              Reserved1;
};
````


## -struct-fields




### -field Hdr

Pointer to a <a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> indicates either a set or a clear feature operation, to perform on a device, interface, endpoint or other non-standard component. <b>Hdr.Function</b> must have one of the following values:

<b>Hdr.Length</b> must equal <code>sizeof(_URB_CONTROL_FEATURE_REQUEST)</code>.


### -field Reserved

Reserved. Do not use.


### -field Reserved2

Reserved. Do not use.


### -field Reserved3

Reserved. Do not use.


### -field Reserved4

Reserved. Do not use.


### -field Reserved5

Reserved. Do not use.


### -field UrbLink

Reserved. Do not use.


### -field hca

Reserved. Do not use.


### -field Reserved0

Reserved. Do not use.


### -field FeatureSelector

Specifies the USB-defined feature code to be cleared or set. Using a feature code that is invalid, cannot be set, or cannot be cleared will cause the target to stall. The bus driver will copy the value in the <b>FeatureSelector</b> member to the <b>wValue</b> field of the setup packet. 


### -field Index

Specifies the device-defined index, returned by a successful configuration request, if the request is for an endpoint or interface. Otherwise, <b>Index</b> must be zero. The bus driver will copy the value in the <b>Index</b> member to the <b>wIndex</b> field of the setup packet. 


### -field Reserved1

Reserved. Do not use.


## -remarks



Drivers can use the <b>UsbBuildFeatureRequest</b> service routine to format this URB. 

The reserved members of this structure must be treated as opaque and are reserved for system use.

When a driver arms a USB device for remote wakeup with an IRP_MN_WAIT_WAKE request, the USB bus driver automatically sets remote wakeup feature on the device. A control feature URB is not necessary.

Likewise, when a driver issues a URB with a function type of URB_FUNCTION_SYNC_RESET_PIPE_AND_CLEAR_STALL to a pipe, the bus driver will automatically clear the pipe's endpoint stall feature. The driver does not have to send a control feature URB to the pipe to clear the endpoint stall.




## -see-also

<a href="..\usb\ns-usb-_urb.md">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a>



 

 


