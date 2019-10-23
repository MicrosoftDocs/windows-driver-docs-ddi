---
UID: NE:wdfusb._WDF_USB_BMREQUEST_DIRECTION
title: _WDF_USB_BMREQUEST_DIRECTION (wdfusb.h)
description: The WDF_USB_BMREQUEST_DIRECTION enumeration identifies the data transfer direction for a USB control transfer.
old-location: wdf\wdf_usb_bmrequest_direction.htm
tech.root: wdf
ms.assetid: e39748b8-d84c-4f9e-a790-bff192a6769c
ms.date: 02/26/2018
ms.keywords: BmRequestDeviceToHost, BmRequestHostToDevice, DFUsbRef_c758891d-14e3-4034-8e95-b896470437fd.xml, WDF_USB_BMREQUEST_DIRECTION, WDF_USB_BMREQUEST_DIRECTION enumeration, _WDF_USB_BMREQUEST_DIRECTION, kmdf.wdf_usb_bmrequest_direction, wdf.wdf_usb_bmrequest_direction, wdfusb/BmRequestDeviceToHost, wdfusb/BmRequestHostToDevice, wdfusb/WDF_USB_BMREQUEST_DIRECTION
ms.topic: enum
f1_keywords:
 - "wdfusb/WDF_USB_BMREQUEST_DIRECTION"
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
- WDF_USB_BMREQUEST_DIRECTION
product:
- Windows
targetos: Windows
req.typenames: WDF_USB_BMREQUEST_DIRECTION
---

# _WDF_USB_BMREQUEST_DIRECTION enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_BMREQUEST_DIRECTION</b> enumeration identifies the data transfer direction for a USB control transfer. 


## -enum-fields




### -field BmRequestHostToDevice

The data transfer direction is from the host system to the device.


### -field BmRequestDeviceToHost

The data transfer direction is from the device to the host system.


## -remarks



The <b>WDF_USB_BMREQUEST_DIRECTION</b> enumeration is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

For more information about the data transfer direction for a USB control transfer, see the USB specification.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a>
 

 

