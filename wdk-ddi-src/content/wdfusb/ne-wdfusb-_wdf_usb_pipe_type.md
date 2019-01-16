---
UID: NE:wdfusb._WDF_USB_PIPE_TYPE
title: "_WDF_USB_PIPE_TYPE"
description: The WDF_USB_PIPE_TYPE enumeration identifies the types of USB pipes.
old-location: wdf\wdf_usb_pipe_type.htm
tech.root: wdf
ms.assetid: ae230ff0-4fd9-417b-8ee0-80e3ca5a30ff
ms.date: 02/26/2018
ms.keywords: DFUsbRef_6a3da4b3-f8ac-4208-bdd2-1136a6417b3a.xml, WDF_USB_PIPE_TYPE, WDF_USB_PIPE_TYPE enumeration, WdfUsbPipeTypeBulk, WdfUsbPipeTypeControl, WdfUsbPipeTypeInterrupt, WdfUsbPipeTypeInvalid, WdfUsbPipeTypeIsochronous, _WDF_USB_PIPE_TYPE, kmdf.wdf_usb_pipe_type, wdf.wdf_usb_pipe_type, wdfusb/WDF_USB_PIPE_TYPE, wdfusb/WdfUsbPipeTypeBulk, wdfusb/WdfUsbPipeTypeControl, wdfusb/WdfUsbPipeTypeInterrupt, wdfusb/WdfUsbPipeTypeInvalid, wdfusb/WdfUsbPipeTypeIsochronous
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfusb.h
api_name:
-	WDF_USB_PIPE_TYPE
product:
- Windows
targetos: Windows
req.typenames: WDF_USB_PIPE_TYPE
---

# _WDF_USB_PIPE_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_PIPE_TYPE</b> enumeration identifies the types of USB pipes.


## -enum-fields




### -field WdfUsbPipeTypeInvalid

Reserved for internal use.


### -field WdfUsbPipeTypeControl

The pipe is a control pipe.


### -field WdfUsbPipeTypeIsochronous

The pipe is an isochronous pipe. 


### -field WdfUsbPipeTypeBulk

The pipe is a bulk pipe.


### -field WdfUsbPipeTypeInterrupt

The pipe is an interrupt pipe.


## -remarks



The <b>WDF_USB_PIPE_TYPE</b> enumeration is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553037">WDF_USB_PIPE_INFORMATION</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553037">WDF_USB_PIPE_INFORMATION</a>
 

 

