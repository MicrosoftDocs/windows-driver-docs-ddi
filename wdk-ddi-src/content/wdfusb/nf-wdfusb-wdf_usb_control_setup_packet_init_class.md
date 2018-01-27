---
UID: NF:wdfusb.WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS
title: WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS function
author: windows-driver-content
description: The WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS function initializes a WDF_USB_CONTROL_SETUP_PACKET structure for a device class-specific USB control transfer.
old-location: wdf\wdf_usb_control_setup_packet_init_class.htm
old-project: wdf
ms.assetid: c44e16f1-2ecd-4dad-b3c3-c6b6a3dcbb84
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS, WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS function, wdfusb/WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS, kmdf.wdf_usb_control_setup_packet_init_class, wdf.wdf_usb_control_setup_packet_init_class, DFUsbRef_840aad44-522b-426d-ad95-457dee6c44dd.xml
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	wdfusb.h
apiname: 
-	WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS
product: Windows
targetos: Windows
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</b> function initializes a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure for a device class-specific USB control transfer.


## -syntax


````
VOID WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS(
  _Out_ PWDF_USB_CONTROL_SETUP_PACKET Packet,
  _In_  WDF_USB_BMREQUEST_DIRECTION   Direction,
  _In_  WDF_USB_BMREQUEST_RECIPIENT   Recipient,
  _In_  BYTE                          Request,
  _In_  USHORT                        Value,
  _In_  USHORT                        Index
);
````


## -parameters




### -param Packet [out]

A pointer to a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param Direction [in]

A <a href="..\wdfusb\ne-wdfusb-_wdf_usb_bmrequest_direction.md">WDF_USB_BMREQUEST_DIRECTION</a>-typed value that is stored in the <b>Packet.bm.Request.Dir</b> member of the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure. 


### -param Recipient [in]

A <a href="..\wdfusb\ne-wdfusb-_wdf_usb_bmrequest_recipient.md">WDF_USB_BMREQUEST_RECIPIENT</a>-typed value that is stored in the <b>Packet.bm.Request.Recipient</b> member of the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure. 


### -param Request [in]

A request type constant that is stored in the<b>Packet.bRequest</b> member of the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param Value [in]

A request-specific value that is stored in the <b>Packet.wValue.Value</b> member of the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param Index [in]

A request-specific index value that is stored in the <b>Packet.wIndex.Value</b> member of the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


## -returns


None



## -remarks


The <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</b> function does the following:
<ol>
<li>
Zeros the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

</li>
<li>
Sets the <b>Packet.bm.Request.Type</b> member to <b>BmRequestClass</b>.

</li>
<li>
Sets other structure members by using the <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</b> function's input arguments.

</li>
</ol>To initialize a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure, the driver should call one of the following functions:
<ul>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init.md">WDF_USB_CONTROL_SETUP_PACKET_INIT</a>


</li>
<li>
<b>WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</b>

</li>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_feature.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</a>


</li>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_get_status.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</a>


</li>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_vendor.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>


</li>
</ul>


## -see-also

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_get_status.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</a>

<a href="..\wdfusb\ne-wdfusb-_wdf_usb_bmrequest_recipient.md">WDF_USB_BMREQUEST_RECIPIENT</a>

<a href="..\wdfusb\ne-wdfusb-_wdf_usb_bmrequest_direction.md">WDF_USB_BMREQUEST_DIRECTION</a>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_feature.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</a>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_vendor.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init.md">WDF_USB_CONTROL_SETUP_PACKET_INIT</a>

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

