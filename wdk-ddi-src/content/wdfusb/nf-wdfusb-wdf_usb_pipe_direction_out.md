---
UID: NF:wdfusb.WDF_USB_PIPE_DIRECTION_OUT
title: WDF_USB_PIPE_DIRECTION_OUT function
author: windows-driver-content
description: The WDF_USB_PIPE_DIRECTION_OUT function determines whether a specified USB endpoint is an output endpoint.
old-location: wdf\wdf_usb_pipe_direction_out.htm
old-project: wdf
ms.assetid: 404e1893-8ee2-429c-b7e3-e6d8d01eaa1c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfusb/WDF_USB_PIPE_DIRECTION_OUT, WDF_USB_PIPE_DIRECTION_OUT, WDF_USB_PIPE_DIRECTION_OUT function, wdf.wdf_usb_pipe_direction_out, kmdf.wdf_usb_pipe_direction_out, DFUsbRef_24f2180e-94da-4d77-9209-6bf97ea051a3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
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
req.lib: None
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	None
-	None.dll
apiname: 
-	WDF_USB_PIPE_DIRECTION_OUT
product: Windows
targetos: Windows
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_USB_PIPE_DIRECTION_OUT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_PIPE_DIRECTION_OUT</b> function determines whether a specified USB endpoint is an output endpoint.


## -syntax


````
BOOLEAN WDF_USB_PIPE_DIRECTION_OUT(
  _In_ UCHAR EndpointAddress
);
````


## -parameters




### -param EndpointAddress [in]

A USB endpoint address.


## -returns


<b>WDF_USB_PIPE_DIRECTION_OUT</b> returns <b>TRUE</b> if the specified endpoint is an output endpoint. Otherwise, this function returns <b>FALSE</b>.



## -remarks


The high bit of the endpoint address determines the direction (input or output) of an endpoint. For more information about endpoint addresses, see the USB specification.

For more information about the <b>WDF_USB_PIPE_DIRECTION_OUT</b> function and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeisoutendpoint.md">WdfUsbTargetPipeIsOutEndpoint</a>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_pipe_direction_in.md">WDF_USB_PIPE_DIRECTION_IN</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_PIPE_DIRECTION_OUT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

