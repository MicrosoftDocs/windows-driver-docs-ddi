---
UID: NE:wdfusb._WDF_USB_REQUEST_TYPE
title: "_WDF_USB_REQUEST_TYPE"
author: windows-driver-content
description: The WDF_USB_REQUEST_TYPE enumeration identifies the types of USB requests that a framework-based driver can send to a USB I/O target.
old-location: wdf\wdf_usb_request_type.htm
old-project: wdf
ms.assetid: 4d10cefb-1039-4c48-b9f7-c4a530a6514b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_USB_REQUEST_TYPE, DFUsbRef_b3c4cd6e-66ac-40b3-b78b-c550f14c3e94.xml, PWDF_USB_REQUEST_TYPE, PWDF_USB_REQUEST_TYPE enumeration pointer, WDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE enumeration, WdfUsbRequestTypeDeviceControlTransfer, WdfUsbRequestTypeDeviceString, WdfUsbRequestTypeDeviceUrb, WdfUsbRequestTypeInvalid, WdfUsbRequestTypeNoFormat, WdfUsbRequestTypePipeAbort, WdfUsbRequestTypePipeRead, WdfUsbRequestTypePipeReset, WdfUsbRequestTypePipeUrb, WdfUsbRequestTypePipeWrite, _WDF_USB_REQUEST_TYPE, kmdf.wdf_usb_request_type, wdf.wdf_usb_request_type, wdfusb/PWDF_USB_REQUEST_TYPE, wdfusb/WDF_USB_REQUEST_TYPE, wdfusb/WdfUsbRequestTypeDeviceControlTransfer, wdfusb/WdfUsbRequestTypeDeviceString, wdfusb/WdfUsbRequestTypeDeviceUrb, wdfusb/WdfUsbRequestTypeInvalid, wdfusb/WdfUsbRequestTypeNoFormat, wdfusb/WdfUsbRequestTypePipeAbort, wdfusb/WdfUsbRequestTypePipeRead, wdfusb/WdfUsbRequestTypePipeReset, wdfusb/WdfUsbRequestTypePipeUrb, wdfusb/WdfUsbRequestTypePipeWrite"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: "<=DISPATCH_LEVEL  (See Remarks section.)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfusb.h
api_name:
-	WDF_USB_REQUEST_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# _WDF_USB_REQUEST_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_REQUEST_TYPE</b> enumeration identifies the types of USB requests that a framework-based driver can send to a USB I/O target.


## -enum-fields




### -field WdfUsbRequestTypeInvalid

For internal use only.


### -field WdfUsbRequestTypeNoFormat

This value is not used.


### -field WdfUsbRequestTypeDeviceString

A request to <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-devices">obtain a device's Unicode strings</a>.


### -field WdfUsbRequestTypeDeviceControlTransfer

A request to <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-devices">send a control transfer</a>.


### -field WdfUsbRequestTypeDeviceUrb

A request to <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-devices">send a URB to a device</a>.


### -field WdfUsbRequestTypePipeWrite

A request to <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-pipes">write to a pipe</a>.


### -field WdfUsbRequestTypePipeRead

A request to <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-pipes">read from a pipe</a>.


### -field WdfUsbRequestTypePipeAbort

A request to <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-pipes">stop a pipe</a>.


### -field WdfUsbRequestTypePipeReset

A request to <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-pipes">reset a pipe</a>.


### -field WdfUsbRequestTypePipeUrb

A request to <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-pipes">send a URB to a pipe</a>.


## -remarks



The <b>WDF_USB_REQUEST_TYPE</b> enumeration is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553049">WDF_USB_REQUEST_COMPLETION_PARAMS</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553049">WDF_USB_REQUEST_COMPLETION_PARAMS</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_REQUEST_TYPE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

