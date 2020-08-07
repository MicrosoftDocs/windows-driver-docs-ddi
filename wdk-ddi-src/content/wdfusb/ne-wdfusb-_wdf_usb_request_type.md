---
UID: NE:wdfusb._WDF_USB_REQUEST_TYPE
title: _WDF_USB_REQUEST_TYPE (wdfusb.h)
description: The WDF_USB_REQUEST_TYPE enumeration identifies the types of USB requests that a framework-based driver can send to a USB I/O target.
old-location: wdf\wdf_usb_request_type.htm
tech.root: wdf
ms.assetid: 4d10cefb-1039-4c48-b9f7-c4a530a6514b
ms.date: 02/26/2018
keywords: ["WDF_USB_REQUEST_TYPE enumeration"]
ms.keywords: "*PWDF_USB_REQUEST_TYPE, DFUsbRef_b3c4cd6e-66ac-40b3-b78b-c550f14c3e94.xml, PWDF_USB_REQUEST_TYPE, PWDF_USB_REQUEST_TYPE enumeration pointer, WDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE enumeration, WdfUsbRequestTypeDeviceControlTransfer, WdfUsbRequestTypeDeviceString, WdfUsbRequestTypeDeviceUrb, WdfUsbRequestTypeInvalid, WdfUsbRequestTypeNoFormat, WdfUsbRequestTypePipeAbort, WdfUsbRequestTypePipeRead, WdfUsbRequestTypePipeReset, WdfUsbRequestTypePipeUrb, WdfUsbRequestTypePipeWrite, _WDF_USB_REQUEST_TYPE, kmdf.wdf_usb_request_type, wdf.wdf_usb_request_type, wdfusb/PWDF_USB_REQUEST_TYPE, wdfusb/WDF_USB_REQUEST_TYPE, wdfusb/WdfUsbRequestTypeDeviceControlTransfer, wdfusb/WdfUsbRequestTypeDeviceString, wdfusb/WdfUsbRequestTypeDeviceUrb, wdfusb/WdfUsbRequestTypeInvalid, wdfusb/WdfUsbRequestTypeNoFormat, wdfusb/WdfUsbRequestTypePipeAbort, wdfusb/WdfUsbRequestTypePipeRead, wdfusb/WdfUsbRequestTypePipeReset, wdfusb/WdfUsbRequestTypePipeUrb, wdfusb/WdfUsbRequestTypePipeWrite"
f1_keywords:
 - "wdfusb/WDF_USB_REQUEST_TYPE"
 - "WDF_USB_REQUEST_TYPE"
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfusb.h
api_name:
- WDF_USB_REQUEST_TYPE
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
---

# _WDF_USB_REQUEST_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_REQUEST_TYPE</b> enumeration identifies the types of USB requests that a framework-based driver can send to a USB I/O target.


## -enum-fields




### -field WdfUsbRequestTypeInvalid

For internal use only.


### -field WdfUsbRequestTypeNoFormat

This value is not used.


### -field WdfUsbRequestTypeDeviceString

A request to <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-devices">obtain a device's Unicode strings</a>.


### -field WdfUsbRequestTypeDeviceControlTransfer

A request to <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-devices">send a control transfer</a>.


### -field WdfUsbRequestTypeDeviceUrb

A request to <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-devices">send a URB to a device</a>.


### -field WdfUsbRequestTypePipeWrite

A request to <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-pipes">write to a pipe</a>.


### -field WdfUsbRequestTypePipeRead

A request to <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-pipes">read from a pipe</a>.


### -field WdfUsbRequestTypePipeAbort

A request to <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-pipes">stop a pipe</a>.


### -field WdfUsbRequestTypePipeReset

A request to <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-pipes">reset a pipe</a>.


### -field WdfUsbRequestTypePipeUrb

A request to <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-pipes">send a URB to a pipe</a>.


## -remarks



The <b>WDF_USB_REQUEST_TYPE</b> enumeration is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_request_completion_params">WDF_USB_REQUEST_COMPLETION_PARAMS</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_request_completion_params">WDF_USB_REQUEST_COMPLETION_PARAMS</a>
 

 

