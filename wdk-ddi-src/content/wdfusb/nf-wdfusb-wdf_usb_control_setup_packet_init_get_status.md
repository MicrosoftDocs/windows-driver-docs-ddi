---
UID: NF:wdfusb.WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS
title: WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS function
author: windows-driver-content
description: The WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS function initializes a WDF_USB_CONTROL_SETUP_PACKET structure for a USB control transfer that obtains device status.
old-location: wdf\wdf_usb_control_setup_packet_init_get_status.htm
old-project: wdf
ms.assetid: 1d21fe54-761b-42cf-9da2-83687cb9e079
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdf_usb_control_setup_packet_init_get_status, wdfusb/WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS, WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS, wdf.wdf_usb_control_setup_packet_init_get_status, WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS function, DFUsbRef_b1eaf694-27f6-4767-9e7f-f9af5c0fd605.xml
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
-	WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</b> function initializes a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure for a USB control transfer that obtains device status.


## -syntax


````
VOID WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS(
  _Out_ PWDF_USB_CONTROL_SETUP_PACKET Packet,
  _In_  WDF_USB_BMREQUEST_RECIPIENT   BmRequestRecipient,
  _In_  USHORT                        Index
);
````


## -parameters




### -param Packet [out]

A pointer to a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param BmRequestRecipient [in]

A <a href="..\wdfusb\ne-wdfusb-_wdf_usb_bmrequest_recipient.md">WDF_USB_BMREQUEST_RECIPIENT</a>-typed value that is stored in the <b>Packet.bm.Request.Recipient</b> member of the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure. 


### -param Index [in]

A status index value that is stored in the <b>Packet.wIndex.Value</b> member of the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


## -returns


None



## -remarks


The <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</b> function does the following:
<ol>
<li>
Zeros the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

</li>
<li>
Sets the <b>Packet.bm.Request.Type</b> member to <b>BmRequestStandard</b>.

</li>
<li>
Sets the <b>Packet.bm.Request.Dir</b> member to <b>BmRequestDeviceToHost</b>.

</li>
<li>
Sets the <b>Packet.bRequest</b> member to a "get status" request value.

</li>
<li>
Sets the <b>Packet.wValue.Value</b> member to zero.

</li>
<li>
Sets the <b>Packet-&gt;Packet.wIndex.Value</b> member to the <i>Index</i> argument.

</li>
</ol>To initialize a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure, the driver should call one of the following functions:
<ul>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init.md">WDF_USB_CONTROL_SETUP_PACKET_INIT</a>


</li>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_class.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</a>


</li>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_feature.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</a>


</li>
<li>
<b>WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</b>

</li>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_vendor.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>


</li>
</ul>


## -see-also

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_feature.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</a>

<a href="..\wdfusb\ne-wdfusb-_wdf_usb_bmrequest_recipient.md">WDF_USB_BMREQUEST_RECIPIENT</a>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_class.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</a>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init.md">WDF_USB_CONTROL_SETUP_PACKET_INIT</a>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_vendor.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

