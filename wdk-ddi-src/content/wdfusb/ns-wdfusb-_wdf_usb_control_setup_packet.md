---
UID: NS:wdfusb._WDF_USB_CONTROL_SETUP_PACKET
title: "_WDF_USB_CONTROL_SETUP_PACKET"
author: windows-driver-content
description: The WDF_USB_CONTROL_SETUP_PACKET structure describes a setup packet for a USB control transfer.
old-location: wdf\wdf_usb_control_setup_packet.htm
tech.root: wdf
ms.assetid: f50ee559-3df7-4e15-b5a6-d6b85277c461
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_USB_CONTROL_SETUP_PACKET, DFUsbRef_d563752f-cbb6-4b63-9322-2bb0dc96d855.xml, PWDF_USB_CONTROL_SETUP_PACKET, PWDF_USB_CONTROL_SETUP_PACKET union pointer, WDF_USB_CONTROL_SETUP_PACKET, WDF_USB_CONTROL_SETUP_PACKET union, _WDF_USB_CONTROL_SETUP_PACKET, kmdf.wdf_usb_control_setup_packet, wdf.wdf_usb_control_setup_packet, wdfusb/PWDF_USB_CONTROL_SETUP_PACKET, wdfusb/WDF_USB_CONTROL_SETUP_PACKET"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfusb.h
api_name:
-	WDF_USB_CONTROL_SETUP_PACKET
product:
- Windows
targetos: Windows
req.typenames: WDF_USB_CONTROL_SETUP_PACKET, *PWDF_USB_CONTROL_SETUP_PACKET
---

# _WDF_USB_CONTROL_SETUP_PACKET structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_CONTROL_SETUP_PACKET</b> structure describes a setup packet for a USB control transfer.


## -struct-fields




### -field Packet


### -field Packet.bm


### -field Packet.bm.Request


### -field Packet.bm.Request.Recipient

A bit field that is specified by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552554">WDF_USB_BMREQUEST_RECIPIENT</a>-typed value.


### -field Packet.bm.Request.Reserved

A reserved bit field. Do not use this member.


### -field Packet.bm.Request.Type

A bit field that is specified by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552557">WDF_USB_BMREQUEST_TYPE</a>-typed value.


### -field Packet.bm.Request.Dir

A bit field that is specified by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552545">WDF_USB_BMREQUEST_DIRECTION</a>-typed value.


### -field Packet.bm.Byte

A byte-sized bitmap that contains the <b>Request.Recipient</b>, <b>Request.Reserved</b>, <b>Request.Type</b>, and <b>Request.Dir</b> bit fields. Use this member as an alternative to specifying the individual bit fields.


### -field Packet.bRequest

A request type. Request type constants are defined in <i>Usb100.h</i>. For more information about request types, see the USB specification.


### -field Packet.wValue


### -field Packet.wValue.Bytes


### -field Packet.wValue.Bytes.LowByte

The low byte of a 2-byte, request-specific value. For more information about specifying <b>wValue</b>, see the USB specification.


### -field Packet.wValue.Bytes.HiByte

The high byte of a 2-byte, request-specific value. 


### -field Packet.wValue.Value

A 2-byte value that contains the <b>Bytes.LowByte</b> and <b>Bytes.HiByte</b> values. Use this member as an alternative to specifying individual low-byte and high-byte values.


### -field Packet.wIndex


### -field Packet.wIndex.Bytes


### -field Packet.wIndex.Bytes.LowByte

The low byte of a 2-byte, request-specific value. For more information about specifying <b>wValue</b>, see the USB specification.


### -field Packet.wIndex.Bytes.HiByte

The high byte of a 2-byte, request-specific value. 


### -field Packet.wIndex.Value

A 2-byte value that contains the <b>Bytes.LowByte</b> and <b>Bytes.HiByte</b> values. Use this member as an alternative to specifying individual low-byte and high-byte values.


### -field Packet.wLength

The number of bytes to transfer, if applicable. For more information about this value, see the USB specification. The framework sets this value.


### -field Generic


### -field Generic.Bytes

An 8-byte value that represents the entire setup packet. You can use this member as an alternative to specifying individual structure members.


## -remarks



The <b>WDF_USB_CONTROL_SETUP_PACKET</b> structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550104">WdfUsbTargetDeviceSendControlTransferSynchronously</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550082">WdfUsbTargetDeviceFormatRequestForControlTransfer</a> methods.

To initialize a <b>WDF_USB_CONTROL_SETUP_PACKET</b> structure, the driver should call one of the following functions:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552571">WDF_USB_CONTROL_SETUP_PACKET_INIT</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552574">WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552576">WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552582">WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552588">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>


</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552545">WDF_USB_BMREQUEST_DIRECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552554">WDF_USB_BMREQUEST_RECIPIENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552557">WDF_USB_BMREQUEST_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550082">WdfUsbTargetDeviceFormatRequestForControlTransfer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550104">WdfUsbTargetDeviceSendControlTransferSynchronously</a>
 

 

