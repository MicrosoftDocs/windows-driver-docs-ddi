---
UID: NS:usb._URB_ISOCH_TRANSFER
title: "_URB_ISOCH_TRANSFER"
author: windows-driver-content
description: The _URB_ISOCH_TRANSFER structure is used by USB client drivers to send data to or retrieve data from an isochronous transfer pipe.
old-location: buses\_urb_isoch_transfer.htm
old-project: usbref
ms.assetid: b021211a-3f72-47ff-9e69-bbf3807f4ec4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: USBD_SHORT_TRANSFER_OK, USBD_START_ISO_TRANSFER_ASAP, USBD_TRANSFER_DIRECTION_IN, _URB_ISOCH_TRANSFER, _URB_ISOCH_TRANSFER structure [Buses], buses._urb_isoch_transfer, usb/_URB_ISOCH_TRANSFER, usbstrct_5a064ef7-b08f-405f-8d73-22fea138ac29.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usb.h
api_name:
-	_URB_ISOCH_TRANSFER
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# _URB_ISOCH_TRANSFER structure


## -description


The <b>_URB_ISOCH_TRANSFER</b> structure is used by USB client drivers to send data to or retrieve data from an isochronous transfer pipe.


## -struct-fields




### -field Hdr

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_ISOCH_TRANSFER, and <b>Hdr.Length</b> must be the size of this variable-length data structure.


### -field PipeHandle

Specifies an opaque handle to the isochronous pipe. The host controller driver returns this handle when the client driver selects the device configuration with a URB of type URB_FUNCTION_SELECT_CONFIGURATION or when the client driver changes the settings for an interface with a URB of type URB_FUNCTION_SELECT_INTERFACE.   


### -field TransferFlags


Specifies zero, one, or a combination of the following flags:



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="USBD_TRANSFER_DIRECTION_IN"></a><a id="usbd_transfer_direction_in"></a><dl>
<dt><b>USBD_TRANSFER_DIRECTION_IN</b></dt>
</dl>
</td>
<td width="60%">
Is set to request data from a device. To transfer data to a device, this flag must be clear. 

</td>
</tr>
<tr>
<td width="40%"><a id="USBD_SHORT_TRANSFER_OK"></a><a id="usbd_short_transfer_ok"></a><dl>
<dt><b>USBD_SHORT_TRANSFER_OK</b></dt>
</dl>
</td>
<td width="60%">
Is set to direct the host controller not to return an error when it receives a packet from the device that is shorter than the maximum packet size for the endpoint. This flag has no effect on an isochronous pipe, because the bus driver does not return an error when it receives short packets on an isochronous pipe.

</td>
</tr>
<tr>
<td width="40%"><a id="USBD_START_ISO_TRANSFER_ASAP"></a><a id="usbd_start_iso_transfer_asap"></a><dl>
<dt><b>USBD_START_ISO_TRANSFER_ASAP</b></dt>
</dl>
</td>
<td width="60%">
Causes the transfer to begin on the next frame, if no transfers have been submitted to the pipe since the pipe was opened or last reset. Otherwise, the transfer begins on the first frame that follows all currently queued requests for the pipe. The actual frame that the transfer begins on will be adjusted for bus latency by the host controller driver.

</td>
</tr>
</table>
 


### -field TransferBufferLength

Specifies the length, in bytes, of the buffer specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL</b>. The host controller driver returns the number of bytes that are sent to or read from the pipe in this member.


### -field TransferBuffer

A pointer to a resident buffer for the transfer is <b>NULL</b> if an MDL is supplied in <b>TransferBufferMDL</b>. The contents of this buffer depend on the value of <b>TransferFlags</b>. If USBD_TRANSFER_DIRECTION_IN is specified, this buffer will contain data that is read from the device on return from the host controller driver. Otherwise, this buffer contains driver-supplied data for transfer to the device.


### -field TransferBufferMDL

A pointer to an MDL that describes a resident buffer is <b>NULL</b> if a buffer is supplied in <b>TransferBuffer</b>. The contents of the buffer depend on the value of <b>TransferFlags</b>. If USBD_TRANSFER_DIRECTION_IN is specified, the described buffer will contain data that is read from the device on return from the host controller driver. Otherwise, the buffer contains driver-supplied data for transfer to the device. This MDL must be allocated from nonpaged pool.


### -field UrbLink

Reserved. Do not use.


### -field hca

Reserved. Do not use.


### -field StartFrame

Specifies the frame number that the transfer should begin on. This variable must be within a system-defined range of the current frame. The range is specified by the constant USBD_ISO_START_FRAME_RANGE.

If START_ISO_TRANSFER_ASAP is set in <b>TransferFlags</b>, this member contains the frame number that the transfer began on, when the request is returned by the host controller driver. Otherwise, this member must contain the frame number that this transfer begins on.


### -field NumberOfPackets

Specifies the number of packets that are described by the variable-length array member <b>IsoPacket</b>.


### -field ErrorCount

Contains the number of packets that completed with an error condition on return from the host controller driver.


### -field IsoPacket

Contains a variable-length array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539084">USBD_ISO_PACKET_DESCRIPTOR</a> structures that describe the isochronous transfer packets to be transferred on the USB bus.  For more information about this member see the Remarks section.


## -remarks



The USB bus driver always returns a value of USBD_STATUS_SUCCESS in <b>Hdr.Status</b>, unless  every packet in the transfer generated an error or the request was not well-formed and could not be executed at all. The following table includes possible error codes returned in <b>Hdr.Status</b>.

<table>
<tr>
<th>Error value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
USBD_STATUS_ISOCH_REQUEST_FAILED

