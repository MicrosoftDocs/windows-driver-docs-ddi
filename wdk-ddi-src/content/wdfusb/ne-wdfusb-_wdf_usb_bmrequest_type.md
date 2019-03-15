---
UID: NE:wdfusb._WDF_USB_BMREQUEST_TYPE
title: _WDF_USB_BMREQUEST_TYPE (wdfusb.h)
description: The WDF_USB_BMREQUEST_TYPE enumeration identifies the data transfer type for a USB control transfer.
old-location: wdf\wdf_usb_bmrequest_type.htm
tech.root: wdf
ms.assetid: c20e7aec-32e7-401d-8c40-aa6ac191e857
ms.date: 02/26/2018
ms.keywords: BmRequestClass, BmRequestStandard, BmRequestVendor, DFUsbRef_01dc6407-8fa2-462a-848c-2a8fc53ef50b.xml, WDF_USB_BMREQUEST_TYPE, WDF_USB_BMREQUEST_TYPE enumeration, _WDF_USB_BMREQUEST_TYPE, kmdf.wdf_usb_bmrequest_type, wdf.wdf_usb_bmrequest_type, wdfusb/BmRequestClass, wdfusb/BmRequestStandard, wdfusb/BmRequestVendor, wdfusb/WDF_USB_BMREQUEST_TYPE
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfusb.h
api_name:
- WDF_USB_BMREQUEST_TYPE
product:
- Windows
targetos: Windows
req.typenames: WDF_USB_BMREQUEST_TYPE
---

# _WDF_USB_BMREQUEST_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_BMREQUEST_TYPE</b> enumeration identifies the data transfer type for a USB control transfer. 


## -enum-fields




### -field BmRequestStandard

The data transfer is a standard USB control transfer.


### -field BmRequestClass

The data transfer is a device class-specific USB control transfer.


### -field BmRequestVendor

The data transfer is a vendor-specific USB control transfer.


## -remarks



The <b>WDF_USB_BMREQUEST_TYPE</b> enumeration is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

For more information about data transfer types for a USB control transfer, see the USB specification.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a>
 

 

