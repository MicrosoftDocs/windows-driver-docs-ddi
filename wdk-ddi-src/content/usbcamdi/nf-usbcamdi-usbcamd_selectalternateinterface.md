---
UID: NF:usbcamdi.USBCAMD_SelectAlternateInterface
title: USBCAMD_SelectAlternateInterface function
author: windows-driver-content
description: The USBCAMD_SelectAlternateInterface function selects an alternate setting within the USB video streaming interface.
old-location: stream\usbcamd_selectalternateinterface.htm
old-project: stream
ms.assetid: b9a31719-2674-4d3f-8792-b099640faa07
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , A, B, C, D, I, M, S, U, USBCAMD_SelectAlternateInterface, USBCAMD_SelectAlternateInterface function [Streaming Media Devices], _, a, c, e, f, l, n, r, stream.usbcamd_selectalternateinterface, t, usbcamdi/USBCAMD_SelectAlternateInterface, usbcmdpr_48a3328b-869a-42fd-acfd-b1981384db85.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
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
req.lib: Usbcamd2.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	usbcamd2.lib
-	usbcamd2.dll
apiname:
-	USBCAMD_SelectAlternateInterface
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# USBCAMD_SelectAlternateInterface function


## -description


The <b>USBCAMD_SelectAlternateInterface</b> function selects an alternate setting within the USB video streaming interface.


## -syntax


````
NTSTATUS USBCAMD_SelectAlternateInterface(
  _In_    PVOID                       DeviceContext,
  _Inout_ PUSBD_INTERFACE_INFORMATION RequestInterface
);
````


## -parameters




### -param DeviceContext [in]

Pointer to a device-specific context.


### -param RequestInterface [in, out]

Pointer to a <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structure initialized with the proper values for a SELECT_INTERFACE URB request. This interface structure corresponds to a single isochronous interface on the device.


## -returns



<b>USBCAMD_SelectAlternateInterface </b>returns the status of the SELECT_INTERFACE USB bus driver request. Other possible error codes include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_DATA_ERROR</b></dt>
</dl>
</td>
<td width="60%">
USBCAMD failed to cancel outstanding bulk/interrupt IRPs.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There are insufficient resources to allocate the USB request block

</td>
</tr>
</table>
 




## -remarks



On successful completion, the structure pointed to by the <i>RequestInterface</i> argument is filled in with the information from the SELECT_INTERFACE USB bus driver request.

This function is typically called by a camera minidriver in response to a request to allocate or free bandwidth. This function should not be called when any video streams in the minidriver are open and/or actively streaming data.




## -see-also

<a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_SelectAlternateInterface function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

