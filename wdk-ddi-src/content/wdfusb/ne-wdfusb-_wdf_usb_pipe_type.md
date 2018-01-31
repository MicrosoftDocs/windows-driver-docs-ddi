---
UID: NE:wdfusb._WDF_USB_PIPE_TYPE
title: "_WDF_USB_PIPE_TYPE"
author: windows-driver-content
description: The WDF_USB_PIPE_TYPE enumeration identifies the types of USB pipes.
old-location: wdf\wdf_usb_pipe_type.htm
old-project: wdf
ms.assetid: ae230ff0-4fd9-417b-8ee0-80e3ca5a30ff
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdf_usb_pipe_type, WdfUsbPipeTypeInterrupt, WdfUsbPipeTypeIsochronous, WDF_USB_PIPE_TYPE enumeration, wdfusb/WdfUsbPipeTypeIsochronous, _WDF_USB_PIPE_TYPE, wdfusb/WdfUsbPipeTypeControl, wdfusb/WdfUsbPipeTypeInterrupt, wdf.wdf_usb_pipe_type, wdfusb/WdfUsbPipeTypeBulk, wdfusb/WDF_USB_PIPE_TYPE, WdfUsbPipeTypeInvalid, WdfUsbPipeTypeBulk, DFUsbRef_6a3da4b3-f8ac-4208-bdd2-1136a6417b3a.xml, wdfusb/WdfUsbPipeTypeInvalid, WdfUsbPipeTypeControl, WDF_USB_PIPE_TYPE
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
-	WDF_USB_PIPE_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_USB_PIPE_TYPE
req.product: Windows 10 or later.
---

# _WDF_USB_PIPE_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_PIPE_TYPE</b> enumeration identifies the types of USB pipes.


## -syntax


````
typedef enum _WDF_USB_PIPE_TYPE { 
  WdfUsbPipeTypeInvalid      = 0,
  WdfUsbPipeTypeControl      = 1,
  WdfUsbPipeTypeIsochronous  = 2,
  WdfUsbPipeTypeBulk         = 3,
  WdfUsbPipeTypeInterrupt    = 4
} WDF_USB_PIPE_TYPE;
````


## -enum-fields




#### - WdfUsbPipeTypeInvalid

Reserved for internal use.


#### - WdfUsbPipeTypeControl

The pipe is a control pipe.


#### - WdfUsbPipeTypeIsochronous

The pipe is an isochronous pipe. 


#### - WdfUsbPipeTypeBulk

The pipe is a bulk pipe.


#### - WdfUsbPipeTypeInterrupt

The pipe is an interrupt pipe.


## -remarks


The <b>WDF_USB_PIPE_TYPE</b> enumeration is used in the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a> structure.



## -see-also

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_PIPE_TYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

