---
UID: NF:wdfusb.WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS
title: WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS function (wdfusb.h)
description: The WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS function initializes a WDF_USB_CONTROL_SETUP_PACKET structure for a device class-specific USB control transfer.
old-location: wdf\wdf_usb_control_setup_packet_init_class.htm
tech.root: wdf
ms.assetid: c44e16f1-2ecd-4dad-b3c3-c6b6a3dcbb84
ms.date: 02/26/2018
ms.keywords: DFUsbRef_840aad44-522b-426d-ad95-457dee6c44dd.xml, WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS, WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS function, kmdf.wdf_usb_control_setup_packet_init_class, wdf.wdf_usb_control_setup_packet_init_class, wdfusb/WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS
ms.topic: function
f1_keywords:
 - "wdfusb/WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS"
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
- WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure for a device class-specific USB control transfer.


## -parameters




### -param Packet [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param Direction [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ne-wdfusb-_wdf_usb_bmrequest_direction">WDF_USB_BMREQUEST_DIRECTION</a>-typed value that is stored in the <b>Packet.bm.Request.Dir</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure. 


### -param Recipient [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ne-wdfusb-_wdf_usb_bmrequest_recipient">WDF_USB_BMREQUEST_RECIPIENT</a>-typed value that is stored in the <b>Packet.bm.Request.Recipient</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure. 


### -param Request [in]

A request type constant that is stored in the<b>Packet.bRequest</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param Value [in]

A request-specific value that is stored in the <b>Packet.wValue.Value</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param Index [in]

A request-specific index value that is stored in the <b>Packet.wIndex.Value</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


## -remarks



The <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</b> function does the following:

<ol>
<li>
Zeros the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

</li>
<li>
Sets the <b>Packet.bm.Request.Type</b> member to <b>BmRequestClass</b>.

</li>
<li>
Sets other structure members by using the <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</b> function's input arguments.

</li>
</ol>
To initialize a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure, the driver should call one of the following functions:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init">WDF_USB_CONTROL_SETUP_PACKET_INIT</a>


</li>
<li>
<b>WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</b>

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init_feature">WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init_get_status">WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init_vendor">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>


</li>
</ul>

#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

```cpp
WDF_USB_CONTROL_SETUP_PACKET  packet;
WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS(
                                        &packet,
                                        BMREQUEST_HOST_TO_DEVICE,
                                        BMREQUEST_TO_DEVICE,
                                        0,
                                        0,
                                        0
                                        );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ne-wdfusb-_wdf_usb_bmrequest_direction">WDF_USB_BMREQUEST_DIRECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ne-wdfusb-_wdf_usb_bmrequest_recipient">WDF_USB_BMREQUEST_RECIPIENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init">WDF_USB_CONTROL_SETUP_PACKET_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init_feature">WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init_get_status">WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init_vendor">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>
 

 

