---
UID: NF:wdfusb.WDF_USB_PIPE_DIRECTION_OUT
title: WDF_USB_PIPE_DIRECTION_OUT function (wdfusb.h)
description: The WDF_USB_PIPE_DIRECTION_OUT function determines whether a specified USB endpoint is an output endpoint.
old-location: wdf\wdf_usb_pipe_direction_out.htm
tech.root: wdf
ms.assetid: 404e1893-8ee2-429c-b7e3-e6d8d01eaa1c
ms.date: 02/26/2018
ms.keywords: DFUsbRef_24f2180e-94da-4d77-9209-6bf97ea051a3.xml, WDF_USB_PIPE_DIRECTION_OUT, WDF_USB_PIPE_DIRECTION_OUT function, kmdf.wdf_usb_pipe_direction_out, wdf.wdf_usb_pipe_direction_out, wdfusb/WDF_USB_PIPE_DIRECTION_OUT
ms.topic: function
f1_keywords:
 - "wdfusb/WDF_USB_PIPE_DIRECTION_OUT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- None
- None.dll
api_name:
- WDF_USB_PIPE_DIRECTION_OUT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_USB_PIPE_DIRECTION_OUT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_PIPE_DIRECTION_OUT</b> function determines whether a specified USB endpoint is an output endpoint.


## -parameters




### -param EndpointAddress [in]

A USB endpoint address.


## -returns



<b>WDF_USB_PIPE_DIRECTION_OUT</b> returns <b>TRUE</b> if the specified endpoint is an output endpoint. Otherwise, this function returns <b>FALSE</b>.




## -remarks



The high bit of the endpoint address determines the direction (input or output) of an endpoint. For more information about endpoint addresses, see the USB specification.

For more information about the <b>WDF_USB_PIPE_DIRECTION_OUT</b> function and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdf_usb_pipe_direction_in">WDF_USB_PIPE_DIRECTION_IN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetpipeisoutendpoint">WdfUsbTargetPipeIsOutEndpoint</a>
 

 

