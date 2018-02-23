---
UID: NE:wdfusb._WDF_USB_REQUEST_TYPE
title: "_WDF_USB_REQUEST_TYPE"
author: windows-driver-content
description: The WDF_USB_REQUEST_TYPE enumeration identifies the types of USB requests that a framework-based driver can send to a USB I/O target.
old-location: wdf\wdf_usb_request_type.htm
old-project: wdf
ms.assetid: 4d10cefb-1039-4c48-b9f7-c4a530a6514b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfUsbRequestTypePipeWrite, wdfusb/WDF_USB_REQUEST_TYPE, WdfUsbRequestTypePipeRead, WdfUsbRequestTypePipeUrb, wdf.wdf_usb_request_type, wdfusb/WdfUsbRequestTypePipeUrb, *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE, PWDF_USB_REQUEST_TYPE, WdfUsbRequestTypeNoFormat, DFUsbRef_b3c4cd6e-66ac-40b3-b78b-c550f14c3e94.xml, PWDF_USB_REQUEST_TYPE enumeration pointer, wdfusb/PWDF_USB_REQUEST_TYPE, WdfUsbRequestTypeInvalid, wdfusb/WdfUsbRequestTypePipeReset, wdfusb/WdfUsbRequestTypePipeWrite, WdfUsbRequestTypeDeviceControlTransfer, wdfusb/WdfUsbRequestTypePipeRead, wdfusb/WdfUsbRequestTypePipeAbort, wdfusb/WdfUsbRequestTypeDeviceControlTransfer, wdfusb/WdfUsbRequestTypeInvalid, WdfUsbRequestTypePipeReset, WDF_USB_REQUEST_TYPE enumeration, kmdf.wdf_usb_request_type, WdfUsbRequestTypePipeAbort, wdfusb/WdfUsbRequestTypeDeviceUrb, _WDF_USB_REQUEST_TYPE, wdfusb/WdfUsbRequestTypeDeviceString, wdfusb/WdfUsbRequestTypeNoFormat, WdfUsbRequestTypeDeviceUrb, WdfUsbRequestTypeDeviceString
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfusb.h
apiname:
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


## -syntax


````
typedef enum _WDF_USB_REQUEST_TYPE { 
  WdfUsbRequestTypeInvalid                = 0,
  WdfUsbRequestTypeNoFormat               = 1,
  WdfUsbRequestTypeDeviceString           = 2,
  WdfUsbRequestTypeDeviceControlTransfer  = 3,
  WdfUsbRequestTypeDeviceUrb              = 4,
  WdfUsbRequestTypePipeWrite              = 5,
  WdfUsbRequestTypePipeRead               = 6,
  WdfUsbRequestTypePipeAbort              = 7,
  WdfUsbRequestTypePipeReset              = 8,
  WdfUsbRequestTypePipeUrb                = 9
} WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE;
````


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



The <b>WDF_USB_REQUEST_TYPE</b> enumeration is used in the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_request_completion_params.md">WDF_USB_REQUEST_COMPLETION_PARAMS</a> structure.




## -see-also

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_request_completion_params.md">WDF_USB_REQUEST_COMPLETION_PARAMS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_REQUEST_TYPE enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