</td>
<td>
Indicates that every packet of an isochronous request was completed with errors. 

</td>
</tr>
<tr>
<td>
USBD_STATUS_BAD_START_FRAME

</td>
<td>
Indicates that the requested start frame is not within USBD_ISO_START_FRAME_RANGE of the current USB frame. 

</td>
</tr>
<tr>
<td>
USBD_ISO_NOT_ACCESSED_LATE

</td>
<td>
Indicates that every packet was submitted too late for the packet to be sent, based on the requested start frame. 

</td>
</tr>
<tr>
<td>
USBD_STATUS_INVALID_PARAMETER

</td>
<td>
Indicates that one of the URB parameters was incorrect. 

</td>
</tr>
</table>
 

Before the host controller sends an isochronous request to a USB device, it requires information about the device's endpoint to which it must send or receive data. This information is stored in endpoint descriptors (<a href="https://msdn.microsoft.com/library/windows/hardware/ff539317">USB_ENDPOINT_DESCRIPTOR</a>) that are retrieved from the selected configuration descriptor. 
After the bus driver gets the endpoint descriptor, it creates an isochronous transfer pipe to set up the data transfer. The pipe's attributes are stored in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539114">USBD_PIPE_INFORMATION</a> structure. For isochronous transfers, the members are set as follows:<ul>
<li>The  <b>PipeType</b> member specifies the type of transfer and is set to UsbdPipeTypeIsochronous.</li>
<li>The <b>MaximumPacketSize</b> member specifies the amount of data, in bytes, that constitutes one packet. For isochronous transfers, the packet size is fixed and can be a value from 0-1024. The packet size either equals or is less than the <b>wMaxPacketSize</b> value of the endpoint descriptor.</li>
<li>The <b>Interval</b> member is derived from the <b>bInterval</b> value of the endpoint descriptor. This value is used to calculate the polling period that indicates the frequency at which data is sent on the bus. For full speed devices, the period is measured in units of 1 millisecond frames; for high speed devices, the period is measured in microframes.</li>
</ul>The host controller also determines the amount of data that can be transferred (within a frame or a microframe) depending on the type of device. This information is available in bits <b>12.. 11</b> of  <b>wMaxPacketSize</b> in the endpoint descriptor. 

For full-speed devices, only one packet can be transferred within a frame; bits <b>12.. 11</b> are reserved and set to zero. 

For high speed devices, data can be transferred in a single packet or might span multiple packets, within a microframe. 
If bits <b>12.. 11</b> are set to <i>n</i>,  you can transfer <code>(n+1)*MaximumPacketSize</code> bytes per microframe. Bits <b>12.. 11</b> set to zero indicate that only one packet can be transferred in a microframe. If bits <b>12.. 11</b> are set to 1,  the host controller can transfer two packets in a microframe.


The <b>IsoPacket</b> member of <b>_URB_ISOCH_TRANSFER</b> is an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539084">USBD_ISO_PACKET_DESCRIPTOR</a> that describes the transfer buffer layout. Each element in the array correlates to data that is transferred in one microframe. If <b>IsoPacket</b> has <i>n</i> elements,  the host controller transfers use <i>n</i> frames (for full speed devices) or microframes (for high speed devices) to transfer data. The <b>IsoPacket[</b>i<b>].Offset</b> member is used to track the amount of data to send or receive. This is done  by setting a byte offset from the start of the entire transfer buffer for the request. 

For example, there are five microframes available to transfer 1024 byte-sized packets.

If bits <b>12.. 11</b> are set to zero (indicating a single packet per microframe transfer),  <b>IsoPacket</b> contains the following entries:

Microframe 1<code> IsoPacket.Element[0].Offset = 0</code> (start address) 

Microframe 2<code> IsoPacket.Element[1].Offset = 1024</code>

Microframe 3<code> IsoPacket.Element[2].Offset = 2048</code>

Microframe 4<code> IsoPacket.Element[3].Offset = 3072</code>

Microframe 5<code> IsoPacket.Element[4].Offset = 4096</code>

If bits <b>12.. 11</b> are set to 1 (indicating two packets per microframe),  <b>IsoPacket</b> contains the following entries:

Microframe 1<code> IsoPacket.Element[0].Offset = 0</code> (start address) 

Microframe 2<code> IsoPacket.Element[1].Offset = 2048</code>

Microframe 3<code> IsoPacket.Element[2].Offset = 4096</code>

Microframe 4<code> IsoPacket.Element[3].Offset = 6144</code>

Microframe 5<code> IsoPacket.Element[4].Offset = 8192</code>

<b>Note</b>  For multiple packets, the offset value indicates sizes for all the packets within the microframe.

The <b>IsoPacket[</b>i<b>].Length</b> member is updated by the host controller to indicate the actual number of bytes  that are received from the device for isochronous IN transfers. <b>IsoPacket[</b>i<b>].Length</b> is not used for isochronous OUT transfers.

Drivers can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537144">GET_ISO_URB_SIZE</a> macro to determine the size that is needed to hold the entire URB. If the length is too small to fill the space set aside for this packet, the bus driver leaves a gap from the end of the retrieved data to the offset for the next packet. The bus driver will not adjust the offsets to avoid wasting buffer space. 

The <b>TransferBuffer</b> or <b>TransferBufferMDL</b> members must specify a virtually contiguous buffer.

Treat other members that are part of this structure but not described here as opaque. They are reserved for system use. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406225">How to Transfer Data to USB Isochronous Endpoints</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539084">USBD_ISO_PACKET_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406231">USBD_IsochUrbAllocate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a>
 

 

