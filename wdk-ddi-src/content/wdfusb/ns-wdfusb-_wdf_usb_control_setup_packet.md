---
UID: NS:wdfusb._WDF_USB_CONTROL_SETUP_PACKET
title: "_WDF_USB_CONTROL_SETUP_PACKET"
author: windows-driver-content
description: The WDF_USB_CONTROL_SETUP_PACKET structure describes a setup packet for a USB control transfer.
old-location: wdf\wdf_usb_control_setup_packet.htm
old-project: wdf
ms.assetid: f50ee559-3df7-4e15-b5a6-d6b85277c461
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , *, *PWDF_USB_CONTROL_SETUP_PACKET, ,, A, B, C, D, DFUsbRef_d563752f-cbb6-4b63-9322-2bb0dc96d855.xml, E, F, K, L, N, O, P, PWDF_USB_CONTROL_SETUP_PACKET, PWDF_USB_CONTROL_SETUP_PACKET union pointer, R, S, T, U, W, WDF_USB_CONTROL_SETUP_PACKET, WDF_USB_CONTROL_SETUP_PACKET union, _, _WDF_USB_CONTROL_SETUP_PACKET, kmdf.wdf_usb_control_setup_packet, wdf.wdf_usb_control_setup_packet, wdfusb/PWDF_USB_CONTROL_SETUP_PACKET, wdfusb/WDF_USB_CONTROL_SETUP_PACKET"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfusb.h
apiname:
-	WDF_USB_CONTROL_SETUP_PACKET
product: Windows
targetos: Windows
req.typenames: WDF_USB_CONTROL_SETUP_PACKET, *PWDF_USB_CONTROL_SETUP_PACKET
req.product: Windows 10 or later.
---

# _WDF_USB_CONTROL_SETUP_PACKET structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_CONTROL_SETUP_PACKET</b> structure describes a setup packet for a USB control transfer.


## -syntax


````
typedef union _WDF_USB_CONTROL_SETUP_PACKET {
  struct {
    union {
      struct {
        BYTE Recipient  :2;
        BYTE Reserved  :3;
        BYTE Type  :2;
        BYTE Dir  :1;
      } Request;
      BYTE   Byte;
    } bm;
    BYTE   bRequest;
    union {
      struct {
        BYTE LowByte;
        BYTE HiByte;
      } Bytes;
      USHORT Value;
    } wValue;
    union {
      struct {
        BYTE LowByte;
        BYTE HiByte;
      } Bytes;
      USHORT Value;
    } wIndex;
    USHORT wLength;
  } Packet;
  struct {
    BYTE Bytes[8];
  } Generic;
} WDF_USB_CONTROL_SETUP_PACKET, *PWDF_USB_CONTROL_SETUP_PACKET;
````


## -struct-fields




### -field Packet



#### bRequest

A request type. Request type constants are defined in <i>Usb100.h</i>. For more information about request types, see the USB specification.



#### wLength

The number of bytes to transfer, if applicable. For more information about this value, see the USB specification. The framework sets this value.


### -field Packet.bm


### -field Packet.bm.Request



###### bm.Request.Recipient

A bit field that is specified by a <a href="..\wdfusb\ne-wdfusb-_wdf_usb_bmrequest_recipient.md">WDF_USB_BMREQUEST_RECIPIENT</a>-typed value.



###### bm.Request.Reserved

A reserved bit field. Do not use this member.



###### bm.Request.Type

A bit field that is specified by a <a href="..\wdfusb\ne-wdfusb-_wdf_usb_bmrequest_type.md">WDF_USB_BMREQUEST_TYPE</a>-typed value.



###### bm.Request.Dir

A bit field that is specified by a <a href="..\wdfusb\ne-wdfusb-_wdf_usb_bmrequest_direction.md">WDF_USB_BMREQUEST_DIRECTION</a>-typed value.


### -field Packet.bm.Byte

A byte-sized bitmap that contains the <b>Request.Recipient</b>, <b>Request.Reserved</b>, <b>Request.Type</b>, and <b>Request.Dir</b> bit fields. Use this member as an alternative to specifying the individual bit fields.


### -field Packet.wValue


### -field Packet.wValue.Bytes



###### wValue.Bytes.LowByte

The low byte of a 2-byte, request-specific value. For more information about specifying <b>wValue</b>, see the USB specification.



###### wValue.Bytes.HiByte

The high byte of a 2-byte, request-specific value. 


### -field Packet.wValue.Value

A 2-byte value that contains the <b>Bytes.LowByte</b> and <b>Bytes.HiByte</b> values. Use this member as an alternative to specifying individual low-byte and high-byte values.


### -field Packet.wIndex


### -field Packet.wIndex.Bytes



###### wIndex.Bytes.LowByte

The low byte of a 2-byte, request-specific value. For more information about specifying <b>wValue</b>, see the USB specification.



###### wIndex.Bytes.HiByte

The high byte of a 2-byte, request-specific value. 


### -field Packet.wIndex.Value

A 2-byte value that contains the <b>Bytes.LowByte</b> and <b>Bytes.HiByte</b> values. Use this member as an alternative to specifying individual low-byte and high-byte values.


### -field Generic



#### Bytes

An 8-byte value that represents the entire setup packet. You can use this member as an alternative to specifying individual structure members.


## -remarks



The <b>WDF_USB_CONTROL_SETUP_PACKET</b> structure is used as input to the <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicesendcontroltransfersynchronously.md">WdfUsbTargetDeviceSendControlTransferSynchronously</a> and <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforcontroltransfer.md">WdfUsbTargetDeviceFormatRequestForControlTransfer</a> methods.

To initialize a <b>WDF_USB_CONTROL_SETUP_PACKET</b> structure, the driver should call one of the following functions:

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

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_get_status.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</a>


</li>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_vendor.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>


</li>
</ul>



## -see-also

<a href="..\wdfusb\ne-wdfusb-_wdf_usb_bmrequest_recipient.md">WDF_USB_BMREQUEST_RECIPIENT</a>



<a href="..\wdfusb\ne-wdfusb-_wdf_usb_bmrequest_type.md">WDF_USB_BMREQUEST_TYPE</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforcontroltransfer.md">WdfUsbTargetDeviceFormatRequestForControlTransfer</a>



<a href="..\wdfusb\ne-wdfusb-_wdf_usb_bmrequest_direction.md">WDF_USB_BMREQUEST_DIRECTION</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicesendcontroltransfersynchronously.md">WdfUsbTargetDeviceSendControlTransferSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_CONTROL_SETUP_PACKET union%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

